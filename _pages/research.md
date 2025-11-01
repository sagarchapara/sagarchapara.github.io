---
layout: default
title: "Research Notes"
permalink: /research/
---

<p>Dive into focused references and experiment logs from my research notebooks.</p>

<ul class="post-list">
  {% assign research_entries = site.research | sort: 'title' %}
  {% for entry in research_entries %}
    <li>
      <h3><a class="post-link" href="{{ entry.url | relative_url }}">{{ entry.title }}</a></h3>
      {% if entry.excerpt %}
        <p>{{ entry.excerpt | strip_html | truncate: 160 }}</p>
      {% endif %}
    </li>
  {% endfor %}
</ul>
