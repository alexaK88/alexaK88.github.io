---
title: Travel
layout: default
---

<div class="travel-hero">
  <h1>Travel</h1>
  <p>Places, paths, and moments worth remembering.</p>
</div>

<div class="travel-grid">
{% for post in site.categories.travel %}
  <a href="{{ post.url }}" class="travel-card">
    {% if post.cover %}
      <img src="{{ post.cover }}" alt="{{ post.title }}">
    {% endif %}
    <div class="travel-card-text">
      <h2>{{ post.title }}</h2>
      <p>{{ post.date | date: "%B %Y" }}</p>
    </div>
  </a>
{% endfor %}
</div>
