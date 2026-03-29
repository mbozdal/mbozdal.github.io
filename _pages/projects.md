---
layout: default
title: "Projects"
permalink: /projects/
---

# Projects

{% assign sorted_projects = site.projects | reverse %}
{% for project in sorted_projects %}
  <div class="card card-has-link">
    <a href="{{ project.url }}" class="card-link-overlay" aria-label="View project: {{ project.title }}"></a>
    <h2>{{ project.title }}</h2>
    {% if project.duration %}
    <p><strong>Duration:</strong> {{ project.duration }}</p>
    {% endif %}
    {% if project.team %}
    <p><strong>Team:</strong> {{ project.team }}</p>
    {% endif %}
    {% if project.funding %}
    <p><strong>Funding:</strong> {{ project.funding }}</p>
    {% endif %}
    {% unless project.duration or project.team or project.funding %}
    <p>{{ project.content | strip_html | truncatewords: 30, '...' }}</p>
    {% endunless %}
  </div>
{% endfor %} 