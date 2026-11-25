---
title: Events
permalink: /workshop/
---
 
 
 
<header class="masthead text-center">
    <h1>Workshop</h1>
  </header>
------
 
<!--
  각 워크숍 파일(_workshop/*.md) 맨 위에 start_date, end_date, venue를 적으면
  날짜·장소가 카드에 표시되고, start_date 기준 최신순으로 정렬됩니다.
  일수와 발표 수는 session 데이터에서 자동으로 계산됩니다.
  스타일은 style.scss의 Workshop 섹션에 있습니다.
-->
<div class="workshop-list">
{%- assign workshop_list = site.workshop | sort: 'start_date' | reverse -%}
{%- assign today = 'now' | date: '%Y-%m-%d' -%}
{%- for ws in workshop_list -%}
  {%- assign ws_talks = ws.session | where: "type", "talk" -%}
  {%- assign ws_days = ws.session | map: "day" | uniq -%}
  {%- assign ws_end_date = ws.end_date | default: ws.start_date -%}
  {%- assign ws_start = ws.start_date | date: '%Y-%m-%d' -%}
  {%- assign ws_end = ws_end_date | date: '%Y-%m-%d' -%}
  {%- assign ws_start_month = ws.start_date | date: '%m' -%}
  {%- assign ws_end_month = ws_end_date | date: '%m' %}
  <div class="workshop-card{% if ws.hidden %} is-hidden{% endif %}">
    <div class="workshop-when">
      {%- if ws.start_date %}
      <span class="workshop-month">{{ ws.start_date | date: '%b %Y' }}</span>
      <span class="workshop-days">
        {{- ws.start_date | date: '%-d' -}}
        {%- if ws_end != ws_start -%}
          –{% if ws_end_month != ws_start_month %}{{ ws_end_date | date: '%b' }} {% endif %}{{ ws_end_date | date: '%-d' }}
        {%- endif -%}
      </span>
      {%- endif %}
    </div>
    <div class="workshop-main">
      {%- if ws.start_date and ws_end >= today %}
      <span class="workshop-badge">Upcoming</span>
      {%- endif %}
      <h3 class="workshop-title">
        {%- if ws.hidden -%}
          {{ ws.title }}
        {%- else -%}
          <a href="{{ site.baseurl }}{{ ws.url }}">{{ ws.title }}</a>
        {%- endif -%}
      </h3>
      {%- if ws.venue %}
      <p class="workshop-venue">{{ ws.venue }}</p>
      {%- endif %}
      <p class="workshop-meta">
        {%- if ws.hidden %}
        <span>Program coming soon</span>
        {%- else %}
        <span>{{ ws_days.size }} {% if ws_days.size == 1 %}day{% else %}days{% endif %} · {{ ws_talks.size }} {% if ws_talks.size == 1 %}talk{% else %}talks{% endif %}</span>
        <a class="workshop-more" href="{{ site.baseurl }}{{ ws.url }}">View program &rarr;</a>
        {%- endif %}
      </p>
    </div>
  </div>
{%- endfor %}
</div>
 