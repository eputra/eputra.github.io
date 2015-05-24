---
layout: page
title: Categories
description: Kategori blognya si Eka Putra
---

{% assign sorted_cats = site.categories | sort %}
{% for cat in sorted_cats %}
<span id="{{ cat[0] }}" class="cat">{{ cat[0] }}</span>
<div class="post-list">
	{% for post in cat[1] %}
		<li>
			<a href="{{ post.url }}">{{ post.title }}</a><br>
			<small><time datetime="{{ post.date | date_to_xmlschema }}" class="post-date">{{ post.date | date_to_string }}</time></small>
		</li>
	{% endfor %}
</div>
{% endfor %}
