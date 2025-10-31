---
layout: page
title: "Section B - Central Corridor"
slug: section-b
description: "Central stretch of the Quebec to NOLA trail, connecting northern and southern segments."
map: "<div class='map-placeholder'>Interactive map of Section B would go here</div>"
---

# Section B Overview

Section B forms the central corridor of the Quebec to NOLA trail, linking the northern approaches with the southern routes.

## Key Features

- **Connecting Route**: Bridges major segments of the trail
- **Mixed Terrain**: Rolling hills, river crossings, and forested areas
- **Historic Waypoints**: Sites of travel, trade, and settlement

## All Content for Section B

<div class="card">
  <div class="card__header">
    <h3 class="card__title">All Content</h3>
    <p class="card__subtitle">Complete archive of research and updates</p>
  </div>
  <div class="card__content">
    {% assign historical = site.historical | where_exp: "item", "item.sections contains page.slug" %}
    {% assign modern = site.modern | where_exp: "item", "item.sections contains page.slug" %}
    {% assign photos = site.photos | where_exp: "item", "item.sections contains page.slug" %}
    {% assign references = site.references | where_exp: "item", "item.sections contains page.slug" %}

    {% assign all_posts = "" | split: "" %}
    {% assign all_posts = all_posts | concat: historical | concat: modern | concat: photos | concat: references | sort: "date" | reverse %}

    {% if all_posts.size > 0 %}
      {% for post in all_posts %}
        <div class="activity-item">
          <h4><a href="{{ post.url | relative_url }}">{{ post.title }}</a></h4>
          <div class="activity-meta">
            {% if post.date %}
              <span class="tag">{{ post.date | date: "%B %d, %Y" }}</span>
            {% endif %}
            <span class="tag tag--tertiary">{{ post.collection | capitalize }}</span>
            {% if post.sections %}
              {% for section in post.sections %}
                <span class="tag tag--primary">{{ section | capitalize }}</span>
              {% endfor %}
            {% endif %}
            {% if post.tags %}
              {% for tag in post.tags %}
                <span class="tag tag--secondary">{{ tag | capitalize }}</span>
              {% endfor %}
            {% endif %}
          </div>
          {% if post.description %}
            <p class="text-tertiary">{{ post.description }}</p>
          {% elsif post.excerpt %}
            <p class="text-tertiary">{{ post.excerpt | strip_html | truncate: 200 }}</p>
          {% endif %}
        </div>
      {% endfor %}
    {% else %}
      <p class="text-tertiary">No content has been documented for Section B yet. Check back soon as we continue to explore and document the trail!</p>
    {% endif %}
  </div>
</div>



