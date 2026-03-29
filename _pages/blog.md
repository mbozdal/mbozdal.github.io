---
layout: default
title: "Blog"
permalink: /blog/
---

# Blog

{% for post in site.posts %}
  <div class="card card-has-link">
    <a href="{{ post.url }}" class="card-link-overlay" aria-label="Read more about {{ post.title }}"></a>
    <h2>{{ post.title }}</h2>
    <p><small>{{ post.date | date: "%B %d, %Y" }}</small></p>
    <p>{{ post.excerpt }}</p>
  </div>
{% endfor %} 