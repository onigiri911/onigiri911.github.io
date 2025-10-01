---
permalink: /projects/
title: "Projects"
author_profile: true
---

{% include base_path %}

{% assign projects = site.data.projects | default: empty %}
{% if projects and projects.size > 0 %}
<ul class="projects-list">
  {% for project in projects %}
  <li>
    {% if project.url %}
      <a href="{{ project.url | relative_url }}">{{ project.title | default: project.name }}</a>
    {% else %}
      {{ project.title | default: project.name }}
    {% endif %}
    {% if project.description %}
      <p>{{ project.description }}</p>
    {% endif %}
  </li>
  {% endfor %}
</ul>
{% else %}
<p>No projects listed yet.</p>
{% endif %}

