---
title: Model serving
layout: page
parent: Units
nav_order: 6
---

# Model serving

This week, we moved on to the next stage of the ML system lifecycle: model serving.

We said that a model serving service:

* may be able to prepare batch predictions in advance of when they are needed, but only if the data is available in advance. Furthermore, in some cases it may be wasteful if we don't need _all_ of the predictions.
* or, it will be required to make online predictions in real time, when a user or autonomous system is waiting for its response. 

and we further noted that the model serving service may live in the cloud (in which case it is subject to network conditions) or on an edge device (in which case it should be small, and has access to limited compute power).

In developing a model serving design, our goals are usually: low latency (online) or high throughput (batch), low cost, and accurate results. However, we will often have to make compromises in one area to gain an advantage in another.

With this in mind, we described both model-level optimizations and system-level optimizations we could use.

Model-level optimizations:

* The choice of model or foundation model is likely to have the greatest impact on latency and throughput! A smaller model, or a model architecture (e.g. a MobileNet, a YOLO) that is specifically designed for speed, it likely to be much faster than a very large model, but it may be less accurate.
* We said that many of the remamining model-optimizations rely on us first compiling our model into a graph. Then, it becomes possible to apply graph optimizations such as:
  * eliminating operations on constants
  * fusing operations
  * transforming primitives from a less-customized implementation to an implementation that is customized for the specific hardware on which the model will be executed
  * and optimizing these implementations considering factors such as the memory layout or memory access characteristics of the target device. (We looked at one example, from [How to Optimize a CUDA Matmul Kernel for cuBLAS-like Performance: a Worklog](https://siboehm.com/articles/22/CUDA-MMM)).
* We also consider quantization or reduced precision: either quantization aware training or post-training quantization (and, it can be static or dynamic).
* and finally, we mentioned two other model-level optimizations: pruning and knowledge distiillation.

System-level optimizations:

* We mentioned warm start vs cold start, which is typically a cost vs latency tradeoff.
* We discussed concurrent model execution, both of different models and parallel instances of the same model.
* We talked about dynamic batching.
* and, ensembling models that perform a task together.

Finally, we shifted gears and used [LyftLearn Serving](https://eng.lyft.com/powering-millions-of-real-time-decisions-with-lyftlearn-serving-9bb1f73318dc) as an example to talk about what an organization would want out of a model serving *platform*:

* support many different ML frameworks, 
* isolate different models owned by different teams, so that they do not affect one another,
* and make it easy for ML teams to create a deployment that will perform well for their particular model and use case, e.g. with customized templates.

[Slides: Model serving](https://link.excalidraw.com/p/readonly/65nXMf00Qfu3mhUr4eDv){: .btn .btn-purple }


## Lab assignment

Due 3/20
{: .label .label-yellow}

This lab assignment is in three parts:

[Lab: Part 1: Model optimizations for serving](https://teaching-on-testbeds.github.io/serve-model-chi/){: .btn .btn-green } 
[Lab: Part 2: Serving models on edge devices](https://teaching-on-testbeds.github.io/serve-edge-chi/){: .btn .btn-green } 
[Lab: Part 3: System optimizations for serving](https://teaching-on-testbeds.github.io/serve-system-chi/){: .btn .btn-green }

The first part ("Model optimizations") should be completed first; then you can do the second and third parts in any order.

You will submit screenshots and answer questions about this assignment in Gradescope. The link to the Gradescope submission is in Brightspace. You should review the Gradescope assignment before you begin, so that you know in advance exactly what you will need to submit.

{:.important }
> Resource usage notes for this lab assignment:
> 
> * For this experiment, you will need to reserve time on a GPU node in advance. There is certainly not enough capacity for the entire class, or even a substantial fraction of the class, to access these resources in the last few days before the deadline, so you should not anticipate that you can do this lab just before it is due. It is your responsibility to plan ahead, make an advance reservation, and use that time effectively.
> * For the first part, "Model optimizations for serving", you will need a 3-hour block on a `compute_liqid` node type at CHI@TACC, or `compute_gigaio` node type at CHI@UC. These are subject to contention with other Chameleon users, so you should make a reservation right away.
> * For the second part, "Serving on edge devices", you will reserve a 2-hour block on a Raspberry Pi 5 device on CHI@Edge. 
> * For the third part, "System optimizations for serving", you will need a 3-hour block on a `gpu_p100` node type at CHI@TACC. These are subject to contention with other Chameleon users.


