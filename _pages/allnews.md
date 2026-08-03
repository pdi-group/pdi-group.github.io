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
    <div>{% include render_news.html headline=article.headline %}</div>
  </article>
  {% endfor %}
</div>
