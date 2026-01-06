---
title: 2026 HDMT Winter Workshop
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


# 2026 HDMT Winter Workshop

--- 

## Introduction

The *2026 HDMT Winter Workshop* is organized to promote academic and personal interaction among current members and alumni of the *High-Dimensional Multiple Testing Lab*. Through this workshop, participants are expected to gain a better understanding of each other's research topics and engage in active discussions.

Each participant will give a presentation of approximately *25 minutes* on their research, followed by a question-and-answer session.

---

## Date & Venue

- January 21, 2026, 13:00 – January 22, 2026, 12:00
<!-- - 2026.01.21 13:00 - 2026.01.22 12:00 -->
<!-- - 13:00, Jan 21, 2026 – 12:00, Jan 22, 2026 -->
- Room 806-1, Convention Center, Siheung Campus, Seoul National University

---


<!--
# 2026 고차원 다중검정 연구실 겨울 워크샵

<br>

--- 

## 소개

고차원 다중검정 연구실 구성원과 졸업생들의 연구실 구성원이 인적, 학문적 교류를 하기 위한 워크샵을 개최한다. 이를 통해 서로의 연구 주제에 대해 이해하고 논의해볼 수 있을 것으로 기대한다. 각자의 연구 주제에 대해 25분에 걸쳐 발표하고, 질의응답을 진행한다.

고차원 다중검정 연구실 구성원과 졸업생들의 연구실 구성원이 인적·학문적 교류를 할 수 있도록 HDMT Winter Workshop 2026을 개최한다. 본 워크숍을 통해 서로의 연구 주제에 대해 이해하고 자유롭게 논의할 수 있을 것으로 기대한다.

워크숍에서는 각 참여자가 자신의 연구 주제에 대해 약 25분간 발표를 진행하며, 발표 후에는 질의응답 시간을 통해 연구 내용과 방법론에 대해 토론한다.

---

## 일시 및 장소

- 2026년 1월 21일(수) 오후 1시 ~ 1월 22일(목) 오후 12시
- 서울대학교 시흥캠퍼스 컨벤션센터 806-1호

--- -->



## Programs

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

*This work was supported by the National Research Foundation of Korea (NRF) grant funded by the Korea government (MSIT) (RS-2025-00556575).*

<!-- 이 성과는 정부(과학기술정보통신부)의 재원으로 한국연구재단의 지원을 받아 수행된 연구임(No. RS-2025-00556575) -->