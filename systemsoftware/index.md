---
layout: default
work: true
main: true
title: Selected Projects
description: System Software에 관한 큰 범주의 메뉴
project-header: true
header-img: "img/project_bg.jpg"
---

<div class="catalogue">
{% assign sorted = site.pages | sort: 'order' | reverse %}
{% for page in sorted %}
{% if page.systemsoftware == true %}

     {% include post-list.html %}

{% endif %}
{% endfor %}
</div>
