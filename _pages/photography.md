---
layout: page
permalink: /photography/
title: photography
nav: true
nav_order: 3
description: 
images:
  slider: true
---

<style>
  .post-title, .page-heading {
    display: none;
  }
</style>

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
  
  {% assign lab_images = site.static_files | where_exp: "item", "item.path contains '/assets/img/gallery/lab/'" | sort: "path" %}
  {% for file in lab_images %}
    {% unless file.extname == '.webp' %}
      {% assign relative_path = file.path | remove_first: '/' %}
      <swiper-slide>
        <div class="swiper-image-wrapper">
          {% include figure.liquid loading="eager" path=relative_path class="img-fluid rounded z-depth-1" %}
        </div>
      </swiper-slide>
    {% endunless %}
  {% endfor %}
</swiper-container>

<style>
  /* Swiper slide alignment */
  swiper-slide {
    display: flex !important;
    justify-content: center !important;
    align-items: center !important;
    height: 100% !important;
  }

  .swiper-image-wrapper {
    height: 100%;
    width: 100%;
    display: flex;
    justify-content: center;
    align-items: center;
  }

  /* Force al-folio's figure wrapper to fit the slider height */
  .swiper-image-wrapper figure {
    height: 100% !important;
    max-height: 500px !important; /* Matches container height */
    margin: 0 !important;
    display: flex !important;
    justify-content: center !important;
    align-items: center !important;
  }

  /* Override img-fluid width:100% on desktop so tall images constrain by height */
  .swiper-image-wrapper picture,
  .swiper-image-wrapper img {
    max-height: 500px !important;
    max-width: 100% !important;
    width: auto !important; /* Overrides Bootstrap img-fluid width: 100% */
    height: auto !important;
    object-fit: contain !important;
  }
</style>