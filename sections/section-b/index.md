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

<h2 id="posts">All Content for Section B</h2>

{% include index-section.html 
  collection_type="all"
  section_filter=page.slug
  title="All Content"
  subtitle="Complete archive of research and updates"
  show_footer=false
%}

<h2>Posts By Theme</h2>

<div class="grid grid-cols-1 lg:grid-cols-2 gap-6">
  {% include index-section.html 
    collection_type="modern"
    section_filter=page.slug
    title="Modern Exploration"
    subtitle="Recent research and field work"
    show_footer=false
  %}

  {% include index-section.html 
    collection_type="historical"
    section_filter=page.slug
    title="Historical Documentation"
    subtitle="Historical research findings"
    show_footer=false
  %}

  {% include index-section.html 
    collection_type="photos"
    section_filter=page.slug
    title="Photo Gallery"
    subtitle="Visual documentation"
    show_footer=false
  %}

  {% include index-section.html 
    collection_type="references"
    section_filter=page.slug
    title="References"
    subtitle="Research sources and documentation"
    show_footer=false
  %}
</div>



