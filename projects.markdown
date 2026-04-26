---
layout: page
title: PROJECTS
permalink: /projects/
---
<h2 class="section-title">Graphic Design</h2>
<div class="project-grid">
  {% assign design = site.projects | where: "category", "design" %}
  {% for project in design %}
  <a href="{{ project.url }}" class="project-card">
    {% if project.cover %}
    <div class="project-img" style="background-image: url('{{ project.cover }}')"></div>
    {% else %}
    <div class="project-img placeholder"></div>
    {% endif %}
    <h3>{{ project.title }}</h3>
    <p>{{ project.description }}</p>
    {% if project.tags %}
    <div class="project-tags">
      {% for tag in project.tags %}
      <span class="tag">{{ tag }}</span>
      {% endfor %}
    </div>
    {% endif %}
  </a>
  {% endfor %}
</div>

<h2 class="section-title">Arch Ricing</h2>
<div class="project-grid">
  {% assign rice = site.projects | where: "category", "rice" %}
  {% for project in rice %}
  <a href="{{ project.url }}" class="project-card">
    {% if project.cover %}
    <div class="project-img" style="background-image: url('{{ project.cover }}')"></div>
    {% else %}
    <div class="project-img placeholder"></div>
    {% endif %}
    <h3>{{ project.title }}</h3>
    <p>{{ project.description }}</p>
    {% if project.tags %}
    <div class="project-tags">
      {% for tag in project.tags %}
      <span class="tag">{{ tag }}</span>
      {% endfor %}
    </div>
    {% endif %}
  </a>
  {% endfor %}
</div>

<h2 class="section-title">Illustration</h2>
<div class="project-grid">
  {% assign illustration = site.projects | where: "category", "illustration" %}
  {% for project in illustration %}
  <a href="{{ project.url }}" class="project-card">
    {% if project.cover %}
    <div class="project-img" style="background-image: url('{{ project.cover }}')"></div>
    {% else %}
    <div class="project-img placeholder"></div>
    {% endif %}
    <h3>{{ project.title }}</h3>
    <p>{{ project.description }}</p>
    {% if project.tags %}
    <div class="project-tags">
      {% for tag in project.tags %}
      <span class="tag">{{ tag }}</span>
      {% endfor %}
    </div>
    {% endif %}
  </a>
  {% endfor %}
</div>





