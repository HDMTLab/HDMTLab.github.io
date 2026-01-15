---
title: 2026 Workshop on Robust Inference for High-Dimensional Complex Data 
permalink: /workshop/workshop2026winter/
---

<style>
.talk-card {
  border: 1px solid #e0e0e0;
  border-radius: 8px;
  padding: 0.6em 1em;
  margin: 1em 0;
  background: #fafafa;
  transition: box-shadow 0.2s ease;
}

.talk-card:hover {
  box-shadow: 0 4px 12px rgba(0,0,0,0.06);
}

.talk-card summary {
  cursor: pointer;
  list-style: none;
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.talk-card summary::-webkit-details-marker {
  display: none;
}

.talk-title {
  font-weight: 600;
}

.talk-speaker {
  /* font-style: italic; */
  color: #555;
}

.talk-abstract {
  margin-top: 0.8em;
  padding-top: 0.8em;
  border-top: 1px solid #ddd;
  line-height: 1.6;
}
.talk-abstract {
  animation: fadeIn 0.25s ease-in;
}

@keyframes fadeIn {
  from {
    opacity: 0;
    transform: translateY(-4px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

.session-title {
  display: flex;
  justify-content: space-between;
  align-items: baseline;
  margin-top: 2.2em;
  margin-bottom: 0.8em;
  padding-bottom: 0.3em;
  border-bottom: 2px solid #ddd;
  font-size: 1.4em;
  font-weight: 600;
}


.session-time {
  font-size: 0.9em;
  font-weight: normal;
  color: #666;
  white-space: nowrap;
}

.day-title {
  margin-top: 2em;
  margin-bottom: 1em;
  font-size: 2em;
  font-weight: 700;
  border-bottom: 3px solid #000;
}
</style>


# 2026 Workshop on Robust Inference for High-Dimensional Complex Data

--- 

## Introduction

The *2026 Workshop on Robust Inference for High-Dimensional Complex Data* aims to bring together researchers to discuss recent advances in robust statistical inference for modern complex data settings. The workshop focuses on methodological developments that ensure reliable inference in the presence of high dimensionality, dependence, and structural complexity.

The sessions will cover a range of contemporary topics, including *multiple testing, e-values, false discovery rate (FDR) control, conformal prediction, test for means, empirical Bayes, and other related topics*. These methodologies will be discussed in the context of complex data types such as *high-dimensional data, online or streaming data, functional data, and tensor-valued data*.

Through presentations and discussions, the workshop seeks to foster the exchange of ideas on unifying principles and practical challenges in robust inference, and to encourage collaboration among researchers working on theoretical foundations as well as methodological and applied aspects of modern statistics. Each participant will give a presentation of approximately 20 minutes on their research, followed by a question-and-answer session.


---

## Date & Venue

- January 21, 2026, 13:00 – January 22, 2026, 12:00
- Room 806, Convention Center, Siheung Campus, Seoul National University


---




## Program and Schedule


<!-- site.data.{yml 파일명}만 수정해서 사용 (원본 파일은 data/workshop_2026winter.yml) -->
{% assign days = site.data.workshop_2026winter | group_by: "day" %}

{% for day in days %}
<h1 class="day-title">{{ day.name }}</h1>

{% assign sessions = day.items | group_by: "session_id" %}
{% for session in sessions %}
{% assign first = session.items | first %}

<h2 class="session-title">
<span class="session-name">{{ first.session }}</span>
{% if first.session_time %}
<span class="session-time">{{ first.session_time }}</span>
{% endif %}
</h2>

{% for talk in session.items %}
{% if talk.type == "talk" %}
<details class="talk-card">
    <summary>
    <span class="talk-title">{{ talk.title }}</span>
    <span class="talk-speaker">{{ talk.speaker }}</span>
    </summary>

    <div class="talk-abstract">
    {{ talk.abstract }}
    </div>
</details>
{% endif %}
{% endfor %}
{% endfor %}
{% endfor %}


---

## Location

<br>


#### 서울대학교 시흥캠퍼스 컨벤션센터 806호 (Workshop)

<!-- * 카카오맵 - 지도퍼가기 -->
<!-- 1. 지도 노드 -->
<div id="daumRoughmapContainer1768018058689" class="root_daum_roughmap root_daum_roughmap_landing" style="width:70%"></div>

<!--
	2. 설치 스크립트
	* 지도 퍼가기 서비스를 2개 이상 넣을 경우, 설치 스크립트는 하나만 삽입합니다.
-->
<script charset="UTF-8" class="daum_roughmap_loader_script" src="https://ssl.daumcdn.net/dmaps/map_js_init/roughmapLoader.js" ></script>

<!-- 3. 실행 스크립트 -->
<script charset="UTF-8">
	new daum.roughmap.Lander({  
		"timestamp" : "1768018058689",
		"key" : "fdm46rmtjd8",
		"mapWidth" : "80%",
		"mapHeight" : "300"
	}).render();
</script>


<!-- <iframe src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d1489.6365384984156!2d126.71831237291562!3d37.36500091251467!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x357b70e84a95728d%3A0x1dd90cd7498ac1f9!2z7ISc7Jq464yA7ZWZ6rWQIOyLnO2dpey6oO2NvOyKpA!5e0!3m2!1sko!2skr!4v1768007435061!5m2!1sko!2skr" width="80%" height="300" style="border:0;" allowfullscreen="" loading="lazy" referrerpolicy="no-referrer-when-downgrade"></iframe> -->

<br>

#### 돝집 거북섬점 (석식)

<!-- * 카카오맵 - 지도퍼가기 -->
<!-- 1. 지도 노드 -->
<div id="daumRoughmapContainer1768018227575" class="root_daum_roughmap root_daum_roughmap_landing" style="width:70%"></div>

<!-- 3. 실행 스크립트 -->
<script charset="UTF-8">
	new daum.roughmap.Lander({
		"timestamp" : "1768018227575",
		"key" : "frc7dx3s2fi",
		"mapWidth" : "80%",
		"mapHeight" : "300"
	}).render();
</script>

<!-- <iframe src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d3172.7940147177683!2d126.67655072716717!3d37.32370667210244!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x357b75006eb3b8af%3A0xd26e2bfeb4b9e575!2z64-d7KeR!5e0!3m2!1sko!2skr!4v1768007491647!5m2!1sko!2skr" width="80%" height="300" style="border:0;" allowfullscreen="" loading="lazy" referrerpolicy="no-referrer-when-downgrade"></iframe> -->

<br>

#### 시흥 웨이브 엠 호텔 웨스트 호텔 (숙박/조식)

<!-- * 카카오맵 - 지도퍼가기 -->
<!-- 1. 지도 노드 -->
<div id="daumRoughmapContainer1768018361511" class="root_daum_roughmap root_daum_roughmap_landing" style="width:70%"></div>

<!-- 3. 실행 스크립트 -->
<script charset="UTF-8">
	new daum.roughmap.Lander({
		"timestamp" : "1768018361511",
		"key" : "fdmba9xddvc",
		"mapWidth" : "80%",
		"mapHeight" : "300"
	}).render();
</script>

<!-- <iframe src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d3172.9383971279926!2d126.67545637716707!3d37.32028687210339!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x357b75002a8b6fa1%3A0xbc0d7535b1b349d1!2z7Juo7J2067iM7Jeg7Zi47YWUIOybqOyKpO2KuA!5e0!3m2!1sko!2skr!4v1768007571132!5m2!1sko!2skr" width="80%" height="300" style="border:0;" allowfullscreen="" loading="lazy" referrerpolicy="no-referrer-when-downgrade"></iframe> -->

<br>

#### 투파인드피터 배곧점 (중식)

<!-- * 카카오맵 - 지도퍼가기 -->
<!-- 1. 지도 노드 -->
<div id="daumRoughmapContainer1768018397700" class="root_daum_roughmap root_daum_roughmap_landing" style="width:70%"></div>

<!-- 3. 실행 스크립트 -->
<script charset="UTF-8">
	new daum.roughmap.Lander({
		"timestamp" : "1768018397700",
		"key" : "fdo3baww2h6",
		"mapWidth" : "80%",
		"mapHeight" : "300"
	}).render();
</script>

<!-- <iframe src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d3170.829996979321!2d126.7244165771686!3d37.37019927208997!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x357b714c38ab5daf%3A0x47b1d58189e97644!2z7Yis7YyM7J2465Oc7ZS87YSwIOuwsOqzp-ygkA!5e0!3m2!1sko!2skr!4v1768007685137!5m2!1sko!2skr" width="80%" height="300" style="border:0;" allowfullscreen="" loading="lazy" referrerpolicy="no-referrer-when-downgrade"></iframe> -->

---

*This work was supported by the National Research Foundation of Korea (NRF) grant funded by the Korea government (MSIT) (RS-2025-00556575).*

<!-- 이 성과는 정부(과학기술정보통신부)의 재원으로 한국연구재단의 지원을 받아 수행된 연구임(No. RS-2025-00556575) -->