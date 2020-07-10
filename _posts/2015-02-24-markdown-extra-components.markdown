---
title: "DeepMoD"
layout: post
date: 2020-07-10 12:12
image: /assets/images/markdown.jpg
headerImage: false
projects: true
category: project
author: Remykusters
description: DeepMoD
---

## Summary:

DeepMoD is a Deep learning based Model Discovery algorithm. DeepMoD discovers the partial differential equation underlying a spatio-temporal data set using sparse regression on a library of possible functions and their derivatives. A neural network approximates the data and constructs the function library, but it also performs the sparse regression.

This tool has been released as package in both Tensorflow and Pytorch. Note that all the further developmement happens on the  <a href="https://github.com/PhIMaL/DeePyMoD_torch">Pytorch version</a> and that the  <a href="https://github.com/PhIMaL/DeePyMoD">Tensorflow version</a>  is not further maintained. 

The paper is available on <a href="https://arxiv.org/abs/1904.09406">arXiv</a>



[Markdowm Image][/image/url]

```raw
![Markdowm Image][/image/url]
```

---

## Short description 

Essentially this tool allows the user to infer the differential equation underlying a spatio-temporal data set from a predefined set of library  functions. This approach combines classical symbolic regression task with training a neural network to represent the data. Symbolic  regression is a classical data-science approach that seeks the  mathematical or physical expression that “fits” the presented data best. Knowledge of the underlying equations of a data-set allows for extrapolation of the data-set and interpretation of the physical/mathematical parameters involved in the problem at hand. 

In this approach, the PDE underlying a dataset $u({x,t})$ is discovered by writing the model discovery task as a regression problem,

$$u_t(x,t) =  \Theta \xi,$$

where $\Theta$ is a matrix containing a library of polynomial and spatial derivative functions (e.g.$u,u_x,uu_x$). Here model discovery turns into finding a sparse representation of the coefficient vector $\xi$. The novelty of our work is that we implement this regression task directly *within the cost function* of the neural network. Consequently, training the network not only adjusts the weights and biases of the network, but also adjusts the components of the sparse vector $\xi$. 

---

## Video and presentation

Below you can find a presentation from the 2020 Applied Machine Learning Conference in Lausanne during the AI & Physics workshop describing DeepMoD:

<iframe width="560" height="315" src="https://www.youtube.com/embed/Ml4EXS_MUBc" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

Add the slides of this talk are also availeble below:

<iframe src="//www.slideshare.net/slideshow/embed_code/key/akfCHprHumVgOm" width="595" height="485" frameborder="0" marginwidth="0" marginheight="0" scrolling="no" style="border:1px solid #CCC; border-width:1px; margin-bottom:5px; max-width: 100%;" allowfullscreen> </iframe> <div style="margin-bottom:5px"> <strong> <a href="//www.slideshare.net/RemyKusters/deepmod-deep-learning-model-discovery-236789164" title="DeepMoD: Deep Learning Model discovery" target="_blank">DeepMoD: Deep Learning Model discovery</a> </strong> from <strong><a href="https://www.slideshare.net/RemyKusters" target="_blank">Remy Kusters</a></strong> </div>





