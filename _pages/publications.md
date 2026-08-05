---
title: Publications
heading: Publications
layout: page
eyebrow: Research output
intro: Selected highlights followed by the complete publication list included in this repository.
permalink: /publications/
---

{% assign sorted_publist = site.data.publist | sort: "year" | reverse %}

<section class="publication-section">
  <div class="section-heading section-heading--stacked">
    <p class="eyebrow">Highlights</p>
    <h2>Representative publications</h2>
  </div>

  <div class="publication-highlight-grid">
    {% assign number_printed = 0 %}
    {% for publi in sorted_publist %}
      {% if publi.highlight == 1 and number_printed < 3 %}
      <article class="publication-highlight-card">
        {% if publi.image %}
        <a class="publication-highlight-card__image" href="{{ publi.link.url }}" target="_blank" rel="noopener">
          <img src="{{ '/images/pubpic/' | append: publi.image | relative_url }}" alt="">
        </a>
        {% endif %}
        <div class="publication-highlight-card__body">
          <h3><a href="{{ publi.link.url }}" target="_blank" rel="noopener">{{ publi.title }}</a></h3>
          {% if publi.description %}<p>{{ publi.description | strip_html | truncate: 220 }}</p>{% endif %}
          <p class="publication-authors">{{ publi.authors }}</p>
          <p class="publication-venue">{{ publi.link.display }}</p>
        </div>
      </article>
      {% assign number_printed = number_printed | plus: 1 %}
      {% endif %}
    {% endfor %}
  </div>
</section>

<section class="publication-section" id="full-list-of-publications">
  <div class="section-heading section-heading--stacked">
    <p class="eyebrow">Archive</p>
    <h2>Selected publication list</h2>
  </div>

  <div class="publication-list">
    {% for publi in sorted_publist %}
    <article class="publication-row">
      <div class="publication-row__number">{{ forloop.index }}</div>
      <div>
        <h3><a href="{{ publi.link.url }}" target="_blank" rel="noopener">{{ publi.title }}</a></h3>
        <p class="publication-authors">{{ publi.authors }}</p>
        <p class="publication-venue">{{ publi.link.display }}</p>
      </div>
    </article>
    {% endfor %}
  </div>
</section>
