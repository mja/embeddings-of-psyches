---
layout: page
title: History of Art
permalink: /projects/art-history
---

<h2><i>"Depictions of 'Madness' in the History of Art"</i></h2>

<p><b>Introduction:</b> <a href="{% post_url 2022-06-25-symptoms-and-disorders %}">Symptoms and disorders</a></p>
<p><b>Prompt format:</b> <code>the (depiction|representation) of [X] in the history of art</code></p>

<p>The images on this page are AI-art created with image-to-text transformers. Each image links to information about the prompt and other metadata.</p>

{% assign journeys = site.midjourney | where: "project", "art-history" %}

<h3><i>"Madness"</i></h3>
{% assign madness = journeys | where: "symptom", "madness" %}
{% for mj in madness %}
  <p><a href="{{ mj.url }}"><img src="{{ mj.image }}" alt="{{ mj.prompt }}" width="70%" height="70%"/></a></p>
{% endfor %}

<h3><i>"Melancholy"</i></h3>
{% assign melancholy = journeys | where: "symptom", "melancholy" %}
{% for mj in melancholy %}
  <p><a href="{{ mj.url }}"><img src="{{ mj.image }}" alt="{{ mj.prompt }}" width="70%" height="70%"/></a></p>
{% endfor %}

<h3><i>"Rumination"</i></h3>
{% assign rumination = journeys | where: "symptom", "rumination" %}
{% for mj in rumination %}
  <p><a href="{{ mj.url }}"><img src="{{ mj.image }}" alt="{{ mj.prompt }}" width="70%" height="70%"/></a></p>
{% endfor %}

<h3><i>"Mania"</i></h3>
{% assign mania = journeys | where: "symptom", "mania" %}
{% for mj in mania %}
  <p><a href="{{ mj.url }}"><img src="{{ mj.image }}" alt="{{ mj.prompt }}" width="70%" height="70%"/></a></p>
{% endfor %}

<h3><i>"Psychosis"</i></h3>
{% assign psychosis = journeys | where: "symptom", "psychosis" %}
{% for mj in psychosis %}
  <p><a href="{{ mj.url }}"><img src="{{ mj.image }}" alt="{{ mj.prompt }}" width="70%" height="70%"/></a></p>
{% endfor %}

<h3><i>"Neurosis"</i></h3>
{% assign neurosis = journeys | where: "symptom", "neurosis" %}
{% for mj in neurosis %}
  <p><a href="{{ mj.url }}"><img src="{{ mj.image }}" alt="{{ mj.prompt }}" width="70%" height="70%"/></a></p>
{% endfor %}
