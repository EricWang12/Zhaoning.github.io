---
layout: default
title: "More About Me"
permalink: /photos/
---

<article class="post">
  <header class="post-header">
    <h1 class="post-title">More About Me</h1>
  </header>
  <div class="post-content">
    <p><a href="/">&larr; Back</a></p>
    <div class="gallery-grid">
      {% for item in site.data.gallery %}
      <div class="gallery-item{% if item.size == 'full' %} gallery-item--full{% endif %}">
        <img src="{{ '/assets/images/gallery/' | relative_url }}{{ item.image }}" alt="{{ item.caption }}"/>
        <p class="gallery-caption">{{ item.caption }}</p>
      </div>
      {% endfor %}
    </div>
  </div>
</article>
