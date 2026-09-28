---
layout: page
title: People
---

<section class="post">
  <header class="major">
    <h2>Current Lab Members</h2>
  </header>

  {% assign current = site.people | where: "categories", "lab-member-current" %}
  {% for person in current %}
    <a href="{{ person.url }}" class="lab-member-card-link">
      <div class="lab-member-card">
        <img class="lab-member-card-photo" src="/assets/images/bio_pics/{{ person.img }}" alt="{{ person.title }}" />
        <div class="lab-member-card-info">
          <h4 class="name-header">{{ person.title }}</h4>
          {% if person.role %}
            <p class="lab-member-card-role">{{ person.role }}</p>
          {% endif %}
          <p class="lab-member-card-snippet">{{ person.content | strip_html | truncatewords: 40, "..." }}</p>
        </div>
      </div>
    </a>
  {% endfor %}

  <header class="major" style="margin-top: 4rem;">
    <h2>Past Lab Members</h2>
  </header>

  {% assign past = site.people | where: "categories", "lab-member-past" %}
  {% for person in past %}
    <a href="{{ person.url }}" class="lab-member-card-link">
      <div class="lab-member-card">
        <img class="lab-member-card-photo" src="/assets/images/bio_pics/{{ person.img }}" alt="{{ person.title }}" />
        <div class="lab-member-card-info">
          <h4 class="name-header">{{ person.title }}</h4>
          {% if person.role %}
            <p class="lab-member-card-role">{{ person.role }}</p>
          {% endif %}
          <p class="lab-member-card-snippet">{{ person.content | strip_html | truncatewords: 40, "..." }}</p>
        </div>
      </div>
    </a>
  {% endfor %}

</section>
