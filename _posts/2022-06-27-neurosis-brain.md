---
layout: post
title:  "Neurosis on the brain: text weights in Midjourney"
tags: art-history
author: markadams
date:   2022-06-27 20:52:59 +0100
---

Initial experiments for the [History of Art][art-history] project with the term "neurosis" in the prompt returned results with brain-like imagery:

{% assign brain = site.midjourney | where: "prompt", "the depiction of neurosis in the history of art" %}
{%- for mj in brain limit:3 -%}
<a href="{{ mj.url }}"><img src="{{ site.static_url }}/midjourney/{{ mj.save }}.jpg" alt="{{ mj.prompt }}" width="33%" height="33%"/></a>
{%- endfor -%}

The image with the [deflated brain][c0fa160c] (or is it a bunch of small brains piled like pillows?) was intriguing, the overall effect was not what I was going for. I then redid the prompt adding [text weight][text-weight] modifiers to downweight or remove any brain-related output.

{% assign nobrain = site.midjourney | where: "prompt", "the depiction of neurosis in the history of art::1 brain::-0.5" %}
{%- for mj in nobrain limit:3 -%}
<a href="{{ mj.url }}"><img src="{{ site.static_url }}/midjourney/{{ mj.save }}.jpg" alt="{{ mj.prompt }}" width="33%" height="33%"/></a>
{%- endfor -%}

While the engineers who collect the data, design the model, and train it are responsible for what text-to-image generators _can_ produce, the user still has a duty to accept, reject, or modify the results of their prompt. 

[art-history]: /projects/art-history
[c0fa160c]: /midjourney/2022-06-25-c0fa160c-the_depictionofneurosisinthehistoryofart.html
[text-weight]: https://midjourney.gitbook.io/docs/user-manual#advanced-text-weights