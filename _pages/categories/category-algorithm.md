---
title: "자료구조&알고리즘" # 카테고리 이름
layout: archive
permalink: categories/data_structure_algorithm # url
author_profile: true
sidebar:
  nav: "docs"
---

{% assign posts = site.categories.DataStructureAlgorithm %}
{% for post in posts %} 
  {% include archive-single.html type=page.entries_layout %} 
{% endfor %}