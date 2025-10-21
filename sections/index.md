---
layout: page
title: "Trail Sections"
description: "Explore the Quebec to NOLA trail section by section, with detailed documentation for each area"
---

Explore the Quebec to NOLA trail section by section. Each section contains historical documentation, modern exploration, and conservation information.

## Available Sections

{% assign all_sections = "" | split: "" %}
{% for collection in site.collections %}
  {% unless collection.label == "posts" %}
    {% for item in collection.docs %}
      {% if item.sections %}
        {% for section in item.sections %}
          {% unless all_sections contains section %}
            {% assign all_sections = all_sections | push: section %}
          {% endunless %}
        {% endfor %}
      {% endif %}
    {% endfor %}
  {% endunless %}
{% endfor %}

{% for section_name in all_sections %}
  {% assign section_overview = site.pages | where: "slug", section_name | first %}
  
  <div class="section-card">
    <h2><a href="{{ '/sections/' | relative_url }}{{ section_name }}/">{{ section_name | capitalize }}</a></h2>
    {% if section_overview %}
      <p>{{ section_overview.description }}</p>
    {% endif %}
    
    <div class="section-stats">
      {% assign historical_count = site.historical | where_exp: "item", "item.sections contains section_name" | size %}
      {% assign modern_count = site.modern | where_exp: "item", "item.sections contains section_name" | size %}
      {% assign photos_count = site.photos | where_exp: "item", "item.sections contains section_name" | size %}
      {% assign references_count = site.references | where_exp: "item", "item.sections contains section_name" | size %}
      
      <span class="stat">Historical: {{ historical_count }}</span>
      <span class="stat">Modern: {{ modern_count }}</span>
      <span class="stat">Photos: {{ photos_count }}</span>
      <span class="stat">References: {{ references_count }}</span>
    </div>
  </div>
{% endfor %}

{% if all_sections.size == 0 %}
  <div class="no-content">
    <p>No trail sections have been documented yet. Check back soon as we continue to explore and document the trail!</p>
  </div>
{% endif %}

## How Sections Are Organized

Each trail section contains:

- **Historical Documentation**: Events, stories, and archaeological findings specific to that section
- **Modern Exploration**: Current research, discoveries, and exploration efforts
- **Photos**: Visual documentation and galleries
- **References**: Sources and materials related to that section

## Contributing

If you have information about a specific section of the trail, please see our [How to Contribute](/how-to-contribute/) page for guidelines on adding content.
