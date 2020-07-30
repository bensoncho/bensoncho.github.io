---
layout: page
title: Links
description: 没有链接的博客是孤独的
keywords: 友情链接
comments: true
menu: 链接
permalink: /links/
---

> 好用工具網站.

<ul>
{% for link in site.data.links %}
  {% if link.src == 'tools' %}
  <li><a href="{{ link.url }}" target="_blank">{{ link.name}}</a></li>
  {% endif %}
{% endfor %}
</ul>

> Coding 類.

<ul>
{% for link in site.data.links %}
  {% if link.src == 'coding' %}
  <li><a href="{{ link.url }}" target="_blank">{{ link.name}}</a></li>
  {% endif %}
{% endfor %}
</ul>

> 設計類.

<ul>
{% for link in site.data.links %}
  {% if link.src == 'design' %}
  <li><a href="{{ link.url }}" target="_blank">{{ link.name}}</a></li>
  {% endif %}
{% endfor %}
</ul>


> 其它

<ul>
{% for link in site.data.links %}
  {% if link.src == 'others' %}
  <li><a href="{{ link.url }}" target="_blank">{{ link.name}}</a></li>
  {% endif %}
{% endfor %}
</ul>
