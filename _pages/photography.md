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
  style="height: 500px;"> <!-- Adjust slider height here -->
  
  {% assign lab_images = site.static_files | where_exp: "item", "item.path contains '/assets/img/gallery/lab/'" %}
  {% for file in lab_images %}
    {% unless file.extname == '.webp' %}
      {% assign relative_path = file.path | remove_first: '/' %}
      <swiper-slide style="display: flex; justify-content: center; align-items: center; height: 100%;">
        <div class="swiper-image-wrapper">
          {% include figure.liquid loading="eager" path=relative_path class="img-fluid rounded z-depth-1" %}
        </div>
      </swiper-slide>
    {% endunless %}
  {% endfor %}

</swiper-container>

<!-- Custom styling to prevent al-folio image cropping -->
<style>
  .swiper-image-wrapper {
    height: 100%;
    width: 100%;
    display: flex;
    justify-content: center;
    align-items: center;
  }

  /* Force al-folio generated figure, picture, and img elements to respect container boundaries */
  .swiper-image-wrapper figure,
  .swiper-image-wrapper picture,
  .swiper-image-wrapper img {
    max-height: 100% !important;
    max-width: 100% !important;
    width: auto !important;
    height: auto !important;
    object-fit: contain !important;
    margin: 0 auto;
  }
</style>