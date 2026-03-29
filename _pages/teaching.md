---
layout: default
title: "Teaching"
permalink: /teaching/
---

# Teaching

<div class="card" style="text-align:center; padding: 50px 20px; border-style: dashed;">
  <div style="font-size: 3rem; margin-bottom: 20px;">🚧</div>
  <h2 style="border:none; margin-bottom: 10px;">Under Construction</h2>
  <p style="color: #64748b; font-size: 1.1rem;">This section is currently being updated. Course materials for **Embedded Systems** and other lectures will be available here soon.</p>
</div>

{% comment %}
{% if site.courses and site.courses.size > 0 %}
{% for course in site.courses %}
  <div class="card card-has-link">
    <a href="{{ course.url }}" class="card-link-overlay" aria-label="View course: {{ course.title }}"></a>
    <h2>{{ course.title }}</h2>
    {% if course.code %}
    <p><strong>Course Code:</strong> {{ course.code }}</p>
    {% endif %}
    {% if course.term %}
    <p><strong>Term:</strong> {{ course.term }}</p>
    {% endif %}
    {% if course.level %}
    <p><strong>Level:</strong> {{ course.level }}</p>
    {% endif %}
  </div>
{% endfor %}
{% else %}
<div style="text-align:center; color:#aaa; font-size:1.3em; margin: 3em 0;">🚧 This page is under construction 🚧</div>
{% endif %}
{% endcomment %}