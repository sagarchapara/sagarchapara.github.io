---
layout: page
permalink: /blog/
title: "Blog"
excerpt: "Latest research notes, experiments, and tutorials."
---

<p>Welcome to the archive of my machine learning writing. Use the links below to explore topics like optimization, diffusion models, and evaluation methodology.</p>

<ul class="post-list">
  {% for post in site.posts %}
    <li>
      <span class="post-meta">{{ post.date | date: "%B %d, %Y" }}</span>
      <h3>
        <a class="post-link" href="{{ post.url | relative_url }}">{{ post.title }}</a>
      </h3>
      {% if post.excerpt %}
        <p>{{ post.excerpt | strip_html | truncate: 160 }}</p>
      {% endif %}
    </li>
  {% endfor %}
</ul>
