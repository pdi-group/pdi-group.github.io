---
title: Team
heading: Team
layout: page
eyebrow: Our people
intro: Researchers, students, engineers, and collaborators working together across experiment and instrumentation.
permalink: /team/
---

{% assign pi = site.data.pi %}

<div class="team-page">

  <!-- Principal Investigator -->
  <section class="team-section">

    <div class="team-section-title">
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

          <h3>{{ pi.name }}</h3>

          {% if pi.position %}
          <p class="pi-card__position">{{ pi.position }}</p>
          {% endif %}

          {% if pi.department or pi.university %}
          <div class="pi-card__group">
            <strong>Employment</strong>

            {% if pi.position %}
            <p>{{ pi.position }}</p>
            {% endif %}

            {% if pi.department %}
            <p>{{ pi.department }}</p>
            {% endif %}

            {% if pi.university %}
            <p>{{ pi.university }}</p>
            {% endif %}
          </div>
          {% endif %}

          {% if pi.education1 or pi.education2 %}
          <div class="pi-card__group">
            <strong>Education</strong>

            {% if pi.education1 %}
            <p>{{ pi.education1 }}</p>
            {% endif %}

            {% if pi.education2 %}
            <p>{{ pi.education2 }}</p>
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

        </div>

      </article>

    </div>

  </section>


  <!-- Postgraduate Students -->
  <section class="team-section">

    <div class="team-section-title team-section-title--with-link">
      <h2>Postgraduate Students</h2>

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

          <h3>{{ member.name }}</h3>

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

    <div class="team-section-title">
      <h2>Master and Undergraduate Students</h2>
    </div>

    <div class="team-grid team-grid--compact">

      {% for member in site.data.students %}

      <article class="member-card member-card--compact">

        <div class="member-card__body">
          <h3>{{ member.name }}</h3>

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

    <div class="team-section-title">
      <h2>Alumni</h2>
    </div>

    <div class="alumni-list">

      {% for member in site.data.alumni_members %}

      <article class="alumni-item">
        <h3>{{ member.name }}</h3>

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