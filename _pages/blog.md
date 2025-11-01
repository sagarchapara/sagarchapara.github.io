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

<h2>Drafts in progress</h2>
<p>These longer-form write-ups are currently on the bench while I finish experiments and polish the accompanying notebooks.</p>

<ul class="post-list post-list-in-progress">
  <li class="post-list-item">
    <h3>Speculative Decoding Playbooks: Faster Autoregressive Inference</h3>
    <p>Tracing the evolution of speculative decoding strategies, from paired draft-and-verify models to batched tree search, with reproducible benchmarks.</p>
  </li>
  <li class="post-list-item">
    <h3>Precision Alchemy: Mixing Low-Bit Training with QAT</h3>
    <p>Dissecting how mixed precision schedules and quantization-aware training can coexist, including optimizer tweaks and calibration pitfalls.</p>
  </li>
  <li class="post-list-item">
    <h3>Routing the Giants: Building a Production Mixture-of-Experts Stack</h3>
    <p>From router design to load balancing, a deep dive into scalable MoE systems with practical profiling tips.</p>
  </li>
  <li class="post-list-item">
    <h3>Distributed Training from Scratch: Re-deriving DDP, FSDP, and Tensor Parallelism</h3>
    <p>Rebuilding the core distributed training algorithms step by step, illuminating the communication patterns that make them work.</p>
  </li>
</ul>
