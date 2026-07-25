---
title: Events
permalink: /workshop/
---



<header class="masthead text-center">
    <h1>Workshop</h1>
  </header>

------


{% assign workshop_list = site.workshop | sort: 'joined' %}

<div class="content list">
{% for workshop_ind in workshop_list %}
<!-- <div class="list-item">
<p><a href="{{ site.baseurl }}{{ workshop_ind.url }}"><h5>{{ workshop_ind.title }}</h5></a></p>
</div> -->
<!-- hidden: true 이면 비밀번호 요청; 비밀번호: hdmt -->
{% if workshop_ind.hidden == true %}
<ul>
  <li>
    <!-- 자물쇠 아이콘: 클릭 시 checkPassword 함수를 실행합니다. -->
    <span style="cursor: pointer; font-size: 0.8em; color: #888;" title="비밀번호 입력" onclick="checkPassword(this)">
      🔒
    </span>    
    <!-- 숨겨진 내용: 처음에는 display: none; 으로 안 보이게 설정합니다. -->
    <span class="hidden-content" style="display: none;">
      <a href="{{ site.baseurl }}{{ workshop_ind.url }}">
        <strong>{{ workshop_ind.title }}</strong>
      </a>
    </span>
  </li>
</ul>
{% else %}
<ul>
  <li>
    <a href="{{ site.baseurl }}{{ workshop_ind.url }}">
      <strong>{{ workshop_ind.title }}</strong>
    </a>
  </li>
</ul>
{% endif %}
{% endfor %}
</div>


<!-- 기능 작동을 위한 자바스크립트 (파일 맨 아래에 한 번만 넣어주세요) -->
<script>
function checkPassword(iconElement) {
  // 1. 비밀번호를 묻는 알림창 띄우기
  var userInput = prompt("비밀번호를 입력하세요:");
  
  // 2. 비밀번호 확인 (원하는 비밀번호로 '1234' 부분을 수정하세요)
  var correctPassword = "hdmt"; 

  if (userInput === correctPassword) {
    // 3. 비밀번호가 맞으면 자물쇠 옆의 숨겨진 태그를 찾아서 보여줌
    var hiddenContent = iconElement.nextElementSibling;
    if (hiddenContent) {
      hiddenContent.style.display = "inline";
      iconElement.style.display = "none"; // 열린 후에는 자물쇠 아이콘 숨기기 (선택 사항)
    }
  } else if (userInput !== null) {
    // 4. 취소를 누르지 않았는데 틀린 경우
    alert("비밀번호가 틀렸습니다.");
  }
}
</script>