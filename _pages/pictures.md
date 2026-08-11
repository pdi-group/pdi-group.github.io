---
title: Gallery
heading: Gallery
layout: page
eyebrow: Life in the group
intro: Group activities, celebrations, conferences, and moments together.
permalink: /gallery/
---

<div class="gallery-grid">
  {% for pic in site.data.pictures_Leiden %}
  <figure class="gallery-card">
    <div class="gallery-card__image">
      <img
        src="{{ '/images/picpic/Gallery/' | append: pic.image | relative_url }}"
        alt="{{ pic.title }}"
        loading="lazy"
      >
    </div>

    <figcaption class="gallery-card__caption">
      <h2>{{ pic.title }}</h2>

      {% if pic.description and pic.description != "" %}
      <p>{{ pic.description }}</p>
      {% endif %}
    </figcaption>
  </figure>
  {% endfor %}
</div>
