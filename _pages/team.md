---
title: Team
heading: Meet the team behind the work.
layout: page
eyebrow: Our people
intro: Our group brings together researchers and students working on photonic devices, integrated optoelectronics, and related technologies.
permalink: /team/
---

{% assign pi = site.data.pi %}

<section class="team-section pi-section">

  <div class="team-section-heading">
    <span>Principal Investigator</span>
  </div>

  <article class="pi-profile">

    <div class="pi-profile__photo">
      <img
        src="{{ '/images/teampic/' | append: pi.photo | relative_url }}"
        alt="Portrait of {{ pi.name }}"
      >
    </div>

    <div class="pi-profile__content">
      <p class="eyebrow">Principal Investigator</p>

      <h2>{{ pi.name }}</h2>

      {% if pi.position %}
      <p class="pi-profile__position">{{ pi.position }}</p>
      {% endif %}

      <div class="pi-profile__affiliation">
        {% if pi.department %}
        <p>{{ pi.department }}</p>
        {% endif %}

        {% if pi.university %}
        <p>{{ pi.university }}</p>
        {% endif %}
      </div>

      <dl class="pi-profile__details">

        {% if pi.office %}
        <div>
          <dt>Office</dt>
          <dd>{{ pi.office }}</dd>
        </div>
        {% endif %}

        {% if pi.email %}
        <div>
          <dt>Email</dt>
          <dd>
            <a href="mailto:{{ pi.email }}">{{ pi.email }}</a>
          </dd>
        </div>
        {% endif %}

        {% if pi.phone and pi.phone != "" %}
        <div>
          <dt>Phone</dt>
          <dd>{{ pi.phone }}</dd>
        </div>
        {% endif %}

      </dl>
    </div>

  </article>

</section>


<section class="team-section current-members">

  <div class="team-section-heading">
    <span>Current Members</span>
  </div>

  <div class="member-grid">

    {% for member in site.data.team_members %}

    <article class="member-card">

      <div class="member-card__image">
        <img
          src="{{ '/images/teampic/' | append: member.photo | relative_url }}"
          alt="Portrait of {{ member.name }}"
        >
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
          Email
        </a>
        {% endif %}

      </div>

    </article>

    {% endfor %}

  </div>

</section>