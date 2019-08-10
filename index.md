---
layout: grid
title: 首页
---
{% assign accidentpage = site.pages | where: "permalink", "/accident.html" | first %}
{% if accidentpage.accident != null %}
  <div style="box-shadow:5px 5px 10px black;border-color:#faebcc;margin-bottom:2em;border-radius:5px">
    <div style="background-color:{{accidentpage.color}};padding:10px 15px;border-radius:5px 5px 0 0">
        <a href="/accident.html" style="font-size:1.5em;margin:0"><b>⚠{{accidentpage.accident}}</b></a>
    </div>
    <div style="line-height:2em;padding:15px 15px 0 15px">
        {{accidentpage.description}}
    </div>
    <p align="right" style="padding:0 15px 15px 0"><a href="/accident.html">点击了解详情</a></p>
  </div>
{% endif %}

![Title Image](/assets/welcome.png)

@row
![群码](/assets/code.png)
@column
## 新峡Craft门户群
欢迎您加入新峡Craft官方门户群，获取第一时间资讯，并与网友讨论。
@row

-----

{% for post in site.posts limit:5 %}
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
