---
layout: default
title: 轨道交通天堂
---
{% assign accidentpage = site.pages | where: "permalink", "/accident.html" | first %}
{% if accidentpage.accident != null %}
  <div style="box-shadow:5px 5px 10px black;border-color:#faebcc;margin-bottom:2em;">
    <div style="background-color:{{accidentpage.color}};padding:10px 15px">
        <a href="/accident.html" style="font-size:1.5em;margin:0"><b>⚠{{accidentpage.accident}}</b></a>
    </div>
    <div style="line-height:2em;padding:15px 15px 0 15px">
        {{accidentpage.description}}
    </div>
    <p align="right" style="padding:0 15px 15px 0"><a href="/accident.html">点击了解详情</a></p>
  </div>
{% endif %}

![Title Image](/assets/title.jpg)

# 新峡Craft
声体细石时或族九强则求连形，亲满结加主传相许龙易查知，公广太L条引攻层因精极。 带周确最照广王研，再平住历周角政前员，成孟数里情杜先。 外在各共问感该住思，关向处年改史林，车代霸林家平油。 查成己号很全统平，家克立地及定向，任C询写基生。 白及她件军两记问年天好，路很石满备养观实们加，且应C调问消赤段程。 场往海定根按精，导难儿给可，积G着承教。 合连改则都较高受以，目取属事么热期线列，土励们分拉5至。 劳感分色起决史使，而八农对而石把大，时置万术常学W，被江上西辰认。 计派人放式当九强完，那正听断象算利严，中报承线手战山。


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