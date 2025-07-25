---
layout: page
permalink: /members/
title: Members
description:
nav: true
nav_order: 2
display_categories: [Current, Alumni]
horizontal: true
---
<div class="members">
{%- if site.enable_project_categories and page.display_categories %}
  {%- for category in page.display_categories %}
    <h2 class="category">{{ category }}</h2>
    {%- assign categorized_members = site.members | where: "category", category -%}
    {%- assign sorted_members = categorized_members | sort: "importance" %}
    <div class="grid">
      {%- for member in sorted_members -%}
        {% include members.html member=member %}
      {%- endfor -%}
    </div>
  {% endfor %}
{%- else -%}
  {%- assign sorted_members = site.members | sort: "importance" -%}
  <div class="grid">
    {%- for member in sorted_members -%}
      {% include members.html member=member %}
    {%- endfor %}
  </div>
{%- endif -%}
</div>

