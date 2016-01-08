---
layout: default
title: Vídeos Semanais
---

<ul>
  {% for post in site.posts %}

    {% unless post.next %}
      <h2>{{ post.date | date: '%Y' }}</h2>
    {% else %}
      {% capture year %}{{ post.date | date: '%Y' }}{% endcapture %}
      {% capture nyear %}{{ post.next.date | date: '%Y' }}{% endcapture %}
      {% if year != nyear %}
        <h2>{{ post.date | date: '%Y' }}</h2>
      {% endif %}
    {% endunless %}

    {% unless post.next %}
      <h3>{{ post.date | date: '%b' }}</h3>
    {% else %}
      {% capture month %}{{ post.date | date: '%b' }}{% endcapture %}
      {% capture nmonth %}{{ post.next.date | date: '%b' }}{% endcapture %}
      {% if month != nmonth %}
        <h3>{{ post.date | date: '%b' }}</h3>
      {% endif %}
    {% endunless %}
    
    {% if post.categories contains "artigos" %}
  
      <p>{{ post.date | date:"%d  :" }} <a href="{{ post.url }}">{{ post.title }}</a></p>
   
   {% endif %}

  {% endfor %}
</ul>

<ul>
  {% for post in site.categories.videos %}
    {% if post.url %}

        <p> {{ post.date | date:"%d-%b: " }} <a href="{{ post.url }}">{{ post.title }}</a></p>

    {% endif %}
  {% endfor %}
</ul>