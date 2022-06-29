---
layout: post
title:  "Prompting madness: exploring the representation of mental illness and experience in AI art"
date:   2022-06-26 16:45:03 +0100
tags: introduction
author: markadams
---

{% assign mj4e39b8ea= site.midjourney | where: "job_id", "4e39b8ea-04bb-48c8-8cc7-19ab59d841be" %}

<a href="{{ mj4e39b8ea[0].url }}"><img src="{{ site.static_url }}/midjourney/{{ mj4e39b8ea[0].save }}.jpg" alt="{{ mj67302fc3[0].prompt }}"/></a>

> [AI] is not a mirror, and it is not a parrot — [Joanna J. Bryson][sentience-and-sensibility]

Text-to-image generators are deep learning models that create images based on natural language prompts. These generators (such as [DALL·E 2][DALLE2], [Midjourney][midjourney], and [IMAGEN][imagen]) are now able to construct novel, credible photograph- and painting-like images. As computer vision algorithms, these tools are built by training them on millions or billions of pairs of images and text descriptions.

An ethical concern with text-to-image generators is that they "[reflect social stereotypes, oppressive viewpoints, and derogatory, or otherwise harmful, associations to marginalized identity groups][saharia-norouzi]". This project explores similar concerns for the representation of mental health, mental disorders, and neurodivergence in AI-generated imagery. At the same time, it looks into how variations, fluctuations, and disruptions of the human psyche have been depicted through art as captured by the latent space of deep learning embeddings.

## Prior art

- Researcher @[eolasinntinn][eolasinntinn] used [craiyon][craiyon] to generate terms from the "[D(ALL-E)SM-5][dallesm5]".

[dalle2]: https://openai.com/dall-e-2/
[midjourney]: https://midjourney.org
[imagen]: https://imagen.research.google
[sentience-and-sensibility]: https://www.wired.com/story/lamda-sentience-psychology-ethics-policy/
[saharia-norouzi]: https://arxiv.org/abs/2205.11487
[prabhu-birhane]: https://arxiv.org/abs/2006.16923
[eolasinntinn]: https://twitter.com/eolasinntinn/
[dallesm5]: https://twitter.com/eolasinntinn/status/1536406266544807936
[craiyon]: https://www.craiyon.com

