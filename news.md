---
title: News
permalink: /news/
---

<!-- ## **News** -->

<header class="masthead text-center">
    <h1>News</h1>
</header>

------


<style>
table td:first-of-type {
    width: 15%;
}
table td:nth-of-type(2) {
    width: 85%;
}
td {
  font-size: 15px !important;
}
</style>


<table>
  <tr>
    <td> <b>Date</b> </td>
    <td> <b>Event</b> </td>
  </tr>
  {% for new in site.data.news %}
  <tr>
    <td> {{ new.date }} </td>
    <td> {{ new.details }} </td>
  </tr>
 {% endfor %}
</table>




<!--
  <div class="news">
    <ul style="list-style-position:outside;padding:20px">
      {% for new in site.data.news %}
      <h4>
          <li> {{ new.date }} | 
            <span>
              {{ new.details }}
            </span>
          </li>
      </h4>
      <br>
      {% endfor %}
    </ul>
  </div>
-->      
