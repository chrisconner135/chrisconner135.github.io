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
  id="custom-gallery-swiper"
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
      <swiper-slide>
        {% include figure.liquid loading="eager" path=relative_path class="img-fluid rounded z-depth-1" %}
      </swiper-slide>
    {% endunless %}
  {% endfor %}

</swiper-container>

<script>
  const swiperEl = document.querySelector('#custom-gallery-swiper');
  
  // Inject custom CSS directly inside Swiper's Shadow DOM
  swiperEl.injectStyles([`
    .swiper-slide {
      display: flex !important;
      justify-content: center !important;
      align-items: center !important;
      height: 100% !important;
    }
    
    .swiper-slide figure,
    .swiper-slide picture,
    .swiper-slide img {
      max-height: 100% !important;
      max-width: 100% !important;
      width: auto !important;
      height: auto !important;
      object-fit: contain !important;
      margin: 0 auto !important;
    }
  `]);

  swiperEl.initialize();
</script>