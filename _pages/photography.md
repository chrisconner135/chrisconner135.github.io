---
layout: page
permalink: /photography/
title: photo gallery
nav: false
nav_order: 3
description: 
images:
  slider: true
---

<!-- <style>
  .post-title, .page-heading {
    display: none;
  }
</style> -->

<swiper-container
  keyboard="true"
  navigation="true"
  pagination="true"
  pagination-clickable="true"
  pagination-dynamic-bullets="true"
  rewind="true"
  autoplay-delay="3000"
  autoplay-disable-on-interaction="false"
  style="height: 500px;">
  {% assign lab_images = site.static_files | where_exp: "item", "item.path contains '/assets/img/gallery/lab/'" %}
  {% for file in lab_images %}
    {% unless file.extname == '.webp' %}
      {% assign relative_path = file.path | remove_first: '/' %}
      <swiper-slide style="display: flex; justify-content: center; align-items: center;">
        {% include figure.liquid
          loading="eager"
          path=relative_path
          class="img-fluid rounded z-depth-1"
          style="max-height: 100%; width: auto; object-fit: contain;" %}
      </swiper-slide>
    {% endunless %}
  {% endfor %}
</swiper-container>