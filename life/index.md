---
layout: default
title: "Life"
description: 아주 가끔씩 일상글을 올려요.
main: true
project-header: true
header-img: img/life.jpg
---

<ul class="catalogue">
{% assign sorted = site.pages | sort: 'order' | reverse %}
{% for page in sorted %}
{% if page.life == true %}
{% include post-list.html %}
{% endif %}
{% endfor %}
</ul>
