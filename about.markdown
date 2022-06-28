---
layout: page
title: About
permalink: /about/
author: markadams
subtitle: Info and contact
---

**Embedding the Psyche** is an art research project about the representation of mental health in AI-driven art. An "embedding" is the way that a data point, concept, or feature is encoded within certain deep learning models. See the [project introduction][intro] for more.

## Authors

<ul>
{% for authorDetails in site.data.authors %}
	<li>{{ authorDetails[1].bio }} (<a href="{{ authorDetails[1].uri }}">web</a>) (<a href="https://twitter.com/{{ authorDetails[1].twitter_username }}">twitter</a>)</li>
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

## Terms

- [Words, code, and text data][source] made available under an MIT license.
- Images generated with [Midjourney][mjco] are copyright [Midjourney, Inc][mjinc], used under license.

[intro]: {% post_url 2022-06-26-prompting-madness %}
[source]: {{ site.source_url }}/README.md
[mjco]: https://midjourney.com
[mjinc]: https://midjourney.org
