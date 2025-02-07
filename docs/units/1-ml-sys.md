---
title: Machine learning systems
layout: page
parent: Units
nav_order: 1
---


# Machine learning systems


In this week's lecture, we identified some differences between a prototype or proof-of-concept machine learning system and a production system, with respect to:

* Scale: this one is obvious! A production system will typically be serving many users.
* Data: in our simple prototypes we used "toy" data that was readily available. In a production system, a big part of the work is creating the data. We also care a lot more about data quality, identifying edge cases, identifying "slices" of interest, etc. And, we noted that the data in a production system is dynamic, while the prototype was built with a static dataset.
* Privacy, fairness, interpretability: tend to be de-emphasized in a prototype, but are much more important in production.
* System type: a prototype is likely to be a single monolithic model, in production a model will likely be part of a composed system with multiple models.
* Objective: in a prototype, it's enough to score well on a "machine learning metric", but in a production system, we need a value proposition that relates to the business interest, and we need to do better than the status quo baseline on the relevant business KPIs - enough to outweigh the cost.

In a production machine learning system, we will want to iterate on the data and on the model. If we approach this the way we built the prototypes, it would be very expensive (in person-hours) to update the system. To make it less expensive, we need an automated pipeline.

For the rest of the semester, we will consider this entire pipeline - not just the model itself - as the overall machine learning system.

Our goal is to learn how to build reliable, scalable, high-quality pipelines. We said that this is not an easy task - 

* Machine learning pipelines in particular tend to accrue lots of technical debt. (Technical debt: there is a conflict between moving fast and engineering quality, and when you choose to move fast, you will have to "pay it back" later by refactoring etc.) (This idea was introduced in a 2015 NeurIPs paper linked in the [Reading](#reading) section, that in some ways is considered to have launched the field of "MLOps".) 
* Large scale machine learning systems can fail in ML-specific ways, but they can *also* fail (and often do!) in any of the typical "large scale distributed systems" ways.  (Refer to the presentation linked in the [Reading](#reading) section. )

We identified some qualities that we will want to have in virtually any machine learning pipeline:

* **velocity**: we want to be able to iterate quickly and experiment easily on the data and model.
* **validation**: we want to find problems as early as possible (before they become more expensive!).
* **versioning**: we want to be able to revert to specific/older versions of data, model, or configurations, as needed.

but we said that the other details of the pipeline need to be responsive to the specific use case. Some questions to consider include: 

* What kind of data do we have available?
* How much data do we have? 
* Where is the data?
* Who is going to use the output and how? 
* How many concurrent users/predictions should we serve? 
* What are the best metrics to evaluate the system?
* How important is explainability? 
* What are the privacy and fairness concerns?
* How fast do things change? 
* What compute resources are available?

The same underlying prediction (e.g., recommending movies to users) will be realized in a very different *system* depending on the answers to these questions.

Engineering a machine learning system involves defining the interfaces, algorithms, data, and hardware necessary for it to satisfy use-case-specific requirements including: reliability, cost, maintainability, and many others. In this course, we'll look at each part of the pipeline in turn, and learn about some components we can use to address system-level challenges at that stage.

[Slides: Machine learning systems](https://link.excalidraw.com/p/readonly/UV8Ez1d9Tc1wLE5vIsLY){: .btn .btn-purple }


## Lab assignment

Due 1/30 
{: .label .label-blue}

{:.warning }
There is a planned outage on KVM@TACC on 1/28, for upgrades and maintenance. You should plan to do the lab assignment on a different day, since KVM@TACC will not be available on 1/28.

This week's lab assignment is:

[Lab manual: Hello, Chameleon](https://teaching-on-testbeds.github.io/hello-chameleon/){: .btn .btn-green }


You won't submit anything for this assignment, but you will need to have done this in order to do the following lab assignments. Since it requires a human-in-the-loop approval step, it's important to get it done right away, rather than when you absolutely need your account to be ready to go.

You will need the project "join link" to finish this assignment - it is posted in Brightspace.

If you have done "Hello, Chameleon" already in a previous course, you will just need to 

* join the project for _this_ course, using the link in Brightspace
* and make sure you can still access the keys associated with your Chameleon profile.

{:.important }
> Resource usage notes for this lab assignment:
> * You should plan to start and finish the assignment within a six-hour period - so block some time accordingly. Your resource may not be "active" for more than six hours. It may be deleted by course staff if it is active for longer than six hours.
> * Delete your compute instance as soon as you are done with the experiment, to free the resources for other students.



## Reading

In this week's lecture, we referred to a case study on a Norwegian grocery delivery service, Oda, to better understand how a machine learning system might be developed to support a real business need. Here are the details:

* [Part 1: How we went from zero insight to predicting service time with a machine learning model](https://medium.com/oda-product-tech/how-we-went-from-zero-insight-to-predicting-service-time-with-a-machine-learning-model-part-1-516b9545d02f)
* [Part 2: How we went from zero insight to predicting service time with a machine learning model](https://medium.com/oda-product-tech/how-we-went-from-zero-insight-to-predicting-service-time-with-a-machine-learning-model-part-2-2-ad8b0c3e4838) 


You should also read - 

* The classic "technical debt" paper: D. Sculley, Gary Holt, Daniel Golovin, Eugene Davydov, Todd Phillips, Dietmar Ebner, Vinay Chaudhary, Michael Young, Jean-Francois Crespo, and Dan Dennison. 2015. Hidden technical debt in Machine learning systems. In Proceedings of the 29th International Conference on Neural Information Processing Systems - Volume 2 (NeurIPS'15), Vol. 2. MIT Press, Cambridge, MA, USA, 2503–2511. [Link](https://proceedings.neurips.cc/paper/2015/hash/86df7dcfd896fcaf2674f757a2463eba-Abstract.html).
* and the one about failures in large ML pipelines:  Daniel Papasian, Todd Underwood. 2020. How ML Breaks: A Decade of Outages for One Large ML Pipeline. In Proceedings of the 2020 USENIX Conference on Operational Machine Learning (OpML '20). [Link](https://www.usenix.org/conference/opml20/presentation/papasian).
* the "3 Vs" of operational machine learning came from an interview study that you may find interesting: Shreya Shankar, Rolando Garcia, Joseph M. Hellerstein, Aditya G. Parameswaran. 2022. Operationalizing Machine Learning: An Interview Study. [arXiv:2209.09125](https://arxiv.org/abs/2209.09125).
