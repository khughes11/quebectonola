---
layout: page
title: "All Posts"
description: "Complete archive of all posts, articles, and content from across the Quebec to NOLA trail documentation site"
---

This page contains a complete archive of all posts, articles, and content from across the Quebec to NOLA trail documentation site, organized by type and date.

## All Content

{% assign all_posts = "" | split: "" %}
{% assign all_posts = all_posts | concat: site.historical | concat: site.modern | concat: site.photos | concat: site.references | sort: "date" | reverse %}

{% for post in all_posts %}
  <div class="post-item {{ post.collection }}">
    <div class="post-meta">
      <span class="post-type">{{ post.collection | capitalize }}</span>
      {% if post.date %}
        <span class="post-date">{{ post.date | date: "%B %d, %Y" }}</span>
      {% endif %}
      {% if post.sections %}
        <span class="post-sections">
          Sections: 
          {% for section in post.sections %}
            <a href="/sections/{{ section }}/">{{ section | capitalize }}</a>
            {% unless forloop.last %}, {% endunless %}
          {% endfor %}
        </span>
      {% endif %}
      {% if post.tags %}
        <span class="post-tags">
          {% for tag in post.tags %}
            <span class="tag">{{ tag }}</span>
          {% endfor %}
        </span>
      {% endif %}
    </div>
    <div class="post-content">
      <h3><a href="{{ post.url }}">{{ post.title }}</a></h3>
      <p>{{ post.excerpt | default: post.description | truncate: 200 }}</p>
    </div>
  </div>
{% endfor %}

{% if all_posts.size == 0 %}
  <div class="no-content">
    <p>No content has been documented yet.</p>
  </div>
{% endif %}

