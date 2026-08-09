---
layout: project
title: Niri 
description: Click any theme card to browse screenshots of each project.
category: rice
tags: [linux, coding, programming, ricing, Niri] 
cover: /assets/images/codepen/codependesktop01.jpg
---

<p class="project-intro">
  My Rices for Niri Windows Manager. <br> 
</p>
<div class="project-gallery-grid">
  <div class="project-card gallery-trigger" data-gallery="kitty-terminal">
    <div class="project-img" style="background-image: url('/assets/images/niri/Jax001.png')"></div>
    <h3>Kitty</h3>
    <p>Themes and Configurations for Kitty Terminal Emulator.</p>
  </div> 
</div>
 
<!-- Gallery image data  -->

<div class="gallery-data"
data-name="kitty-terminal"
data-images='[
"/assets/images/niri/Jax001.png"
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
