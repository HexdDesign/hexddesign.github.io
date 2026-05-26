---
layout: project
title: Codepen.io
description: My Codepen.io HTML + CSS Sandbox Projects
category: rice
tags: [linux, coding, programming, html, css] 
cover: /assets/images/codepen/codependesktop01.jpg
---

<p class="project-intro">
  My Codepen.io - A collection of my sandbox projects that are primarily HTML, CSS, and Javascript. <br> 
  <a href="https://codepen.io/Hexddesign" target="_blank">Click to browse my Codepen projects.</a><br><br>
</p>
<div class="project-gallery-grid">
  <div class="project-card gallery-trigger" data-gallery="brand-colors">
    <div class="project-img" style="background-image: url('/assets/images/codepen/codependesktop01.jpg')"></div>
    <h3>Brand Colors</h3>
    <p>HEXD Brand Color Pallette. [Click here to see live deployment](https://helpful-morning-mole.codepen.app) </p>
  </div> 
<div class="project-gallery-grid">
  <div class="project-card gallery-trigger" data-gallery="social-buttons">
    <div class="project-img" style="background-image: url('/assets/images/codepen/codepensocialbuttons01.jpg')"></div>
    <h3>Social Buttons</h3>
    <p>Social Media Buttons with Animation. [Click here to see live deployment](https://concise-unit-dingo.codepen.app) </p>
  </div>
</div>

<!-- Gallery image data  -->

<div class="gallery-data"
data-name="brand-colors"
data-images='[
"/assets/images/codepen/codependesktop01.jpg",
"/assets/images/codepen/codependesktop02.jpg",
"/assets/images/codepen/codependesktop03.jpg",
"/assets/images/codepen/codepenmobile01.jpg",
"/assets/images/codepen/codepenmobile02.jpg",
"/assets/images/codepen/codepenmobile03.jpg"
]'></div>

<div class="gallery-data"
data-name="social-buttons"
data-images='[
"/assets/images/codepen/codepensocialbuttons01.jpg",
"/assets/images/codepen/codepensocialbuttons02.jpg",
"/assets/images/codepen/codepensocialbuttons03.jpg"
]'></div>


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
