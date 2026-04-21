---
layout: page
title: Illustration
permalink: /illustration/
---

<h2 class="section-title">Illustration Work</h2>

<div class="project-grid">
  {% assign illustrations = site.projects | where: "category", "illustration" %}

  {% for project in illustrations %}
  <a href="{{ project.url }}" class="project-card">
    <div class="project-img placeholder"></div>
    <h3>{{ project.title }}</h3>
    <p>{{ project.description }}</p>
  </a>
  {% endfor %}
</div>
