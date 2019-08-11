---
layout: default
notitleh1: true
title: 轨道交通天堂
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

<div class="row">
    <div class="col-sm-3 col-xs-4">
        <img src="/assets/code.png" />
    </div>
    
    <div class="col-sm-9 col-xs-8">
        <h2>新峡Craft门户群</h2>
        <p>加入新峡Craft门户群，您可以第一时间获取资讯，可以与各路网友交谈，也可以ll会友哦(x)</p>
        <p>赶快来加入吧！</p>
    </div>
</div>

-----
### 最新动态
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
