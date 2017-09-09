---
layout: archive
title: "Каталог проектов."
date: 2014-05-30T11:40:45-04:00
modified:
excerpt: ""
tags: []
image:
  feature:
  teaser:
---

<div class="tiles">
{% for post in site.categories.ru %}
{% if post.categories contains "projects" %}
    {% include post-grid.html %}
{% endif %}
{% endfor %}
</div><!-- /.tiles -->


