---
layout: home_ru
locale: "ru"
permalink: /ru/
image:
  feature: pexels-photo-165509.jpeg
---

<div class="tiles">
{% for post in site.categories.ru limit:8%}
	{% include post-grid.html %}
{% endfor %}
</div><!-- /.tiles -->

