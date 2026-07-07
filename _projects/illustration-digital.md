---
layout: project
title: Digital
description: Digital illustrations
category: illustration
tags: [Illustration, Drawing, Sketching, Digital] 
cover: /assets/images/17.png
---

<p class="project-intro">
  Includes all my digital illustrations.
</p>
<div class="project-gallery-grid">
  <div class="project-card gallery-trigger" data-gallery="digital-illustrations">
    <div class="project-img" style="background-image: url('/assets/images/5.png')"></div>
    <h3>Digital-Illustrations</h3>
    <p>Misc Digital Illustrations - such as my own character work, sketches, and digital paintings. </p>
  </div>
  <div class="project-card gallery-trigger" data-gallery="fan-art">
    <div class="project-img" style="background-image: url('/assets/images/fanart/IMG_1024.png')"></div>
    <h3>Fan-Art</h3>
    <p>All of my digital fan art work. </p>
  </div>
</div>

<!-- Gallery image data  -->

<div class="gallery-data"
data-name="digital-illustrations"
data-images='[
  "/assets/images/1.PNG",  
  "/assets/images/2.JPG",
  "/assets/images/3.jpg",
  "/assets/images/4.PNG",
  "/assets/images/5.png",
  "/assets/images/6.PNG",
  "/assets/images/7.JPG",
  "/assets/images/8.jpg",
  "/assets/images/9.jpg",
  "/assets/images/10.jpg",
  "/assets/images/11.jpg",
  "/assets/images/12.jpg",
  "/assets/images/13.jpg",
  "/assets/images/14.png",
  "/assets/images/15.png",
  "/assets/images/16.png",
  "/assets/images/17.png"
  ]'>
</div>

<div class="gallery-data"
data-name="fan-art"
data-images='[
  "assets/images/fanart/IMG_1035.png",
  "assets/images/fanart/IMG_1034.png",
  "assets/images/fanart/IMG_1032.png",
  "assets/images/fanart/IMG_1031.png",
  "assets/images/fanart/IMG_1029.png",
  "assets/images/fanart/IMG_1027.png",
  "assets/images/fanart/IMG_1026.png",
  "assets/images/fanart/IMG_1024.png",
  "assets/images/fanart/IMG_1022.png",
  "assets/images/fanart/IMG_1020.png",
  "assets/images/fanart/IMG_1018.png",
  "assets/images/fanart/IMG_1017.png",
  "assets/images/fanart/IMG_1016.png",
  "assets/images/fanart/IMG_1015.png",
  "assets/images/fanart/IMG_1014.png",
  "assets/images/fanart/IMG_1013.png",
  "assets/images/fanart/IMG_1011.png",
  "assets/images/fanart/IMG_1008.png",
  "assets/images/fanart/IMG_1007.png",
  "assets/images/fanart/IMG_1005.png"
]'>
</div>


<!-- Lightbox -->
<div class="lightbox" id="lightbox">
  <button class="lightbox-close" id="lightbox-close">&times;</button>
  <button class="lightbox-prev" id="lightbox-prev">&#8592;</button>
  <img class="lightbox-img" id="lightbox-img" src="" alt="" />
  <button class="lightbox-next" id="lightbox-next">&#8594;</button>
  <div class="lightbox-counter" id="lightbox-counter"></div>
</div>

<script>
  const lightbox = document.getElementById('lightbox');
  const lightboxImg = document.getElementById('lightbox-img');
  const counter = document.getElementById('lightbox-counter');
  let currentImages = [];
  let currentIndex = 0;

  function openLightbox(images, index) {
    currentImages = images;
    currentIndex = index;
    showImage();
    lightbox.classList.add('active');
    document.body.style.overflow = 'hidden';
  }

  function closeLightbox() {
    lightbox.classList.remove('active');
    document.body.style.overflow = '';
  }

  function showImage() {
    lightboxImg.src = currentImages[currentIndex];
    counter.textContent = (currentIndex + 1) + ' / ' + currentImages.length;
  }

  document.querySelectorAll('.gallery-trigger').forEach(function(card) {
    card.addEventListener('click', function() {
      var name = card.dataset.gallery;
      var dataEl = document.querySelector('.gallery-data[data-name="' + name + '"]');
      var images = JSON.parse(dataEl.dataset.images);
      openLightbox(images, 0);
    });
  });

  document.getElementById('lightbox-close').addEventListener('click', closeLightbox);

  document.getElementById('lightbox-prev').addEventListener('click', function() {
    currentIndex = (currentIndex - 1 + currentImages.length) % currentImages.length;
    showImage();
  });

  document.getElementById('lightbox-next').addEventListener('click', function() {
    currentIndex = (currentIndex + 1) % currentImages.length;
    showImage();
  });

  lightbox.addEventListener('click', function(e) {
    if (e.target === lightbox) closeLightbox();
  });

  document.addEventListener('keydown', function(e) {
    if (!lightbox.classList.contains('active')) return;
    if (e.key === 'ArrowRight') { currentIndex = (currentIndex + 1) % currentImages.length; showImage(); }
    if (e.key === 'ArrowLeft') { currentIndex = (currentIndex - 1 + currentImages.length) % currentImages.length; showImage(); }
    if (e.key === 'Escape') closeLightbox();
  });
  </script>
