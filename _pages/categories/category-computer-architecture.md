---
title: "컴퓨터 구조" # 카테고리 이름
layout: archive
permalink: categories/computer_architecture # url
author_profile: true
sidebar:
  nav: "docs"
---

{% assign posts = site.categories.ComputerArchitecture %}
{% for post in posts %} 
  {% include archive-single.html type=page.entries_layout %} 
{% endfor %}