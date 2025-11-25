---
title: "Dev Env Trends" # 카테고리 이름
layout: archive
permalink: categories/env_trends # url
author_profile: true
sidebar:
  nav: "docs"
---

{% assign posts = site.categories.EnvTrends %}
{% for post in posts %} 
  {% include archive-single.html type=page.entries_layout %} 
{% endfor %}