---
layout: page
title: History of Art
permalink: /projects/art-history
---

<b><i>"Depictions of Madness in the History of Art"</i></b>

{% for mj in site.midjourney %}
  <p><img src="{{ mj.image }}" alt="{{ mj.prompt }}" width=512 height=512/></p>
  <p>"<i><a href="{{ mj.url }}">{{ mj.prompt }}</a></i>"</p>
{% endfor %}