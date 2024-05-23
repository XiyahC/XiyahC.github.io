---
title: NLP-Connecting Language to the World
date: 2024-05-23
tags: NLP
---

1. [connect vision - language](#1connect-vision---language)
2. generative vision-language model
3. others[speech, audio]
4. from language to code
5. from language to action

# 1.connect vision - language
## History
1960s first cv project.  
2000s shallow classifiers and feature engineering.  
2012  deep learning revolution.  
    CNN in ImageNet.  
    unification of architectures.  
    Rise of image generation (VAEs, GANs, etc.).  
2020s eras of vision transformer.  

## How to encode images?
**Vision Transformers (ViT)**.  Image to patch(matrices, e.g. you have different channels for different colors) + position embedding. Feed these channels into transformers.  

## How to encode paired image-text?
Idea: create a space to represent both semantics of language and image. (This is similar to the idea while I use Meta's laser_encoders to complete multilingual tasks).  

Then create a model that can align semantically-equivalent text and images nearby.  

把image和text转到同一个坐标系里，相关度高的图片和文字如猫猫图片+“A cat”，在坐标系里就会离得近。  


