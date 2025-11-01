---
layout: default
permalink: /blog/
title: "Blog"
excerpt: "Latest research notes, experiments, and tutorials."
---

Welcome to the archive of my machine learning writing. Use the links below to explore topics like optimization, diffusion models, and evaluation methodology.

<ul class="post-list">
  {% for post in site.posts %}
    <li class="post-list-item">
      <span class="post-meta">{{ post.date | date: "%B %d, %Y" }}</span>
      <h3 class="post-list-title">
        <a class="post-link" href="{{ post.url | relative_url }}">{{ post.title }}</a>
      </h3>
      {% assign author_names = "" %}
      {% if post.authors %}
        {% assign author_names = post.authors | array_to_sentence_string %}
      {% elsif post.author and post.author.name %}
        {% assign author_names = post.author.name %}
      {% elsif post.author %}
        {% assign author_names = post.author %}
      {% elsif site.author and site.author.name %}
        {% assign author_names = site.author.name %}
      {% endif %}
      {% if author_names != "" %}
      <p class="post-meta post-meta-authors">By {{ author_names | escape }}</p>
      {% endif %}
      {% if post.excerpt %}
        <p>{{ post.excerpt | strip_html | truncate: 160 }}</p>
      {% endif %}
    </li>
  {% endfor %}
</ul>
