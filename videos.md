---
layout: default
title: Vídeos Semanais
---
# Vídeos Semanais 

<ul>
  {% for post in site.categories.videos %}
    {% if post.url %}

        <p> {{ post.date | date:"%d-%b: " }} <a href="{{ post.url }}">{{ post.title }}</a></p>

    {% endif %}
  {% endfor %}
</ul>