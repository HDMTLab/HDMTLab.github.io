---
title: News
permalink: /news/
---


<header class="masthead text-center">
    <h1>News</h1>
</header>
  <br>

  <div class="news">
    <ul style="list-style-position:outside;padding:20px" >
      <!-- {% for new in site.data.news %}
        {{now}}
        {{new.date}} | {{new.details}} <br>
      {% endfor %} -->
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
          
