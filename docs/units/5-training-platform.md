---
title: Model training infrastructure and platform
layout: page
parent: Units
nav_order: 5
---

# Model training infrastructure and platform

Last week, we introduced techniques for training very large models. This week, we discussed the infrastructure and platform requirements to support that type of large model training, as well as to support the training of many models by many teams. We focused specifically on experiment tracking, versioning and reproducibility, and scheduling training jobs.

Using OPT-175B as an example, we identified some of the things we would need in an experiment tracking service:

* Save details of every run, including model checkpoints, hyperparameters, and code version.
* Monitor ML measures (e.g. loss).
* Monitor infrastructure and system health, including hardware and software systems required for training.

Then, we discussed requirements for a ML training job scheduler:

* Allocate resources effectively, in a way that is aligned with business priorities but also avoids underutilization.
* Usability, flexibility, and observability for users and adminstrators.

and we introduced some scheduling and placement policies, most of which originated in the world of high performance computing.

[Slides: Model training infrastructure and platform](https://link.excalidraw.com/p/readonly/ljOHwbv4f6bOovUeqAZJ){: .btn .btn-purple }


## Lab assignment

Due 3/13
{: .label .label-yellow}

[Lab: Train ML models with MLFlow and Ray](https://teaching-on-testbeds.github.io/mltrain-chi/){: .btn .btn-green }

You will submit screenshots and answer questions about this assignment in Gradescope. The link to the Gradescope submission is in Brightspace. You should review the Gradescope assignment before you begin, so that you know in advance exactly what you will need to submit.

{:.important }
> Resource usage notes for this lab assignment:
> 
> * For this experiment, you will need to reserve time on a GPU node in advance. There is certainly not enough capacity for the entire class, or even a substantial fraction of the class, to access these resources in the last few days before the deadline, so you should not anticipate that you can do this lab just before it is due. It is your responsibility to plan ahead, make an advance reservation, and use that time effectively.
> * Read the rest of these resource usage notes, then refer to the first section of the lab manual for instructions on making a reservation.
> * You will need a 3-hour block for each section of the experiment (MLFlow, Ray). Start each lease on hour boundaries, and end your lease five minutes before the hour boundary, since this simplifies scheduling (e.g. start at XX:00 and end at YY:55, where YY = XX + 3). Avoid leaving 1-hour or 2-hour gaps between your lease and a previous or later lease, since this time may not be usable.
> * We are anticipating a brief outage of the Chameleon Jupyter service on March 3. However, instructions are also provided to bring up your resources using the Horizon GUI, so you can still work on the lab during this outage.

Note on completing the experiment in two separate blocks of time:

When you are working on the MLFlow section, you will do the following parts. (The estimated time is assuming you have read through the material in advance.)

  * 1: Launch and set up server (one version - depending on which type of GPU you reserved) (takes ~30-45 minutes, not including building the container image which runs in the background as you continue)
  * 2: Prepare data (~10 minutes)
  * 3: Start the tracking server (takes ~30 minutes)
  * 4: Track a Pytorch experiment (takes ~45 minutes)
  * 5: Track a Lightning experiment (takes ~40 minutes)
  * 6: Use MLFlow outside of training runs (takes ~5 minutes)

When you are working on the Ray section, you will do the following parts. (The estimated time is assuming you have read through the material in advance.)

  * 1: Launch and set up server (one version - depending on which type of GPU you reserved). (Skip the "Build a container image" cell at the end, which is only for the MLFlow section.) (takes ~30-45 minutes)
  * 2: Prepare data (~10 minutes)
  * 7: Start the Ray cluster (~10 minutes on NVIDIA, ~20 minutes on AMD)
  * 8: Submit jobs to the Ray cluster (~90 minutes)


## Reading

This week, we discussed three case studies:

* The training of OPT-175B at Meta. We referred to the training [logbook](https://github.com/facebookresearch/metaseq/tree/main/projects/OPT/chronicles) and watched some of [this video with Susan Zhang](https://www.youtube.com/watch?v=p9IxoSkvZ-M).
* We read [Scaling ML Training at Nuro](https://medium.com/nuro/introduction-to-nuro-ml-scheduler-fc03d3f8c8ea).
* Our third case study was about Alibaba. We looked at the paper: Qizhen Weng, Wencong Xiao, Yinghao Yu, Wei Wang, Cheng Wang, Jian He, Yong Li, Liping Zhang, Wei Lin, and Yu Ding, "MLaaS in the Wild: Workload Analysis and Scheduling in Large-Scale Heterogeneous GPU Clusters" in NSDI '22. [Link to paper and presentation video](https://www.usenix.org/conference/nsdi22/presentation/weng) 

In this week's lab, we'll work with:

* MLFlow: refer to
  * Matei Zaharia, Andrew Chen, Aaron Davidson, Ali Ghodsi, Sue Ann Hong, Andy Konwinski,
Siddharth Murching, Tomas Nykodym, Paul Ogilvie, Mani Parkhe, Fen Xie, Corey Zumar, "Accelerating the Machine Learning Lifecycle with MLflow" in the 2018 Bulletin of the IEEE Computer Society Technical Committee on Data Engineering. [PDF](https://people.eecs.berkeley.edu/~matei/papers/2018/ieee_mlflow.pdf)
  * Andrew Chen, Andy Chow, Aaron Davidson, Arjun DCunha, Ali Ghodsi, Sue Ann Hong, Andy Konwinski, Clemens Mewald, Siddharth Murching, Tomas Nykodym, Paul Ogilvie, Mani Parkhe, Avesh Singh, Fen Xie, Matei Zaharia, Richard Zang, Juntai Zheng, Corey Zumar, "Developments in MLflow: A System to Accelerate the Machine Learning Lifecycle" in DEEM ’20. [PDF](https://people.eecs.berkeley.edu/~matei/papers/2020/deem_mlflow.pdf)

* and Ray: refer to
  * Philipp Moritz, Robert Nishihara, Stephanie Wang, Alexey Tumanov, Richard Liaw, Eric Liang, Melih Elibol, Zongheng Yang, William Paul, Michael I. Jordan, and Ion Stoica, "Ray: A Distributed Framework for Emerging AI Applications" in OSDI '18. [Link](https://www.usenix.org/conference/osdi18/presentation/moritz)
  * and the [Ray 2.0 Architecture Whitepaper](https://docs.google.com/document/d/1tBw9A4j62ruI5omIJbMxly-la5w4q_TjyJgJL_jN2fI/preview)
