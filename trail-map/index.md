---
layout: page
title: "Trail Map"
description: "Interactive map showing the complete Quebec to NOLA trail route and key points of interest"
---

This interactive map shows the complete route of the Quebec to NOLA trail, including all documented sections, historical sites, and points of interest.

## Map Overview

<div class="map-container">
  <div class="map-placeholder">
    <p>Interactive map would be embedded here</p>
    <p>This could integrate with Google Maps, Leaflet, or another mapping service</p>
  </div>
</div>

## Trail Sections

{% assign sections = site.section_content | group_by: "section" %}
{% for section_group in sections %}
  {% assign section_name = section_group.name %}
  <div class="map-section">
    <h3>{{ section_name | capitalize }}</h3>
    <p>Key features and points of interest in this section:</p>
    <ul>
      {% for content in section_group.items %}
        <li><a href="{{ content.url }}">{{ content.title }}</a></li>
      {% endfor %}
    </ul>
  </div>
{% endfor %}

## Historical Sites

{% for event in site.historical_events %}
  <div class="historical-site">
    <h3>{{ event.title }}</h3>
    <p>{{ event.description | default: event.excerpt }}</p>
    {% if event.sections %}
      <p>Located in: 
        {% for section in event.sections %}
          <a href="{{ '/sections/' | relative_url }}{{ section }}/">{{ section | capitalize }}</a>
          {% unless forloop.last %}, {% endunless %}
        {% endfor %}
      </p>
    {% endif %}
  </div>
{% endfor %}
