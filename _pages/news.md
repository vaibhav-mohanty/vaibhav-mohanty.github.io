---
layout: page
permalink: /news/
title: news
description:
nav: true
nav_order: 4
---

<!-- _pages/news.md : entries live in _data/press.yml -->

<div class="publications">
{% assign press_by_year = site.data.press | group_by_exp: "item", "item.date | slice: 0, 4" %}
{% for year in press_by_year %}
  <h2 class="bibliography">{{ year.name }}</h2>
  <ol class="bibliography">
  {% for item in year.items %}
    <li>
      <div class="title"><a href="{{ item.url }}" target="_blank" rel="noopener">{{ item.title }}</a></div>
      <div class="periodical"><em>{{ item.outlet }}</em>, {{ item.date | append: "-01" | date: "%B" }}</div>
    </li>
  {% endfor %}
  </ol>
{% endfor %}
</div>