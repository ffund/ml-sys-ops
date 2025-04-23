---
title: DevOps for ML
layout: page
parent: Units
nav_order: 3
---


# DevOps for ML systems


In this week's lecture, we reviewed some of the basic ideas of DevOps:

* Continuous integration/continuous delivery
* Version control for everything
* Infrastructure as code
* Proactive monitoring and logging

and we discussed how use of DevOps practices can increase deployment frequency, and decrease lead time for changes, change failure rate, and time to restore service.

We also described some ideas of cloud native computing, which marries DevOps and cloud computing.

Although DevOps has well-developed ideas for managing code and infrastructure, we noted that it does not necessarily have them for models and data, which are an integral part of machine learning systems. Thus, the need for MLOps, which is: DevOps + the application of DevOps ideas to models and data.

We introduced a MLOps lifecycle for a machine learning system, and then we discussed (with reference to Uber as a case study) the core organization capabilities that would be needed to support this lifecycle across many teams and models within the organization.

Finaly, we reviewed the first few stages of the lifecycle in more depth - 

* what happens in that stage
* the inputs and outputs of that stage
* and the core organization capabilities it relies on.

For the rest of the semester, we'll work with a different one of those core organization capabilities in each unit.

[Slides: DevOps for ML systems](https://link.excalidraw.com/p/readonly/xduAEWPqHPv6IqHAOACz){: .btn .btn-purple }

## Lab assignment

Due 4/29
{: .label .label-yellow}

[Lab: Build an MLOps pipeline](https://teaching-on-testbeds.github.io/mlops-chi/){: .btn .btn-green }

{:.important }
> Resource usage notes for this lab assignment:
> 
> * You will do this lab assignment on KVM@TACC, which does not require reservation.
> * You can do the parts in any order, but you should only do one at a time - you must delete resources from a previous part before you start another part.
> * Your resources may not be "active" for more than eight daytime (8AM - 11:59PM) hours. They may be deleted by course staff otherwise.
> * Delete your compute instance as soon as you are done with the experiment, to free the resources for other students.


## Reading



* Most of this lesson is based on: Khalid Salama, Jarek Kazmierczak, Donna Schut. "Practitioners guide to MLOps: A framework for continuous delivery and automation of machine learning." Google Cloud Whitepaper, May 2021. [PDF](https://services.google.com/fh/files/misc/practitioners_guide_to_mlops_whitepaper.pdf)

* We also discussed a case study: Jeremy Hermann. "Meet Michelangelo: Uber’s Machine Learning Platform". Uber blog, September 2017. [URL](https://www.uber.com/blog/michelangelo-machine-learning-platform/)
