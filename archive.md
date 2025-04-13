---
layout: page
title: Archive
permalink: /archive/
---

<div class="archive-page">
  <h1 class="page-heading">All Articles</h1>

  {% for post in site.posts %}
    {% assign currentdate = post.date | date: "%Y" %}
    {% if currentdate != date %}
      {% unless forloop.first %}</ul>{% endunless %}
      <h2 id="y{{post.date | date: "%Y"}}">{{ currentdate }}</h2>
      <ul class="post-list">
      {% assign date = currentdate %}
    {% endif %}
      <li>
        <span class="post-meta">{{ post.date | date: "%b %-d, %Y" }}</span>
        <h3>
          <a class="post-link" href="{{ post.url | relative_url }}">
            {{ post.title | escape }}
          </a>
        </h3>
      </li>
    {% if forloop.last %}</ul>{% endif %}
  {% endfor %}
</div> 