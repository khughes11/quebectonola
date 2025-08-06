---
layout: default
title: All Posts
permalink: /posts/
---

# All Posts

<ul>
  {% for doc in site.posts %}
    <li><a href="{{ doc.url }}">{{ doc.title }}</a></li>
  {% endfor %}
</ul>
