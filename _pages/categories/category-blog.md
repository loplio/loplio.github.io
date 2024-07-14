---
title: "Github Blog 관련" # 카테고리 이름
layout: archive
permalink: categories/blog # url
author_profile: true
sidebar:
  nav: "docs"
---

{% assign posts = site.categories.Blog %}
{% for post in posts %} 
  {% include archive-single.html type=page.entries_layout %} 
{% endfor %}