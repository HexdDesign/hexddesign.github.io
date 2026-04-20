---
layout: page
title: Projects
permalink: /projects/
---

<h2 class="section-title">Graphic Design</h2>
<div class="project-grid">
  {% assign design = site.projects | where: "category", "design" %}
  {% for project in design %}
  <a href="{{ project.url }}" class="project-card">
    <div class="project-img placeholder"></div>
    <h3>{{ project.title }}</h3>
    <p>{{ project.description }}</p>
  </a>
  {% endfor %}
</div>

<h2 class="section-title">Arch Ricing</h2>
<div class="project-grid">
  {% assign rices = site.projects | where: "category", "rice" %}
  {% for project in rices %}
  <a href="{{ project.url }}" class="project-card">
    <div class="project-img placeholder"></div>
    <h3>{{ project.title }}</h3>
    <p>{{ project.description }}</p>
  </a>
  {% endfor %}
</div>

<h2 class="section-title">Illustration</h2>
<div class="project-grid">
  {% assign illustration = site.projects | where: "category", "illustration" %}
  {% for project in illustration %}
  <a href="{{ project.url }}" class="project-card">
    <div class="project-img placeholder"></div>
    <h3>{{ project.title }}</h3>
    <p>{{ project.description }}</p>
  </a>
  {% endfor %}
</div>
