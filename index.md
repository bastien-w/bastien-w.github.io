---
title: Home
layout: home
nav_order: 1
search_exclude: true
---
{% include var_custom.html %}

{% for article in all_articles  %}
# [{{ article.title }}]({{article.url}})
<time>{{ article.date | date_to_long_string }}</time>
  {% for item in article.cat %} 
{{ item }}
{: .label }
  {% endfor %}
{{ article.resume }}
<hr>
{% endfor %}