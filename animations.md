---

layout: splash
title: Animations
classes:
    - landing
    - dark-theme
excerpt: "A Google Earth Engine web application to monitor mountain valley glaciers"
header:
    overlay_image: /assets/images/glacier_header.png
    overlay_filter: 0.1
    
---
<div style="display: flex; flex-wrap: wrap; justify-content: center; gap: 10px; margin-bottom: 10px;">
{% for gif in site.static_files %}
  {% if gif.path contains 'assets/gifs' %}
  <div style="text-align: center; max-width: 400px;">
  <a href="{{ gif.path }}" target="_blank" style="text-decoration: none; color: inherit;"></a>
  <p style="font-size: 14px; color: #555; margin-bottom: 5px;">{{ gif.name | replace: '.gif', '' }}</p>
  <a href="{{ gif.path }}" target="_blank">
  <img src="{{ gif.path }}" alt="{{ gif.name }}" width="100%" style="border-radius: 8px; box-shadow: 2px 2px 10px rgba(0, 0, 0, 0.2);">
  </a>
  </div>
  {% endif %}
{% endfor %}
</div>