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

Due 2/20
{: .label .label-yellow}

The lab assignment will be released in the first half of next week.

<!-- 
This week's lab assignment is:

[Lab manual: Deploy a Continuous X Pipeline for an ML System](){: .btn .btn-green }

You will submit screenshots and answer questions about this assignment in Gradescope. The link to the Gradescope submission is in Brightspace. You should review the Gradescope assignment before you begin, so that you know in advance exactly what you will need to submit.

{:.important }
> Resource usage notes for this lab assignment:
> 
> * You should plan to start and finish the assignment within one or two eight-hour periods - so block some time accordingly. Your resources may not be "active" for more than eight daytime (8AM - 11:59PM) hours. They may be deleted by course staff otherwise.
> * If your net ID ends in an even number (0, 2, 4, 6, 8) you may bring up your cluster on Chameleon on Saturday, Monday, or Wednesday before the due date. 
> * If your net ID ends in an odd number (1, 3, 5, 7, 9) you may bring up your cluster on Chameleon on Friday, Sunday, Tuesday, or Thursday before the due date.  
> * (For the next assignment, the odds and evens will swap weekdays.)
> * You can use more than one of "your" days, if you need to.
> * Overnight hours from midnight to 8AM are "free" - anyone may use them, regardless of the day of the week.
> * Delete your compute instance as soon as you are done with the experiment, to free the resources for other students.

-->

## Reading



* Most of this lesson is based on: Khalid Salama, Jarek Kazmierczak, Donna Schut. "Practitioners guide to MLOps: A framework for continuous delivery and automation of machine learning." Google Cloud Whitepaper, May 2021. [PDF](https://services.google.com/fh/files/misc/practitioners_guide_to_mlops_whitepaper.pdf)

* We also discussed a case study: Jeremy Hermann. "Meet Michelangelo: Uber’s Machine Learning Platform". Uber blog, September 2017. [URL](https://www.uber.com/blog/michelangelo-machine-learning-platform/)
