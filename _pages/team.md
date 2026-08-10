---
title: Team
heading: Team
layout: page
eyebrow: Our people
permalink: /team/
---

{% assign pi = site.data.pi %}

<div class="team-page">

  <!-- Principal Investigator -->
  <section class="team-section">

    <div class="section-heading section-heading--stacked">
      <p class="eyebrow">Leadership</p>
      <h2>Principal Investigator</h2>
    </div>

    <div class="pi-card-wrap">

      <article class="pi-card">

        <div class="pi-card__photo">
          {% if pi.photo %}
          <img
            src="{{ '/images/teampic/' | append: pi.photo | relative_url }}"
            alt="Portrait of {{ pi.name }}"
          >
          {% else %}
          <div class="pi-card__placeholder">
            {{ pi.name | slice: 0, 1 }}
          </div>
          {% endif %}
        </div>

        <div class="pi-card__body">

          <h2 class="team-card-title">{{ pi.name }}</h2>

          {% if pi.department or pi.university %}
          <div class="pi-card__group">

            {% if pi.position %}
            <p><strong>{{ pi.position }}</strong></p>
            {% endif %}

            {% if pi.department %}
            <p><strong>{{ pi.department }}</strong></p>
            {% endif %}

            {% if pi.university %}
            <p><strong>{{ pi.university }}</strong></p>
            {% endif %}
          </div>
          {% endif %}

          {% if pi.office %}
          <div class="pi-card__group">
            <strong>Office</strong>
            <p>{{ pi.office }}</p>
          </div>
          {% endif %}

          {% if pi.email %}
          <div class="pi-card__group">
            <strong>Email</strong>
            <p>
              <a href="mailto:{{ pi.email }}">{{ pi.email }}</a>
            </p>
          </div>
          {% endif %}

          {% if pi.teaching1 or pi.teaching2 %}
          <div class="pi-card__group">
            <strong>Teaching</strong>

            {% if pi.teaching1 %}
            <p>{{ pi.teaching1 }}</p>
            {% endif %}

            {% if pi.teaching2 %}
            <p>{{ pi.teaching2 }}</p>
            {% endif %}
          </div>
          {% endif %}

        </div>

      </article>

    </div>

  </section>


  <!-- Postgraduate Students -->
  <section class="team-section">

    <div class="section-heading">
      <div>
        <p class="eyebrow">Current members</p>
        <h2>Postgraduate Students</h2>
      </div>

      <a class="text-link" href="{{ '/openings/' | relative_url }}">
        Join us
        <span aria-hidden="true">→</span>
      </a>
    </div>

    <div class="team-grid">

      {% for member in site.data.team_members %}

      <article class="member-card">

        <div class="member-card__photo">
          {% if member.photo %}
          <img
            src="{{ '/images/teampic/' | append: member.photo | relative_url }}"
            alt="Portrait of {{ member.name }}"
          >
          {% else %}
          <div class="member-card__placeholder">
            {{ member.name | slice: 0, 1 }}
          </div>
          {% endif %}
        </div>

        <div class="member-card__body">

          <h3 class="team-card-title">
            {% if member.website %}
            <a href="{{ member.website }}" target="_blank" rel="noopener">
              {{ member.name }}
            </a>
            {% else %}
            {{ member.name }}
            {% endif %}
          </h3>

          {% if member.info %}
          <p class="member-role">{{ member.info }}</p>
          {% endif %}

          {% if member.number_educ and member.number_educ > 0 %}
          <div class="member-education">

            {% for i in (1..member.number_educ) %}
              {% capture education_key %}education{{ i }}{% endcapture %}
              {% assign education_item = member[education_key] %}

              {% if education_item and education_item != "" %}
              <p>{{ education_item }}</p>
              {% endif %}
            {% endfor %}

          </div>
          {% endif %}

          {% if member.email %}
          <a class="member-email" href="mailto:{{ member.email }}">
            {{ member.email }}
          </a>
          {% endif %}

        </div>

      </article>

      {% endfor %}

    </div>

  </section>


  <!-- Master and undergraduate students -->
  {% if site.data.students %}
  <section class="team-section">

    <div class="section-heading section-heading--stacked">
      <p class="eyebrow">Students</p>
      <h2>Master and Undergraduate Students</h2>
    </div>

    <div class="team-grid team-grid--compact">

      {% for member in site.data.students %}

      <article class="member-card member-card--compact">

        <div class="member-card__body">
          <h3 class="team-card-title">{{ member.name }}</h3>

          {% if member.info %}
          <p class="member-role">{{ member.info }}</p>
          {% endif %}

          {% if member.email %}
          <a class="member-email" href="mailto:{{ member.email }}">
            {{ member.email }}
          </a>
          {% endif %}
        </div>

      </article>

      {% endfor %}

    </div>

  </section>
  {% endif %}


  <!-- Alumni -->
  {% if site.data.alumni_members %}
  <section class="team-section">

    <div class="section-heading section-heading--stacked">
      <p class="eyebrow">Former members</p>
      <h2>Alumni</h2>
    </div>

    <div class="alumni-list">

      {% for member in site.data.alumni_members %}

      <article class="alumni-item">
        <h3 class="team-card-title">{{ member.name }}</h3>

        {% if member.duration %}
        <p>{{ member.duration }}</p>
        {% endif %}

        {% if member.info %}
        <span>{{ member.info | strip_html }}</span>
        {% endif %}
      </article>

      {% endfor %}

    </div>

  </section>
  {% endif %}

</div>
