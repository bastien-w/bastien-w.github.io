---
layout: page
title: Categories
nav_order: 2
search_exclude: true
---
{% assign cats = "" | split: "" %} 

{% for article in site.articles %} 
  {% assign cats = cats | push: article.cat %} 
{% endfor %} 

{% for article in site.pinned_articles %} 
  {% assign cats = cats | push: article.cat %} 
{% endfor %} 

{% assign cats = cats | uniq %}


{% for cat in cats %} 
## {{ cat }}
  {% for article in site.articles %} 
    {% if article.cat contains cat %}
### {{article.title}}
    {% endif %}
  {% endfor %}
  {% for article in site.pinned_articles %} 
    {% if article.cat contains cat %}
### {{article.title}}
    {% endif %}
  {% endfor %}  
{% endfor %} 