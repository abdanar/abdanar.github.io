---
layout: page
permalink: /blog/
title: blog
nav: true
nav_order: 4

pagination:
  enabled: true
  collection: blog
  per_page: 20
  permalink: /blog/page/:num/
  sort_field: date
  sort_reverse: true
---

{% for post in paginator.posts %}
  <div class="blog-link">
    <span class="blog-date">
      {{ post.date | date: "%Y-%m-%d" }}
    </span>

    <a href="{{ post.url | relative_url }}">
      {{ post.title }}
    </a>
  </div>
{% endfor %}