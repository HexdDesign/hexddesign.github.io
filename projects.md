---
layout: page
title: Portfolio
permalink: /projects/
---

<section class="portfolio-hero">
  <h1>Selected Work</h1>
  <p>Design, UI, Linux customization, Illustration</p>
</section>

<div class="filter-bar">
  <button onclick="filterSelection('all')">All</button>
  <button onclick="filterSelection('design')">Graphic Design</button>
  <button onclick="filterSelection('rice')">Arch Ricing</button>
  <button onclick="filterSelection('illustration')">Illustration</button>
</div>

<div class="portfolio-grid">

{% for project in site.projects %}
<a href="{{ project.url }}" class="portfolio-card filter-item {{ project.category }}">
  
  <img src="{{ project.cover }}" alt="{{ project.title }}">
  
  <div class="portfolio-info">
    <span>{{ project.category }}</span>
    <h3>{{ project.title }}</h3>
    <p>{{ project.description }}</p>
  </div>

</a>
{% endfor %}

</div>

<script>
function filterSelection(category) {
  let cards = document.getElementsByClassName("filter-item");

  for (let i = 0; i < cards.length; i++) {
    cards[i].style.display =
      (category === "all" || cards[i].classList.contains(category))
      ? "block"
      : "none";
  }
}
</script>
