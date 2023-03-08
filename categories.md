---
layout: page
title: Categories
permalink: /categories/
nav_order: 2
search_exclude: true
---
{% include var_custom.html %}

{% for cat in cats %} 
## {{ cat }}
  {% for article in all_articles %} 
    {% if article.cat contains cat %}
[{{article.title}}]({{article.url}}) - <time datetime="{{ article.date | date: "%Y-%m-%d" }}">{{ article.date | date_to_long_string }}</time>
    {% endif %}
  {% endfor %} 
{% endfor %} 