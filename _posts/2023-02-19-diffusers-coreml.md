---
layout: post
title:  "Using Core ML versions of diffusers models in python on Apple Silicon"
date: 2023-02-15 10:54:46 +0000
tags: diffusers
author: markadams
---

Apple have released a set of scripts for [converting Diffusion models to Core ML](https://github.com/apple/ml-stable-diffusion) that are optimised for running on Apple Silicon. The code includes a python command line script for generating images but it is rather slow as it has to compile the model each time. To speed things up, it's possible to load the model in your own python scripts once and then run the pipeline multiple times.

On an M2 Pro with 32GB of memory, I get a 2x speed-up running Stable Diffusion with Core ML in python compared to the PyTorch versions with MPS backend (10 seconds vs 22 seconds).

## Set-up a conda environment

```sh
conda create -n coreml_stable_diffusion python=3.8 -y
conda activate coreml_stable_diffusion
pip install git+https://github.com/apple/ml-stable-diffusion
```

## Download the ready-made Core ML model

Follow the instructions for [downloading the models](https://github.com/apple/ml-stable-diffusion#-using-ready-made-core-ml-models-from-hugging-face-hub). I recommend grabbing the `split_einsum` version of a model as it lets you experiment with running the model on the Apple Neural Engine (ANE). 

```python
repo_id = "apple/coreml-stable-diffusion-v1-4"
variant = "split_einsum/packages"
```

Running the download script should result in the `model_path`
```python
model_path = "models/coreml-stable-diffusion-v1-4_split_einsum_packages"
```

## Create the diffusers pipeline

The [diffusers](https://github.com/huggingface/diffusers) pipeline can be created like normal. It's important that the `model_id` match the version of the Core ML model that was downloaded (in this instance, Stable Diffusion v1.4).

```python
from diffusers import StableDiffusionPipeline
from python_coreml_stable_diffusion.pipeline import get_coreml_pipe
import coremltools
import numpy as np

model_id = "CompVis/stable-diffusion-v1-4"
pytorch_pipe = StableDiffusionPipeline.from_pretrained(model_id)
```

## Get the Core ML version of the pipeline

The `get_coreml_pipe()` function loads the Core ML version of the model using the configuration of the diffusers model

```python
coreml_pipe = get_coreml_pipe(pytorch_pipe=pytorch_pipe,
  mlpackages_dir=model_path,
  model_version=model_id,
  compute_unit="ALL")
```

## Image inference

The `coreml_pipe` can be called similarly to a diffusers pipe, returning a PIL image.

```python
np.random.seed(9)
image = coreml_pipe(prompt="a cat on the moon",
    height=coreml_pipe.height,
    width=coreml_pipe.width,
    num_inference_steps=25,
    guidance_scale=7.5)
image.images[0]
```
![](https://static.differentialist.info/file/mja-static/latent/diffusers/moon-cat-all.png)

## Experiment with other compute unit combinations

You can see the list of available compute units with
```python
coremltools.ComputeUnit._member_names_
## ['ALL', 'CPU_AND_GPU', 'CPU_ONLY', 'CPU_AND_NE']
```

## Model versions

The ready-made Core ML and diffusers models:

|Core ML repo id                     |Diffusers model id                     |
|------------------------------------|---------------------------------------|
|apple/coreml-stable-diffusion-v1-4  |CompVis/stable-diffusion-v1-4          |
|apple/coreml-stable-diffusion-v1-5  |runwayml/stable-diffusion-v1-5         |
|apple/coreml-stable-diffusion-2-base|stabilityai/stable-diffusion-2-base    |
|apple/coreml-stable-diffusion-2-1-base|stabilityai/stable-diffusion-2-1-base|