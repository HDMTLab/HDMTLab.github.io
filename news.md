---
title: News
permalink: /news/
---
 
<!-- ## **News** -->
 
<header class="masthead text-center">
    <h1>News</h1>
</header>
------
 
<!-- 항목 모양은 style.scss의 News 섹션에서 홈의 Recent News와 함께 관리 -->
<div class="news-archive">
{%- assign news_by_year = site.data.news | group_by_exp: "new", "new.date | date: '%Y'" -%}
{%- for year in news_by_year %}
  <div class="news-year-group">
    <h2 class="news-year">{{ year.name }}</h2>
    <ul class="news-list">
    {%- for new in year.items %}
      <li class="news-item">
        <time class="news-date" datetime="{{ new.date | date: '%Y-%m-%d' }}">{{ new.date | date: '%Y.%m.%d' }}</time>
        <div class="news-body">{{ new.details }}</div>
      </li>
    {%- endfor %}
    </ul>
  </div>
{%- endfor %}
</div>
 