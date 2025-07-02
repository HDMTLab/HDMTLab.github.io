---
title: People
permalink: /people/
---

{% assign people_sorted = site.people | sort: 'joined' %}
{% assign role_array = "pi|postdoc|phd|ms|alumni" | split: "|" %}

{% for role in role_array %}

{% assign people_in_role = people_sorted | where: 'position', role %}

<!-- Skip section if there's nobody -->
{% if people_in_role.size == 0 %}
  {% continue %}
{% endif %}

<div class="pos_header">
{% if role == 'pi' %}
<h3>Principal Investigator</h3>
{% elsif role == 'postdoc' %}
<h3>Postdoctoral Fellows</h3>
{% elsif role == 'phd' %}
<h3>Ph.D. Students</h3>
{% elsif role == 'ms' %}
<h3>M.S. Students</h3>
{% elsif role == 'alumni' %}
<h3>Alumni</h3>
{% endif %}
</div>

{% if role != 'alumni' %}
<div class="content list people">
  {% for profile in people_sorted %}
    {% if profile.position contains role %}
      <div class="list-item-people">
        <p class="list-post-title">
          {% if profile.avatar %}
            <a href="{{ site.baseurl }}{{ profile.url }}"><img class="profile-thumbnail" src="{{site.baseurl}}/images/people/{{profile.avatar}}"></a>
          {% else %}
            <a href="{{ site.baseurl }}{{ profile.url }}"><img class="profile-thumbnail" src="http://evansheline.com/wp-content/uploads/2011/02/facebook-Storm-Trooper.jpg"></a>
          {% endif %}
          <a class="name" href="{{ site.baseurl }}{{ profile.url }}">{{ profile.name }}</a>
        </p>
      </div>    
    {% endif %}
  {% endfor %}
</div>
<hr>

{% else %}

{% endif %}
{% endfor %}



<!-- Alumni parts; Extract it from "if" and "for loop" -->
<style>
table th:first-of-type {
    width: 18%;
}
table th:nth-of-type(2) {
    width: 27%;
}
table th:nth-of-type(3) {
    width: 55%;
}
</style>

<div class="pos_header">

<h3>Alumni</h3>
<br>
</div>

| Who are they | When were they here | Where they went |
| :------------- |:-------------| :----------|
| [Hoyoung Park](https://sites.google.com/view/hoyoung-park/home?authuser=0) | Ph.D. Student (2020 - 2021) | Assistant Professor, Dept. of Statistics at Sookmyung Women's Univ. |
| Soyeon Lim | MS Student (2020 - 2023) | Korea Energy Agency |
| Dohyup Shin | MS Student (2021 - 2023) | LG U+ |
| Myungjun Kim | MS Student (2021 - 2023) | Samsung Electronics |
| Seungyeop Hyun | MS Student (2021 - 2023) | Samsung Electronics |
| Dayeon Jung | MS Student (2022 - 2024) | Samsung Electronics |
| Kyurhi Kim | MS Student (2022 - 2024) | Ph.D. Student at Emory University |
| Yeji Seong | MS Student (2023 - 2025) | LG CNS |

<!-- | Who are they | When were they here | Where they went |
| :------------- |:-------------| :----------|
| [Hoyoung Park](http://hdmtlab.github.io/people/hoyoung_park/index.html) | Ph.D. Student (2020 - 2021) | Assistant Professor, Department of Statistics at Sookmyung Women's University |
| [Soyeon Lim](http://hdmtlab.github.io/people/soyeon_lim/index.html) | MS Student (2020 - 2023) | |
| [Dohyup Shin](http://hdmtlab.github.io/people/dohyup_shin/index.html) | MS Student (2021 - 2023) | LG U+ |
| [Myungjun Kim](http://hdmtlab.github.io/people/myungjun_kim/index.html) | MS Student (2021 - 2023) | Samsung Electronics |
| [Seungyeop Hyun](https://hdmtlab.github.io/people/seungyeop_hyun/index.html) | MS Student (2021 - 2023) | Samsung Electronics |
| [Dayeon Jung](https://hdmtlab.github.io/people/dayeon_jung/index.html) | MS Student (2022 - 2024) | Samsung Electronics |
| [Kyurhi Kim](https://hdmtlab.github.io/people/kyurhi_kim/index.html) | MS Student (2022 - 2024) | Ph.D. Student at Emory University | -->