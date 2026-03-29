---
layout: default
title: "Publications"
permalink: /publications/
---

# Publications

<ul class="publications-list">
{% assign pubs = site.data.publications | sort: "Year" | reverse %}
{% for pub in pubs %}
  <li>
    <strong>{{ pub.Title }}</strong>
    <div class="pub-details">
      {% if pub.Publication %}{{ pub.Publication }}{% endif %}
      {% if pub.Volume %}, Vol. {{ pub.Volume }}{% endif %}
      {% if pub.Number %}, No. {{ pub.Number }}{% endif %}
      {% if pub.Pages %}, pp. {{ pub.Pages }}{% endif %}
      {% if pub.Year %}, {{ pub.Year }}{% endif %}
      {% if pub.Publisher %}, {{ pub.Publisher }}{% endif %}
    </div>
    <div class="pub-authors"><em>{{ pub.Authors }}</em></div>
    <div class="pub-links">
      {% if pub.DOI %}
        <a href="https://doi.org/{{ pub.DOI }}" target="_blank" class="pub-link doi-link">
          <svg viewBox="0 0 24 24" width="14" height="14" fill="currentColor" style="margin-right:4px;"><path d="M3.9 12c0-1.71 1.39-3.1 3.1-3.1h4V7H7c-2.76 0-5 2.24-5 5s2.24 5 5 5h4v-1.9H7c-1.71 0-3.1-1.39-3.1-3.1zM8 13h8v-2H8v2zm9-6h-4v1.9h4c1.71 0 3.1 1.39 3.1 3.1s-1.39 3.1-3.1 3.1h-4V17h4c2.76 0 5-2.24 5-5s-2.24-5-5-5z"/></svg>
          DOI
        </a>
      {% endif %}
      {% if pub.PDF %}
        <a href="/{{ pub.PDF }}" target="_blank" class="pub-link pdf-link">
          <svg viewBox="0 0 24 24" width="14" height="14" fill="currentColor" style="margin-right:4px;"><path d="M20 2H8c-1.1 0-2 .9-2 2v12c0 1.1.9 2 2 2h12c1.1 0 2-.9 2-2V4c0-1.1-.9-2-2-2zm-8.5 7.5c0 .83-.67 1.5-1.5 1.5H9v2H7.5V7H10c.83 0 1.5.67 1.5 1.5v1zm5 2c0 .83-.67 1.5-1.5 1.5h-2.5V7H15c.83 0 1.5.67 1.5 1.5v3zm4-3H19v1h1.5V11H19v2h-1.5V7h3v1.5zM9 10.5V8.5h1v2H9zm5 2V8.5h1v4h-1zM2 6v14c0 1.1.9 2 2 2h14v-2H4V6H2z"/></svg>
          PDF
        </a>
      {% endif %}
    </div>
  </li>
{% endfor %}
</ul>

<style>
.publications-list {
  list-style: none; /* Changed to none for cleaner look */
  padding-left: 0;
}
.publications-list li {
  margin-bottom: 2.5em;
  padding-bottom: 1.5em;
  border-bottom: 1px solid #f1f5f9;
}
.publications-list li:last-child {
  border-bottom: none;
}
.pub-details {
  margin-top: 0.4em;
  margin-bottom: 0.4em;
  color: #64748b;
  font-size: 0.95em;
  line-height: 1.6;
}
.pub-authors {
  margin-top: 0.2em;
  font-size: 0.9em;
  color: #94a3b8;
}
.pub-links {
  margin-top: 12px;
  display: flex;
  gap: 12px;
}
.pub-link {
  display: inline-flex;
  align-items: center;
  padding: 6px 12px;
  border-radius: 6px;
  font-size: 0.85rem;
  font-weight: 500;
  text-decoration: none;
  transition: all 0.2s ease;
}
.doi-link {
  background: #f1f5f9;
  color: #475569;
}
.doi-link:hover {
  background: #e2e8f0;
  color: #1e293b;
}
.pdf-link {
  background: #fef2f2;
  color: #b91c1c;
}
.pdf-link:hover {
  background: #fee2e2;
  color: #991b1b;
}
</style>
