---
layout: project
title: Traditional
description: Traditional Work
category: illustration
tags: [Illustration, Drawing, Sketching, Painting, Crafting] 
cover: /assets/images/traditional/Jax002.jpg
---

<p class="project-intro">
  A collection of all my traditional work. 
</p>
  <div class="project-card gallery-trigger" data-gallery="fan-art">
    <div class="project-img" style="background-image: url('/assets/images/fanart/Jax002.jpg')"></div>
    <h3>Fan-Art</h3>
    <p>All of my traditional fan art work for "The Amazing Digital Circus". </p>
  </div>
  
</div>

<!-- Gallery image data  -->

<div class="gallery-data"
data-name="fan-art"
data-images='[
  "/assets/images/traditional/Jax001.jpg, 
  "/assets/images/traditional/Jax002.jpg, 
  "/assets/images/traditional/Jax003.jpg, 



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
