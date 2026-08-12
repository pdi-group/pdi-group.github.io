---
title: Home
layout: homelay
excerpt: Research group homepage.
permalink: /
body_class: home-page
---

<section class="home-hero">
  <div class="site-shell home-hero__grid">
    <div class="home-hero__copy">
      <p class="eyebrow">{{ site.department }} · {{ site.institution }}</p>
      <h2>Exploring the future of integrated photonics.</h2>
      <p class="home-hero__lead">We explore III-V optoelectronic devices, photonic integration, nanophotonics, and silicon photonics for communication, computing, sensing, and emerging fields.</p>
      <div class="button-row">
        <a class="button button--primary" href="{{ '/research/' | relative_url }}">Explore our research</a>
        <a class="button button--ghost" href="{{ '/openings/' | relative_url }}">Join the group</a>
      </div>
    </div>
    <figure class="home-hero__media">
      <img src="{{ '/images/respic/wafer.png' | relative_url }}" alt="Research laboratory">
      <figcaption>Devices on wafer.</figcaption>
    </figure>
  </div>
</section>

<section class="section">
  <div class="site-shell">
    <div class="section-heading">
      <div>
        <p class="eyebrow">What we do</p>
        <h2>Research at a glance</h2>
      </div>
      <a class="text-link" href="{{ '/research/' | relative_url }}">View all research <span aria-hidden="true">→</span></a>
    </div>

    <div class="research-card-grid">
      {% for item in site.data.research %}
      <article class="research-card">
        <a class="research-card__image" href="{{ item.link | relative_url }}">
          <img src="{{ item.image | relative_url }}" alt="">
        </a>
        <div class="research-card__body">
          <h3><a href="{{ item.link | relative_url }}">{{ item.title }}</a></h3>
          <p>{{ item.summary }}</p>
          <a class="text-link" href="{{ item.link | relative_url }}">Learn more <span aria-hidden="true">→</span></a>
        </div>
      </article>
      {% endfor %}
    </div>
  </div>
</section>

<section class="section section--tinted">
  <div class="site-shell split-section">
    <div>
      <div class="section-heading section-heading--stacked">
        <p class="eyebrow">Updates</p>
        <h2>Latest news</h2>
      </div>
      <div class="news-list news-list--home">
        {% for article in site.data.news limit: 4 %}
        <article class="news-item">
          <time>{{ article.date }}</time>
          <div>{% include render_news.html headline=article.headline %}</div>
        </article>
        {% endfor %}
      </div>
      <a class="button button--secondary" href="{{ '/news/' | relative_url }}">All news</a>
    </div>

    <aside class="join-panel">
      <p class="eyebrow">Work with us</p>
      <h2>Curious minds are welcome.</h2>
      <p>We welcome enquiries from prospective students, postdoctoral researchers, and collaborators whose interests connect with our work.</p>
      <a class="button button--light" href="{{ '/openings/' | relative_url }}">See openings</a>
    </aside>
  </div>
</section>

<section class="section">
  <div class="site-shell">
    <div class="section-heading">
      <div>
        <p class="eyebrow">Selected work</p>
        <h2>Featured publications</h2>
      </div>
      <a class="text-link" href="{{ '/publications/' | relative_url }}">Full publication list <span aria-hidden="true">→</span></a>
    </div>

    <div class="featured-publications">
      {% assign featured_count = 0 %}
      {% for publi in site.data.publist %}
        {% if publi.highlight == 1 and featured_count < 3 %}
        <article class="featured-publication">
          {% if publi.image %}
          <img src="{{ '/images/pubpic/' | append: publi.image | relative_url }}" alt="">
          {% endif %}
          <div>
            <h3><a href="{{ publi.link.url }}" target="_blank" rel="noopener">{{ publi.title }}</a></h3>
            <p class="publication-authors">{{ publi.authors }}</p>
            <p class="publication-venue">{{ publi.link.display }}</p>
          </div>
        </article>
        {% assign featured_count = featured_count | plus: 1 %}
        {% endif %}
      {% endfor %}
    </div>
  </div>
</section>

<section class="photo-band">
  <img src="{{ '/images/bg.png' | relative_url }}" alt="Group members">
  <div class="photo-band__overlay">
    <div class="site-shell">
      <p class="eyebrow">People make the science</p>
      <h2>Meet the team behind the work.</h2>
      <a class="button button--light" href="{{ '/team/' | relative_url }}">Our team</a>
    </div>
  </div>
</section>
