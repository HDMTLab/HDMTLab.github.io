---
title: Gallery
permalink: /gallery/
---

<!-- <div class='container'>
  <header class="masthead text-center">
    <h1>Gallery</h1>
    <div class="gallery">
      {% for event in site.gallery %}
        {{event}}

        <div class="event">
          <h3>{{ event.title }}</h3>
          <a href="{{ event.url }}">
            <img src="/gallery/{{ event.photos_folder }}/{{ event.represent_photo }}" alt="{{ event.title }}" />
          </a>
        </div>
      {% endfor %}
    </div>
  </header>
</div> -->

<header class="masthead text-center">
    <h1>Gallery</h1>
  </header>
  <br>

<div class="content list">
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
</div>
