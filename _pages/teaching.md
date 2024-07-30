---
layout: page
permalink: /teaching/
title: Teaching
description: Materials for courses you taught. Replace this text with your description.
nav: true
nav_order: 6
---

Here are the courses I have taught:

{% for course in site.courses %}
- [{{ course.title }}]({{ course.url }}) - {{ course.description }}
{% endfor %}
