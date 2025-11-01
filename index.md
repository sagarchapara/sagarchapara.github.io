---
layout: default
title: Home
---

<div class="home-intro">
  <p>Welcome to my machine learning lab notebook and writing corner. I publish deep dives into the math, code walkthroughs, and
  opinion pieces on how we can deploy ML responsibly.</p>
</div>

<p>You can browse the latest posts below or jump straight into one of these sections:</p>

<div class="home-quick-links">
  <a class="btn" href="/blog/">📚 Blog</a>
  <a class="btn" href="/about/">👋 About</a>
  <a class="btn" href="/projects/">🛠️ Projects</a>
  <a class="btn" href="/research/">🧪 Research Notes</a>
</div>

<h2>Latest posts</h2>
<ul class="post-list">
  {% for post in site.posts limit:5 %}
    <li>
      <span class="post-meta">{{ post.date | date: "%B %d, %Y" }}</span>
      <h3>
        <a class="post-link" href="{{ post.url | relative_url }}">{{ post.title }}</a>
      </h3>
      {% if post.excerpt %}
        <p>{{ post.excerpt | strip_html | truncate: 140 }}</p>
      {% endif %}
    </li>
  {% endfor %}
</ul>
