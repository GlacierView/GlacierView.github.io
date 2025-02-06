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
  {% assign code = gif.path %}
  {% assign glims_e = code | split: "G" | last | split: "E" | first %}
  {% assign glims_n = code | split: "E" | last | split: "N" | first %}{% assign glims_n_first = glims_n | slice: 0, 2 %}
  {% assign glims_n_last = glims_n | slice: -3, 3 %}
  {% assign glims_n_formatted = glims_n_first | append: '.' | append: glims_n_last %}
  {% assign glims_e_first = glims_e | slice: 0, 3 %}
  {% assign glims_e_last = glims_e | slice: -3, 3 %}
  {% assign glims_e_formatted = glims_e_first | append: '.' | append: glims_e_last %}
  <div style="text-align: center; max-width: 400px;">
  <a href="{{ gif.path }}" target="_blank" style="text-decoration: none; color: inherit;"></a>
  <p style="font-size: 14px; color: #555; margin-bottom: 5px;">
  GLIMS ID: {{ gif.name | replace: '.gif', '' | split: "_" | first }} <br>
  <a href="https://earth.google.com/web/@{{ glims_n_formatted | append: ',' | append: glims_e_formatted }},5000a,5000d,35y" target="_blank">Google Earth</a>
  </p>
  <a href="{{ gif.path }}" target="_blank">
  <img src="{{ gif.path }}" alt="{{ gif.name }}" width="100%" style="border-radius: 8px; box-shadow: 2px 2px 10px rgba(0, 0, 0, 0.2);">
  </a>
  </div>
  {% endif %}
{% endfor %}
</div>