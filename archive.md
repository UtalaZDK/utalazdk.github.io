---
layout: page
title: 文章归档
permalink: /archive/
---

{% for post in site.posts %}
  {% assign currentdate = post.date | date: "%Y年" %}
  {% if currentdate != date %}
    {% unless forloop.first %}</ul>{% endunless %}
    <h3>{{ currentdate }}</h3>
    <ul>
    {% assign date = currentdate %}
  {% endif %}
    <li>
      <span>{{ post.date | date: "%m月%d日" }}</span> 
      <a href=" ">{{ post.title }}</a >
    </li>
  {% if forloop.last %}</ul>{% endif %}
{% endfor %}
