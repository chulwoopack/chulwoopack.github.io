---
layout: page
permalink: /projects/
title: Projects
description:
nav: true
nav_order: 2
display_categories: [Active, Completed]
---

<!-- pages/projects.md -->
<div class="projects">
{%- if site.enable_project_categories and page.display_categories %}
  <!-- Display categorized projects -->
  {%- for category in page.display_categories %}
  <h2 class="category">{{ category }}</h2>
  {%- assign categorized_projects = site.projects | where: "category", category -%}
  {%- assign sorted_projects = categorized_projects | sort: "importance" %}
  <!-- Generate cards for each project -->
  <div class="row row-cols1 row-cols-md-2">
  {%- for project in sorted_projects -%}
    {% include projects.html %}
  {%- endfor %}
  </div>
  {% endfor %}
{%- else -%}
<!-- Display projects without categories -->
  {%- assign sorted_projects = site.projects | sort: "importance" -%}
  <!-- Generate cards for each project -->
  <div class="row row-cols1 row-cols-md-2">
  {%- for project in sorted_projects -%}
    {% include projects.html %}
  {%- endfor %}
  </div>
{%- endif -%}
</div>
