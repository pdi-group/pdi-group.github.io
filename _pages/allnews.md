---
title: News
heading: News
layout: page
eyebrow: Updates
permalink: /news/
---

<div class="news-archive">
  {% for article in site.data.news %}

  <article class="news-archive__item">

    <time>{{ article.date }}</time>

    <div class="news-archive__content">
      <div class="news-archive__headline">
        {% include render_news.html headline=article.headline %}
      </div>

      {% if article.image and article.image != "" %}
      <img
        class="news-archive__image"
        src="{{ '/images/newspic/' | append: article.image | relative_url }}"
        alt=""
        loading="lazy"
      >
      {% endif %}
    </div>

  </article>

  {% endfor %}
</div>