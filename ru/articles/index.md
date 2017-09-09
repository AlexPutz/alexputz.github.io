---
layout: archive
title: "Заметки"
date: 2014-05-30T11:39:03-04:00
modified:
excerpt: "Коллекция статей, мыслей, заметок."
tags: []
image:
  feature:
  teaser:
---

<div class="tiles">
{% for post in site.categories.ru %}
{% if post.categories contains "articles" %}
    {% include post-grid.html %}
{% endif %}
{% endfor %}
</div><!-- /.tiles -->
