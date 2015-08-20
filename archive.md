---
layout: page
title: Archive
---

{% for post in site.posts %}
  <h2 class="post-title"><a href="{{ post.url }}">{{ post.title }}</a></h2>
  <span class="post-date">{{ post.date | date: "%B %d, %Y" }}</span>
  {% if post.lead %}
  <p>{{ post.lead | strip_html | strip_newlines | truncate: 130 }}</p>
  {% endif %}
{% endfor %}
