---
layout: page
title: About
permalink: /about/
author: markadams
subtitle: Bio and contact
---

## Contributors

<ul>
{% for authorDetails in site.data.authors %}
	<li>{{ authorDetails[1].bio }}</li>
{% endfor %}
</ul>

## Contact

<ul>
  <li>
	<a href="{{ site.email | prepend: "mailto:" }}">
	  {{ site.email }}
	</a>
  </li>
</ul>