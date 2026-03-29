---
layout: default
title: "Courses"
permalink: /courses/
---

# Courses

## Current Courses

{% assign current_courses = site.courses | where: "status", "current" %}
{% for course in current_courses %}
<div class="card">
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
  {{ course.excerpt }}
  <a href="{{ course.url }}" class="btn">View Course Details</a>
</div>
{% endfor %}

## Past Courses

{% assign past_courses = site.courses | where: "status", "past" %}
{% for course in past_courses %}
<div class="card">
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
  {{ course.excerpt }}
  <a href="{{ course.url }}" class="btn">View Course Details</a>
</div>
{% endfor %} 