---
title: Team
heading: Team
layout: page
eyebrow: Our people
intro: Researchers, students, engineers, and collaborators working together across experiment and instrumentation.
permalink: /team/
---

<section class="team-section">
  <div class="section-heading">
    <div>
      <h2>Meet the group</h2>
      <p class="eyebrow">Current members</p>
      
    </div>
    <a class="text-link" href="{{ '/openings/' | relative_url }}">Join us <span aria-hidden="true">→</span></a>
  </div>

  <div class="team-grid">
    {% for member in site.data.team_members %}
    <article class="member-card">
      <div class="member-card__photo">
        {% if member.photo %}
        <img src="{{ '/images/teampic/' | append: member.photo | relative_url }}" alt="Portrait of {{ member.name }}">
        {% else %}
        <div class="member-card__placeholder" aria-hidden="true">{{ member.name | slice: 0, 1 }}</div>
        {% endif %}
      </div>

      <div class="member-card__body">
        <h3>{{ member.name }}</h3>

        <p class="member-role">{{ member.info }}</p>

        {% if member.number_educ and member.number_educ > 0 %}
        <div class="member-education">
          {% for i in (1..member.number_educ) %}
            {% assign education_item = member[education_key] %}

            {% if education_item and education_item != "" %}
            {{ education_item | markdownify }}
            {% endif %}
          {% endfor %}
        </div>
        {% endif %}

        {% if member.email %}
        <a class="member-email" href="mailto:{{ member.email }}">Email</a>
        {% endif %}
      </div>
    </article>
    {% endfor %}
  </div>
</section>

{% if site.data.students %}
<section class="team-section">
  <div class="section-heading section-heading--stacked">
    <p class="eyebrow">Students</p>
    <h2>Master and bachelor students</h2>
  </div>
  <div class="team-grid team-grid--compact">
    {% for member in site.data.students %}
    <article class="member-card member-card--compact">
      <div class="member-card__body">
        <h3>{{ member.name }}</h3>
        <p class="member-role">{{ member.info }}</p>
      </div>
    </article>
    {% endfor %}
  </div>
</section>
{% endif %}

<section class="team-section">
  <div class="section-heading section-heading--stacked">
    <p class="eyebrow">Alumni</p>
    <h2>Former group members</h2>
  </div>
  <div class="alumni-list">
    {% for member in site.data.alumni_members %}
    <article class="alumni-item">
      <h3>{{ member.name }}</h3>
      <p>{{ member.duration }}</p>
      <span>{{ member.info | strip_html }}</span>
    </article>
    {% endfor %}
  </div>
</section>
