---
layout: page
title: SHOAL Lab Members
permalink: /people/
---
<!-- Global site tag (gtag.js) - Google Analytics -->
<script async src="https://www.googletagmanager.com/gtag/js?id=G-QQLNFGW8CP"></script>
<script>
  window.dataLayer = window.dataLayer || [];
  function gtag(){dataLayer.push(arguments);}
  gtag('js', new Date());

  gtag('config', 'UA-146764207-1');
</script>

<section class="post">

<p>If you are doing research with SHOAL Lab, you should be featured on this page. Follow <a href="{{ '/onboarding/' | relative_url }}">these directions</a> to add your profile to the site.</p>

  {% assign current = site.people | where: "categories", "lab-member-current" %}
  {% if current.size > 0 %}
    <header class="major">
      <h3>Current Lab Members</h3>
    </header>

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
  {% endif %}

  {% assign past = site.people | where: "categories", "lab-member-past" %}
  {% if past.size > 0 %}
    <header class="major" style="margin-top: 4rem;">
      <h3>SHOAL Lab Alumni</h3>
    </header>

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
  {% endif %}

</section>
