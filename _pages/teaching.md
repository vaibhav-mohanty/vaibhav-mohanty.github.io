---
layout: page
permalink: /teaching/
title: teaching
description:
nav: true
nav_order: 5
---

<!-- _pages/teaching.md : entries live in _data/teaching.yml -->

<div class="publications">
{% assign teaching_by_year = site.data.teaching | group_by: "year" %}
{% for year in teaching_by_year %}
  <h2 class="bibliography">{{ year.name }}</h2>
  <ol class="bibliography">
  {% for item in year.items %}
    <li>
      <div class="title">{{ item.place }}{% if item.course %}, {{ item.course }}{% endif %}</div>
      <div class="periodical"><em>{{ item.role }}</em></div>
      {% if item.term or item.level %}<div class="periodical">{{ item.term }}{% if item.term and item.level %}, {% endif %}{{ item.level }}</div>{% endif %}
      {% if item.note %}<div class="periodical">{{ item.note }}</div>{% endif %}
    </li>
  {% endfor %}
  </ol>
{% endfor %}
</div>