---
title: "DeepMoD 2.0: An integrated framework for model discovery"
layout: post
date: 2021-04-10 16:10
image: /assets/images/markdown.jpg
headerImage: false
projects: true
category: project
author: Remykusters
description: DeepMoD 2.0.
---

<em> (Published as a workshop paper at AAAI 2021 Spring Symposium on Machine Learning with Physics Sciences, <a href="https://arxiv.org/abs/2011.04336">link</a>) <em>

In this pos we present a modular approach to combine deep-learning based models with state-of-the-art sparse regression techniques. This framework is a generalisation of the DeepMoD 1.0 work and it's main goal is to provide an accessible and modular package to perform NN (neural network)-based model discovery. 

<img src="{{site.baseurl}}/assets/images/deepmod2.png">

This framework consists of four modules. (I) A function approximator constructs a surrogate model of the data, (II) from which a library of candidate terms and the time derivatives is constructed using automatic differentiation. (III)  A sparsity estimator constructs a sparsity mask to select the active terms in the library using a pre-defined sparse regression algorithm and (IV) a constraint function constrains the function approximator to solutions allowed by the active terms obtained from the sparsity estimator.

New to the framework is that we dynamically apply a mask to select the active terms in the function library throughout training and constrain the network to solutions of the equation given by these active terms. To determine this mask, we can use any non-differentiable sparsity-promoting algorithm, such as PDE-Find or adaptive Lasso to select the PDE that underlies the data. Below we show an example of this mask during the optimisation (training) of a model discovery task of the Burgers equation ($u_t = \nu u_{xx} - u u_x$).

<img src="{{site.baseurl}}/assets/images/training.png">

This allows us to use a constrained neural network to model the data and construct an accurate function library, while an advanced sparsity promoting algorithm is used to dynamically discover the equation based on output from the network. 

We provide our <a href="https://github.com/PhIMaL/DeePyMoD">framework</a> as a python based package with the its corresponding  <a href="https://phimal.github.io/DeePyMoD/">documentation</a>.  Mirroring our approach, each model consists of four modules: a function approximator, library, constraint and sparsity estimator module. Each module can be customised or replaced without affecting the other modules, allowing for quick experimentation. Our framework is built on Pytorch and any Pytorch model (i.e. RNNs) can be used as function approximator. The sparse estimator module follows the Scikit-learn API, i.e., all the build-in Scikit-learn estimators can be used.

