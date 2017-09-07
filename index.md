---
layout: home
permalink: /
image:
  feature: pexels-photo-165509.jpeg
---

<div class="tiles">
{% for post in site.posts limit:8 %}
	{% include post-grid.html %}
{% endfor %}
</div><!-- /.tiles -->

