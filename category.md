---
layout: rawhtml
title:  "分类"
navbar: "..."
permalink: /category
---

<html lang="zh-cn">

  {%- include head.html -%}

  <body>

    {%- include header.html -%}

    <main class="page-content" aria-label="Content">
      <div class="wrapper" id="mainwrap">
        <div id="allcate">
        <ul>
        {% assign categories_list = site.categories %}
          {% if categories_list.first[0] == null %}
            {% for category in categories_list %}
              <li><a href="/category?sel={{ category }}#{{ category }}">{{ category | capitalize }} <sub>({{ site.tags[category].size }})</sub></a></li>
            {% endfor %}
          {% else %}
            {% for category in categories_list %}
              <li><a href="/category?sel={{ category[0] }}#{{ category[0] }}">{{ category[0] | capitalize }} <sub>({{ category[1].size }})</sub></a></li>
            {% endfor %}
          {% endif %}
        {% assign categories_list = nil %}
        </ul>
        </div>

        {% for tag in site.categories %}
          <div id="{{ tag[0] }}">
          <h3 id="{{ tag[0] }}">{{ tag[0] | capitalize }}</h3>
          <ul>
            {% assign pages_list = tag[1] %}
            {% for post in pages_list %}
              {% if post.title != null %}
              {% if group == null or group == post.group %}
              <li><a href="{{ site.url }}{{ post.url }}">{{ post.title }} <sub><time datetime="{{ post.date | date_to_xmlschema }}" itemprop="datePublished">{{ post.date | date: "%Y-%m-%d" }}</time></sub></a></li>
              {% endif %}
              {% endif %}
            {% endfor %}
            {% assign pages_list = nil %}
            {% assign group = nil %}
          </ul>
          </div>
        {% endfor %}
      </div>
    </main>

    {%- include footer.html -%}

  </body>
    <script type="text/javascript" language="Javascript">
    function getParameterByName(name, url) {
        if (!url) url = window.location.href;
        name = name.replace(/[\[\]]/g, '\\$&');
        var regex = new RegExp('[?&]' + name + '(=([^&#]*)|&|#|$)'),
            results = regex.exec(url);
        if (!results) return null;
        if (!results[2]) return '';
        return decodeURIComponent(results[2].replace(/\+/g, ' '));
    }
    if (getParameterByName('sel')!=null){
        var input = document.getElementById("mainwrap").getElementsByTagName("div");
        var inputList = Array.prototype.slice.call(input)
        inputList.forEach(function (value) {
            if (value.id=="allcate" || value.id!=getParameterByName('sel')){
                value.style.display="none";
            }
        });
    }
  </script>

</html>