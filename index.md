---
title: Home
layout: home
nav_order: 1
search_exclude: true
---
<ul>
  {% for article in site.articles %}
    <h1>
      <a href="{{ article.url }}">
        {{ article.title }}
      </a>
      </h1>
      <time datetime="{{ article.date | date: "%Y-%m-%d" }}">{{ article.date | date_to_long_string }}</time>
      <p>{{ article.resume }}</p>
      <hr>
  {% endfor %}
</ul>