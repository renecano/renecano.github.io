---
layout: page
title: Blog
permalink: /blog/
---

<div class="blog-intro">
  <p class="blog-subtitle">
    Notes and technical write-ups about software, data-driven systems, and IoT projects.
  </p>
</div>

<div class="grid">

{% for post in site.posts %}
  <div class="card">
    <div class="card-title">{{ post.title }}</div>

    <div class="card-meta">
      {{ post.date | date: "%b %d, %Y" }}
    </div>

    <div class="card-text">
      {{ post.excerpt | strip_html | truncate: 160 }}
    </div>

    <div class="card-actions">
      <a class="btn btn-primary" href="{{ post.url }}">Read</a>
    </div>
  </div>
{% endfor %}

</div>

