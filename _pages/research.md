---
permalink: /research/
title: "Research"
excerpt: "Data-driven digital twins for anticipating critical transitions."
---

Data-driven digital twins for anticipating critical transitions.

{% assign projects = site.projects | sort: "importance" %}
{% for project in projects %}
<div class="research-item">
  <h2><a href="{{ project.url | relative_url }}">{{ project.title }}</a></h2>
  <p class="research-item__desc">{{ project.description }}</p>
</div>
{% endfor %}
