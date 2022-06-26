---
layout: page
title: About
permalink: /about/
author: markadams
subtitle: Bio and contact
---

<p>
{% assign authorDetails = site.data.authors[page.author] %}
{{ authorDetails.bio }}
</p>

## Contact

<ul>
  <li>
	<a href="{{ site.email | prepend: "mailto:" }}">
	  {{ site.email }}
	</a>
  </li>
</ul>