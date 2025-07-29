---
layout: page
permalink: /members/
title: Mint Lab
description:
nav: true
nav_order: 2
display_categories: [Faculty, Ph.D., Master, Undergraduate, Alumni]
horizontal: true
---
<h1 class="post-title">
  <a href="https://github.com/Multimodal-Intelligence-Lab" target="_blank" rel="noopener" style="color: inherit; text-decoration: none;">
    <span class="mint-green" style="font-weight: bold;">M</span>ultimodal 
    <span class="mint-green" style="font-weight: bold;">Int</span>elligence Lab
    <i class="fas fa-leaf mint-green"></i>
  </a>
</h1>


<p class="post-description">Research Lab @ SDSU focused on Scientific Knowledge Discovery from Large-Scale Multimodal Data</p>
<!-- pages/members.md -->
<div class="members">
<!-- Display categorized members -->
{%- for category in page.display_categories %}
<h2 class="category">{{ category }}</h2>
{%- assign categorized_members = site.members | where: "category", category -%}
{%- assign sorted_members = categorized_members | sort: "importance" %}
<!-- Generate cards for each member -->
<div >
  {%- for member in sorted_members -%}
    {% include members.html member=member %}
  {%- endfor -%}
</div>
{% endfor %}
</div>

