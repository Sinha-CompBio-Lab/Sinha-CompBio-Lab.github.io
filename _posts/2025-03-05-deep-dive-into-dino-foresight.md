---
layout: single
title: "Deep-Dive into DINO-Foresight"
date: 2025-03-05
categories:
  - Research
  - AI
tags:
  - deep learning
  - computer vision
  - video prediction
  - transformer models
  - computational biology
---
A deep dive to understand DINO-Foresight: Next-Frame prediction breakthrough from Meta. We will cover its technical innovation- factorized transformer, how image embeddings improved during next-frame learning, and, masked features transformer.

Why should anyone care? Next frame prediction is a general-purpose problem extendable across fields and data modalities, eg. how tissues may age given a few sequence images/omics?, and breakthroughs here will help across the board.

Here's the paper before we start: arxiv.org/pdf/2412.11673

Let's start. Autonomous systems need to predict future states to make decisions. Prior approaches generate future RGB frames pixel by pixel. which focuses on irrelevant pars and is computationally inefficient.

If you aren't yet convinced with efficiency as an imp problem - i wanna let you know that chatGPT was possible due to tranformers efficiency to process language.

So what can we do? Videos are crazy amount of data, high-resolution - and pixel-by-pixel learning & prediction is simply not feasible right now. Actually, the solution is conceptually simple.

Instead of pixel-by-pixel learning, we will learn what's conceptually happening in the video (semantic space), predict next step of that, project back to generate video again.

Foundation Models like DINOv2 (pretrained on many images) extract conceptual representations of images. Why not directly predict how these representations evolve instead of going through the pixel space?

(Repeating umpteen time that foundation models are simply models that are pre-trained on a large amount of unlabelled data.)

The above proposed framework is obvious, but the technical solutions is what makes it possible.

First innovation: . DINO-Foresight extracts features from intermediate layers as well, not just the final layer. Why? Because different layers capture different semantic levels: Early layers: local patterns, textures; Middle: object parts; Deep layers: high-level connections (car on ground)

Combining these creates rich, multi-level feature representations. But this creates another challenge: too many dimensions! To solve this, they apply PCA. Can you believe it? Yes, it still exists & works suprisingly well.

Not only it works well to reduce dimension, it actually improves performance - especially for short-term prediction and moving objects. It forces the model to focus on the most important feature variations.

The computational complexity is still pretty high coz we are dealing with attention based transformers - very powerful but time-consuming. A video with just 5 frames at 32×64 resolution, this means 10.7 billion operations - chatGPT3 has 175B parameters. This is not feasible.

Here comes "Factorized Attention" - splitting attention into two separate processes:

Temporal attention: Track how each position evolves across frames

&

Spatial attention: Understand relationships within each frame

Intuitively, this mimics how we perceive motion - following objects through time while understanding spatial context at each moment. We don't process every relationship between every position across all frames (standard attention).

This factorization reduces complexity from to 100× lower - see details in paper (figure 1). For the same 5-frame sequence, this cuts computation from ~10.7B operations to ~0.7B operations - a >100× reduction.

But how does any of this predicts future frames? Here comes Third innovation: Using masked Feature Transformer (Like masked encoders): During training, parts of future frame features are masked. The transformer must predict these features based on patterns in previous frames.

Learning what'll happen next in an image can give deeper understanding of the image. Indeed the features learned during above performed better than state of the art (Vista) with lower resources. But my fav is the below. I promise you'd love it. Ready?

Just to make sure we are on the same page - There's a frozen layer we start with of an image (dinoV2 representation). Then above learning tunes this representation to predict future frames and thus create intermediate layers. Here's the surprise.

They discovered that these intermediate layers that were trained to predict future frame actually end up doing way better than first layer tasks like segmentation, depth prediction, etc. Did you see what happened?


This learning of next frame isn't just learning to predict next frame; It's also learning additional structure of the image in a self-supervised way that was not there - using just image. Elegant and powerful.

Going back to our stuff: there can be many applications of above in computational biology. eg. better protein embedding using dynamics data, tuning scGPT with post-computation of trajectories information.
