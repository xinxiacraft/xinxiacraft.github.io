---
layout: page
title: 动态
permalink: /activity.html
---

{% for post in site.posts %}
  <article style="display:block;box-sizing:border-box;box-shadow:0 6px 12px rgba(34,34,34,0.1);padding:1em">
    <h3 style="margin-bottom:0;margin-top:0.5em">
      <a href="{{ post.url }}">
        {{ post.title }}
      </a>
      <sub><time datetime="{{ post.date | date: "%Y-%m-%d" }}">{{ post.date | date: "%Y-%m-%d" }}</time></sub>
    </h3>
    <p style="margin-left:2em;margin-bottom:0">{{ post.description }}</p>
    {% if post.image %}
    <img src="{{ post.image }}" style="width:100%;border-radius:1em;margin-top:1em" />
    {% endif %}
  </article>
{% endfor %}