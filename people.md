---
title: People
permalink: /people/
---
 
{% assign people_sorted = site.people | sort: 'joined' %}
{% assign role_array = "pi|postdoc|phd|ms" | split: "|" %}
 
{% for role in role_array %}
 
{% assign people_in_role = people_sorted | where: 'position', role %}
 
<!-- Skip section if there's nobody -->
{% if people_in_role.size == 0 %}
  {% continue %}
{% endif %}
 
<div class="pos_header">
{% if role == 'pi' %}
<h3>Professor</h3>
<!-- <h3>Principal Investigator</h3> -->
{% elsif role == 'postdoc' %}
<h3>Postdoctoral Researcher</h3>
{% elsif role == 'phd' %}
<h3>Ph.D. Students</h3> <p>(👑: Lab admin)</p>
{% elsif role == 'ms' %}
<h3>Master's Students</h3>
{% endif %}
</div>
<!-- 왕관 로고 관련 style -->
<style>
  /* 컨테이너 (기준점) */
.list-item-people {
  position: relative;
  display: inline-block;
}
/* 2층: 메인 이미지 위에 올라가는 첫 번째 요소 */
.layer-1 {
  position: absolute;
  top: 0;
  left: 0;
  width: 70px;
  transform: translate(-10%, -10%);
  z-index: 2; /* 메인 이미지(1)보다 위에 배치 */
}
</style>
 
<div class="content list people">
  {% for profile in people_sorted %}
    {% if profile.position contains role %}
      <div class="list-item-people">
        <p class="list-post-title">
          {% if profile.avatar %}
            <!-- <a href="{{ site.baseurl }}{{ profile.url }}"><img class="profile-thumbnail" src="{{site.baseurl}}/images/people/{{profile.avatar}}"></a> -->
            <a href="{{ site.baseurl }}{{ profile.url }}">                     
              <img class="profile-thumbnail " src="{{site.baseurl}}/images/people/{{profile.avatar}}">
              <!-- 방장인 경우, 왕관 로고 추가 --> 
              {% if profile.lab_admin %}
              <img src="{{site.baseurl}}/images/crown_logo.png" class="layer-1">              
              {% endif %}
              <!-- 신입생인 경우, 새싹 로고 추가 --> 
              {% if profile.newbie %}
              <img src="{{site.baseurl}}/images/newbie_logo.png" class="layer-1">              
              {% endif %}
            </a>
          {% else %}
            <a href="{{ site.baseurl }}{{ profile.url }}"><img class="profile-thumbnail" src="http://evansheline.com/wp-content/uploads/2011/02/facebook-Storm-Trooper.jpg"></a>
          {% endif %}
          <!-- 방장인 경우, 이름에 이모지 추가 --> 
          {% if profile.lab_admin %}
            <a class="name" href="{{ site.baseurl }}{{ profile.url }}">{{ profile.name }} 👑</a>             
          {% else %}
          <a class="name" href="{{ site.baseurl }}{{ profile.url }}">{{ profile.name }}</a>
          {% endif %}
        </p>
      </div>    
    {% endif %}
  {% endfor %}
</div>
<hr>
{% endfor %}
 
 
 
<!-- Alumni: 데이터는 _data/alumni.yml, 스타일은 style.scss의 Alumni 섹션 -->
<div class="pos_header">
<h3>Alumni</h3>
</div>
<div class="alumni">
{%- assign alumni_degrees = "phd|ms" | split: "|" -%}
{%- for degree in alumni_degrees -%}
  {%- assign alumni_group = site.data.alumni | where: "degree", degree -%}
  {%- if alumni_group.size > 0 %}
  <div class="alumni-group">
    <h4 class="alumni-degree">{% if degree == 'phd' %}Ph.D.{% else %}M.S.{% endif %}</h4>
    <ul class="news-list">
    {%- for alum in alumni_group %}
      <li class="news-item">
        <!-- <span class="news-date">{{ alum.graduated | replace: "-", "." }}</span> -->
        <span class="news-date">{{ alum.graduated | append: "-01" | date: "%b %Y" }}</span>
        <div class="alumni-body">
          <span class="alumni-name">{% if alum.homepage %}<a href="{{ alum.homepage }}">{{ alum.name }}</a>{% else %}{{ alum.name }}{% endif %}</span>
          {%- if alum.email %} <a class="alumni-email" href="mailto:{{ alum.email }}" aria-label="Email {{ alum.name }}" title="{{ alum.email }}"><i class="fa fa-envelope-o" aria-hidden="true"></i></a>{% endif %}
          <span class="alumni-now">{{ alum.now }}</span>
        </div>
      </li>
    {%- endfor %}
    </ul>
  </div>
  {%- endif %}
{%- endfor %}
</div>
 