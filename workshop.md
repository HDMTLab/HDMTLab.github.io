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

<ul>
<li><a href="{{ site.baseurl }}{{ workshop_ind.url }}"><strong>{{ workshop_ind.title }}</strong></a></li>
</ul>

{% endfor %}
</div>

<!-- <div class="content list">
  {% for post in site.posts %}
    {% if post.categories contains 'gallery' %}
    <div class="list-item">
      <p class="list-post-title">
        <a href="{{ post.url | prepend: site.baseurl }}">
            <div class="row">
                <div class="col-sm-4">
                    <img src="/{% if post.header-img %}{{ post.header-img }}{% else %}{{ site.header-img }}{% endif %}">
                </div>
                <div class="col-sm-8">
                    <h3 class="post-title">
                        {{ post.title }}
                    </h3>
                    <p class="list-detail" >
                      {{ post.content | strip_html | truncatewords:35 }}
                    </p>
                </div>
            </div>
            <hr/>
        </a>
      </p>
    </div>
    {% endif %}
  {% endfor %}
</div> -->
