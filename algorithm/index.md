---
layout: default
work: true
main: true
title: Selected Algorithms
description: 풀어낸 알고리즘 문제에서 정리 할 만한 것들.
project-header: true
header-img: "img/project_bg.jpg"
---

<div class="catalogue">
{% assign sorted = site.pages | sort: 'order' | reverse %}
{% for page in sorted %}
{% if page.algorithm == true %}

     {% include post-list.html %}

{% endif %}
{% endfor %}
</div>
