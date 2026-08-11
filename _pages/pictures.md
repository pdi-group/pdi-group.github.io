---
title: Gallery
heading: Gallery
layout: page
eyebrow: Life in the group
intro: Group activities, celebrations, conferences, and moments together.
permalink: /gallery/
---

<div class="group-gallery">
  {% for pic in site.data.pictures_Leiden %}
  <figure class="group-gallery__item">
    <div class="group-gallery__media">
      <img
        src="{{ '/images/picpic/Gallery/' | append: pic.image | relative_url }}"
        alt="{{ pic.title }}"
        loading="lazy"
      >
    </div>

    <figcaption class="group-gallery__caption">
      <span>{{ pic.title }}</span>
      {% if pic.description and pic.description != "" %}
      <p>{{ pic.description }}</p>
      {% endif %}
    </figcaption>
  </figure>
  {% endfor %}
</div>
