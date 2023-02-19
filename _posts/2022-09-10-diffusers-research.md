---
layout: post
title:  "diffusers: a platform for systematic AI art research and creative ideation"
date:   2022-08-10 11:39:03 +0100
tags: art-history, diffusers
author: markadams
---

[diffusers](https://github.com/huggingface/diffusers) is a python library for running state-of-the art diffusion models like [StableDiffusion](https://github.com/CompVis/stable-diffusion), which has the same capabilities as other text-to-image AI tools like [Midjourney](https://www.midjourney.com) and [DALL·E2 ](https://openai.com/dall-e-2/).

What distinguishes StableDiffusion from the others is that the [model and development are open source](https://stability.ai/blog/stable-diffusion-announcement). You can obtain the model weights yourself from [CompVis page on HuggingFace](https://huggingface.co/CompVis). HuggingFace also hosts a [basic web frontend](https://huggingface.co/spaces/stabilityai/stable-diffusion) and the same model powers [DreamStudio](http://dreamstudio.ai).

Importantly for research purposes, the diffusers library allows programmatic access which makes it possible to explore the model more systematically, iterating over input parameters and prompt constructions.

<img src="https://f000.backblazeb2.com/file/mja-static/latent/diffusers/the_depiction_of_melancholy_in_the_history_of_art-seed673558910-scale5-steps30-auto-20b11a49-5ae8-3a23-bd7b-67ba2205bc89.jpg"  height="33%" width="33%"/><img src="https://f000.backblazeb2.com/file/mja-static/latent/diffusers/the_depiction_of_melancholy_in_the_history_of_art-seed673558910-scale8-steps30-auto-20b11a49-5ae8-3a23-bd7b-67ba2205bc89.jpg"  height="33%" width="33%"/><img src="https://f000.backblazeb2.com/file/mja-static/latent/diffusers/the_depiction_of_melancholy_in_the_history_of_art-seed673558910-scale15-steps30-auto-20b11a49-5ae8-3a23-bd7b-67ba2205bc89.jpg" height="33%" width="33%"/>

<img src="https://f000.backblazeb2.com/file/mja-static/latent/diffusers/the_representation_of_rumination_in_the_history_of_art-seed673558910-scale5-steps30-auto-ae86b7b3-3a69-3c6b-bcb4-e9c6cc269019.jpg"  height="33%" width="33%"/><img src="https://f000.backblazeb2.com/file/mja-static/latent/diffusers/the_representation_of_rumination_in_the_history_of_art-seed673558910-scale8-steps30-auto-ae86b7b3-3a69-3c6b-bcb4-e9c6cc269019.jpg"  height="33%" width="33%"/><img src="https://f000.backblazeb2.com/file/mja-static/latent/diffusers/the_representation_of_rumination_in_the_history_of_art-seed673558910-scale15-steps30-auto-ae86b7b3-3a69-3c6b-bcb4-e9c6cc269019.jpg" height="33%" width="33%"/>

If you know a smattering of Python, diffusers can be set up and run in just a dozen or so lines of code. I've made [a basic Jupyter notebook that runs on Google Colab](https://colab.research.google.com/drive/1Z5Ibpgqe-LEWYzOAeqa8s-qFEhbXml--?usp=sharing) for getting started. 