---
title: "A Technical Blog"
categories:
 - 算法
 - bar
---

* 一点一点把notion上的笔记搬运来这里。
* update since 2021/06/21

{% assign pagecat = page.categories | join ' ' | append: ' '%}
{% assign pagecatlen = page.categories.size %}
  <h1>{{ cat }}</h1>
  <ul>
    {% for post in site.posts %}
    {% assign postcat = '' %}
    {% for thispostcat in post.categories limit: pagecatlen %}
      {% assign postcat = postcat | append: thispostcat %}
      {% assign postcat = postcat | append: ' ' %}
    {% endfor %}

    {% if (postcat == pagecat) %}
      <li><a href="{{ post.url }}">{{ post.title }}</a></li>
    {% endif %}
    {% endfor %}
  </ul>
