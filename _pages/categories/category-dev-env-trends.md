---
title: "트렌드에 맞추는 개발 환경" # 카테고리 이름
layout: archive
permalink: categories/env_trends # url
author_profile: true
sidebar:
  nav: "docs"
---

{% assign posts = site.categories.Env_Trends %}
{% for post in posts %} 
  {% include archive-single.html type=page.entries_layout %} 
{% endfor %}