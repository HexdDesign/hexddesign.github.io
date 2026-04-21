---
layout: page
title: Work
permalink: /projects/
---

<section class="work-header">
  <h1>Work</h1>
  <p>Design, Illustration, Linux setups</p>
</section>

<nav class="work-filters">
  <button onclick="filterSelection('all')">All</button>
  <button onclick="filterSelection('design')">Design</button>
  <button onclick="filterSelection('rice')">Ricing</button>
  <button onclick="filterSelection('illustration')">Illustration</button>
</nav>

<div class="work-grid">

{% for project in site.projects %}

<a href="{{ project.url }}" class="work-card filter-item {{ project.category }}">

  {% if project.cover %}
    <img src="{{ project.cover }}" alt="{{ project.title }}">
  {% endif %}

  <div class="meta">
    <h3>{{ project.title }}</h3>
    <span>{{ project.category }}</span>
  </div>

</a>

{% endfor %}

</div>

<script>
function filterSelection(category){
  let cards = document.getElementsByClassName("filter-item");

  for(let i = 0; i < cards.length; i++){
    cards[i].style.display =
      (category === "all" || cards[i].classList.contains(category))
      ? "block" : "none";
  }
}
</script>
