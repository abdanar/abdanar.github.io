---
layout: page
permalink: /teaching/
title: teaching
nav: true
nav_order: 3
---

{% assign courses = site.teaching | where_exp: "course", "course.listed != false" | sort: "order" %}

{% for course in courses %}
  <div class="teaching-link">
    <span class="course-code">
      {{ course.code }}
    </span>

    <a href="{{ course.url | relative_url }}">
      {{ course.title }}
    </a>
  </div>
{% endfor %}