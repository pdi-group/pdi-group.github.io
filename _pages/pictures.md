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

    <figcaption class="group-gallery__heading">
      <div class="group-gallery__title">{{ pic.title }}</div>

      {% if pic.description and pic.description != "" %}
      <p class="group-gallery__description">{{ pic.description }}</p>
      {% endif %}
    </figcaption>

    <div class="group-gallery__media">
      <img
        src="{{ '/images/picpic/Gallery/' | append: pic.image | relative_url }}"
        alt="{{ pic.title }}"
        loading="lazy"
      >
    </div>

  </figure>

  {% endfor %}
</div>
