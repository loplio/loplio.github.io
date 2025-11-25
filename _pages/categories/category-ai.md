---
title: "인공지능" # 카테고리 이름
layout: archive
permalink: categories/ai # url
author_profile: true
sidebar:
  nav: "docs"
---

{% assign posts = site.categories.AI %}
{% for post in posts %} 
  {% include archive-single.html type=page.entries_layout %} 
{% endfor %}