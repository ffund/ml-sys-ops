---
title: Project
layout: page
nav_order: 3
---

# Project
{: .no_toc }


For your course project, you will design and implement a medium-scale ML system. In your project, you must use the techniques discussed in our lectures to address some of the challenges *also* discussed in those lectures.

1. TOC
{:toc}



## Group work expectations

You will complete these projects in groups of 3 or 4, where:

* certain elements of the project are going to be "owned" by all group members: the idea and the value proposition, the basic setup of the ML problem (what is the data, what is the target variable, etc.), the approach that the group will take for each part, and the overall integration of all of the parts.
* other parts of the project are going to be "owned" by individual group members: 
  1. one group member must "own" the model training part (using units 4 and 5)
  2. the second group member must "own" the model serving (unit 6) and monitoring (unit 7) part
  3. the third group member must "own" the data pipeline (unit 8)
  4. if you are a group of four: another group member must "own" the continuous X pipeline (unit 3). If you are a group of three, the continuous X pipeline is jointly developed by all three group members, where each group member takes responsibility for the part of the continuous X pipeline that relates to their other role on the project.

Part of your project grade will be common to the entire group, based on the "jointly owned" elements; part of your project grade will be individual, based on the work you have produced in your personal role.

## Project deliverables and deadlines

You will submit project deliverables in two stages:

Due 4/3 
{: .label .label-yellow}

Midway through the course, you will submit a project proposal, including:

* a "lightning" presentation describing the system you will build
* a document detailing how your project meets the requirements

Due 5/1
{: .label .label-yellow}

At the end of the course, your final submission will include:

* a Git repository with all of the materials necessary to reproduce your work
* a document describing the details of your system
* and a presentation


## Project requirements

For each unit of the course,

* we will identify specific requirements that your project *must* satisfy, related to that unit
* and we will identify some requirements that your project *may* satisfy, for "difficulty points". Your project is required to meet an overall "difficulty threshold".

The per-unit project requirements will be posted here each week, after the lecture.


### Unit 1: Machine learning systems

Requirements that your project *must* satify:

- [ ] **Scale**: Your project must be at least *medium*-scale in each of these areas: (1) data, (2) model (either have one very large model or a system composed of several smaller models), and (3) deployment.
- [ ] **Value proposition**: You will propose a machine learning system that can be used in an existing business or service. (You should not propose a system in which a *new* business or service would be developed around the machine learning system.) Describe the value proposition for the machine learning system. What's the (non-ML) status quo used in the business or service? What business metric are you going to be judged on? (Note that the "service" does not have to be for general users; you can propose a system for a science problem, for example.)
- [ ] **Outside materials**: You are probably going to use outside materials that you did not create - almost definitely data, and depending on the project, you may use a foundation model or an embedding model. For any outside materials you use, you need to understand and document their lineage and the conditions of their use. For example, if you are using a data set: who created this data set, and when? Under what conditions was it collected? (Is there an academic paper documenting its collection?) Are there privacy, fairness, and/or ethics concerns underlying its use? Is the version of the data we are using pre-processed in any way? Under what conditions is it legally allowed to be used (what is the license)? etc.

For extra "difficulty points":

- [ ] **Composed of multiple models**: Your system may be composed of three or more machine learning models that work together (not just in parallel!), in order to realize some goal that cannot be achieved with fewer models.

### Unit 2: Cloud computing

Requirements that your project *must* satify:

- [ ] **Infrastructure**: Your project will run on the Chameleon infrastructure. (Although we will practice using some commercial clouds later in the semester, we want our project to run on Chameleon.)
- [ ] **Cloud-native**: You will be expected to develop your project as a "cloud-native" service, but we'll discuss what this means specifically in Unit 3.

### Unit 3: DevOps

Requirements that your project *must* satify:

- [ ] **Infrastructure-as-code**: You will avoid ClickOps in provisioning your infrastructure. Instead, you'll define your infrastructure configuration in version control using either a declarative style (like Terraform, which we use in Lab 3) or imperative style (like `python-chi`, used in many other labs). This configuration must live in Git. You will similarly avoid manual installation and configuration of your infrastructure, once it is deployed. Instead, you can use a combination of automation tools like Ansible (used in Lab 3), ArgoCD (used in Lab 3), Argo Workflows (used in Lab 3), Helm, `python-chi`, and/or other tools to set up your infrastructure. Like your infrastructure configuration, these service and software configurations similarly must live in Git.

- [ ] **Cloud-native**: You will be expected to develop your project as a "cloud-native" service. This means: (1) Immutable infrastructure: you avoid manual changes to infrastructure that has already been deployed. Instead, make changes to your configurations in Git, and then bring up your new infrastructure directly from these configurations. (2) Microservices: to the extent that is reasonable, deploy small independent pieces that work together via APIs, but are managed separately. (3) Containers as the smallest compute unit: you will containerize all services, so they can be deployed and scaled efficiently. You won't run anything (except building and managing containers!) directly on compute instances. 

- [ ] **CI/CD and continuous training**: You will define an automated pipeline that, in response to a trigger (which may be a manual trigger, a schedule, or an external condition, or some combination of these), will: re-train your model, run the complete offline evaluation suite, apply the post-training optimizations for serving, test its integration with the overall service, package it inside a container for the deployment environment, and deploy it to a staging area for further testing (e.g. load testing). 

- [ ] **Staged deployment**: You will configure a "staging", "canary", and "production" environment in which your service may be deployed. You will also implement a process by which a service is promoted from the staging area to a canary environment, for online evaluation; and a process by which a service is promoted from canary to production.



<!--

- [ ] **Demo UI**: This isn't a frontend course, but you will need some sort of demo UI in front of your service. [Streamlit](https://github.com/streamlit/streamlit) and [Gradio](https://github.com/gradio-app/gradio) are popular options for putting together a quick demo.
-->


### Unit 4: Model training at scale

Requirements that your project *must* satify:

- [ ] **Train and re-train**: You must train and re-train at least one model. (Your project may additionally use other models without training, but you have to train *something* and then be able to re-train it on production data.)
- [ ] **Modeling**: You must make reasonable, appropriate, and well-justified choices for modeling.

For extra "difficulty points":

- [ ] **Training strategies for large models**: If your training job does not easily fit on a low-end GPU, you will use the strategies discussed in this lesson to train your model. For your reports, you will conduct experiments and show measurements similar to those in the lab assignment, to evaluate the effect of these strategies.

- [ ] **Use distributed training to increase velocity**: If you have a medium-sized training job, how fast can you train your model? Include a discussion (backed up by experiment results!) of total model training time with one GPU vs. multiple GPUs of the same type, using the strategy (DDP, FSDP, and appropriate batch size) that makes the most sense given the size of your model. You will include a plot of training time vs. number of GPUs for each strategy under consideration.

### Unit 5: Model training infrastructure and platform

Requirements that your project *must* satify:

- [ ] **Experiment tracking**: In your project proposal, you will describe the model training experiments that you *plan* to run. Then, when working on your project, you will host an experiment tracking server on Chameleon, and instrument your training code with logging calls, so that the details of all experiments are stored on your tracking server. (You may use [MLFlow](https://mlflow.org/docs/latest/index.html), like in the lab, or you can host your own [`wandb`](https://docs.wandb.ai/guides/hosting/hosting-options/self-managed/), or you can use another experiment tracking server; but you must host it yourself on Chameleon.) 
- [ ] **Scheduling training jobs**: You will run a Ray cluster, like in the lab, and submit training jobs to it as part of your continuous training pipeline.

For extra "difficulty points":

- [ ] **Using Ray Train**: Use Ray Train to execute your training job with features like fault tolerance, checkpointing to remote object storage, etc.

- [ ] **Scheduling hyperparameter tuning jobs**: Use Ray Tune for hyperparameter tuning, and use its advanced tuning algorithms to tune more efficiently.

### Unit 6: Model serving

Requirements that your project *must* satisfy:

- [ ] **Serving from an API endpoint**: You must wrap your model in an API endpoint for serving. (If you implement a front end, it will call your API.)
- [ ] **Identify requirements**: You will identify specific requirements in terms of model size, throughput for batch inference, and/or latency for online (single sample) inference that are aligned with the business use case. For cloud (i.e., not on-device) deployments, you should also identify a concurrency requirement.
- [ ] **Model optimizations to satisfy requirements**: You will explore the use of model-level optimizations, potentially including graph optimizations, quantization or reduced precision, use of operators that are optimized for a specific hardware backend, or other optimizations of your choice. In your final report, you will discuss these optimizations, and their effect on inference performance.
- [ ] **System optimizations to satisfy requirements**: For cloud (i.e., not on-device) deployments, you will explore the use of system-level optimizations to support the required degree of concurrency while still satisfying latency requirements. In your final report, you will discuss these optimizations, and their effect on inference performance.

For extra "difficulty points":

- [ ] **Develop multiple options for serving**: If you are using a model that benefits from using GPU for inference, you can get "extra difficulty points" by developing and evaluating optimized server-grade GPU, server-grade CPU, and on-device options for model serving, and comparing them with respect to performance and cost of deployment on a commercial cloud.

### Unit 7: Evaluation and monitoring

Requirements that your project *must* satisfy:

- [ ] **Offline evaluation of model**: You will define an automated offline evaluation plan, and it will run immediately after model training with results logged to MLFlow. Your offline evaluation must include: (A) evaluation on appropriate "standard" and "domain specific" use cases for your particular model (2) evaluation on populations and slices of special relevance, including an analysis of fairness and bias if relevant (3) test on known failure modes (4) and, unit tests based on templates. Depending on the test results, you will automatically register an updated model in the model registry, or not.

- [ ] **Load test in staging**: Once your "Continuous X" pipeline has deployed the service to a staging area, you should conduct a load test on it, and surface the results. (This load test may also be part of the "continuous X" pipeline.)

- [ ] **Online evaluation in canary**: When your service is ready to deploy to a canary environment (i.e. it has passed tests in staging), you will conduct an online evaluation (like in Lab 7) with artificial "users". (You yourself will "be" the users; you should prepare a plan as to how you will represent the range of real users and user behaviors you might encounter in a real deployment.)

- [ ] **Close the loop**: Implement a means by which you get feedback about the quality of your model's predictions in productions; whether this is with explicit user feedback, human annotators, or natural ground truth labels. Also, during production, you will save some portion of production data, label it, and use it for re-training on updated data. 

- [ ] **Define a business-specific evaluation**: Although you will not be able to realize this plan, because your system will not really be deployed to users as part of a production service, you should define a business-specific evaluation plan with respect to *business metrics*, and explain how you will measure this in production.

For extra "difficulty points":

- [ ] **Monitor for data drift**: After your model is deployed in production, monitor for data drift and label drift, and make this available to engineers (e.g. in a dashboard).

- [ ] **Monitor for model degradation**: After your model is deployed in production, monitor for degradation in the model output (by closing the feedback loop!). Make this available to engineers (e.g in a dashboard), and trigger automatic re-training with new, labeled, production data when this occurs.

### Unit 8: Data pipeline


Requirements that your project *must* satisfy:

- [ ] **Persistent storage**: Following the example of Lab 8, you will provision persistent storage on Chameleon, which may be attached to and detached from your infrastructure. This will store all materials that should persist for the duration of the project, but are not tracked in Git: model training artifacts, test artifacts, models, container images, data, etc.

- [ ] **Offline data**: You will set up and manage all the offline data used by your service, e.g. data used for training and re-training, keeping it in an appropriate data repository depending on whether it is structured data, unstructured data, or both. 

- [ ] **Data pipelines**: You will define ETL pipeline(s) for ingesting new data either from external sources or your production service, processing it (e.g. cleaning it), and loading it into your data repository so that is is ready for model training. Your project proposal should define all data sources, and the steps required to transform them and load them into your data repository.

- [ ] **Online data**: You will set up and manage a streaming data pipeline to manage the online data, e.g. for inference, including similar cleaning and processing steps. You will also need to *simulate* online data: you will write a script to generate real-time data for your service, similar to what it could be expected to see in production use. As part of your project proposal, you should describe the characteristics of this simulated data in detail.

For extra "difficulty points":

- [ ] **Interactive data dashboard**: Implement an interactive and comprehensive data dashboard, that members of the team can use to get high-level insight into the data and data quality.


### "Difficulty points" 

- [ ] In addition to the requirements that you *must* satisfy, your project should:

  * if you are a 3-person team: check off two of the "extra difficulty points" options, and they should be from two different units.
  * if you are a 4-person team: check off four of the "extra difficulty points" options, and they should be from three or four different units.

## Project proposal template

```

## Title of project

<!-- 
Discuss: Value proposition: Your will propose a machine learning system that can be 
used in an existing business or service. (You should not propose a system in which 
a new business or service would be developed around the machine learning system.) 
Describe the value proposition for the machine learning system. What’s the (non-ML) 
status quo used in the business or service? What business metric are you going to be 
judged on? (Note that the “service” does not have to be for general users; you can 
propose a system for a science problem, for example.)
-->

### Contributors

<!-- Table of contributors and their roles. 
First row: define responsibilities that are shared by the team. 
Then, each row after that is: name of contributor, their role, and in the third column, 
you will link to their contributions. If your project involves multiple repos, you will 
link to their contributions in all repos here. -->

| Name                            | Responsible for | Link to their commits in this repo |
|---------------------------------|-----------------|------------------------------------|
| All team members                |                 |                                    |
| Team member 1                   |                 |                                    |
| Team member 2                   |                 |                                    |
| Team member 3                   |                 |                                    |
| Team member 4 (if there is one) |                 |                                    |



### System diagram

<!-- Overall digram of system. Doesn't need polish, does need to show all the pieces. 
Must include: all the hardware, all the containers/software platforms, all the models, 
all the data. -->

### Summary of outside materials

<!-- In a table, a row for each dataset, foundation model. 
Name of data/model, conditions under which it was created (ideally with links/references), 
conditions under which it may be used. -->

|              | How it was created | Conditions of use |
|--------------|--------------------|-------------------|
| Data set 1   |                    |                   |
| Data set 2   |                    |                   |
| Base model 1 |                    |                   |
| etc          |                    |                   |


### Summary of infrastructure requirements

<!-- Itemize all your anticipated requirements: What (`m1.medium` VM, `gpu_mi100`), 
how much/when, justification. Include compute, floating IPs, persistent storage. 
The table below shows an example, it is not a recommendation. -->

| Requirement     | How many/when                                     | Justification |
|-----------------|---------------------------------------------------|---------------|
| `m1.medium` VMs | 3 for entire project duration                     | ...           |
| `gpu_mi100`     | 4 hour block twice a week                         |               |
| Floating IPs    | 1 for entire project duration, 1 for sporadic use |               |
| etc             |                                                   |               |

### Detailed design plan

<!-- In each section, you should describe (1) your strategy, (2) the relevant parts of the 
diagram, (3) justification for your strategy, (4) relate back to lecture material, 
(5) include specific numbers. -->

#### Model training and training platforms

<!-- Make sure to clarify how you will satisfy the Unit 4 and Unit 5 requirements, 
and which optional "difficulty" points you are attempting. -->

#### Model serving and monitoring platforms

<!-- Make sure to clarify how you will satisfy the Unit 6 and Unit 7 requirements, 
and which optional "difficulty" points you are attempting. -->

#### Data pipeline

<!-- Make sure to clarify how you will satisfy the Unit 8 requirements,  and which 
optional "difficulty" points you are attempting. -->

#### Continuous X

<!-- Make sure to clarify how you will satisfy the Unit 3 requirements,  and which 
optional "difficulty" points you are attempting. -->


```

## How to submit your project proposal

Proposal document:

* First, create a Github repository for your project, with a README and an appropriate license. Add all team members as contributors, and also add me (`ffund`) as a contributor.
* Copy the project proposal template into the `README.md`, and modify the template to fill in the details of your project.
* This is due at midnight on 4/3.

Lightning presentation:

* Prepare a single slide with the name of your project, names of all team members, and the diagram from your project proposal. You will submit this as a PDF in Brightspace, due at midnight on 4/2.
* On 4/3, one member of your team will have a 60-second slot to present your project proposal in class.
* During the lightning presentations, pay attention to the other teams' presentations, and note any teams using similar ideas or techniques. You should open a line of dialogue with these teams, so that you can help each other out as you work to implement your projects in the final month of the semester!


## Using resources on Chameleon

As you know, your projects will be developed, hosted, and evaluated entirely on Chameleon. The only external hosted service you are permitted to use is Github (for version control and source code hosting only; you are *not* allowed to use Github-hosted runners for CI actions, for example), and potentially external data APIs.

Please follow these guidelines when using resource on Chameleon:

* **Naming convention**: Whenever you create a resource (including: VMs, bare metal compute instances, bare metal leases, edge device containers, edge device leases, block storage volumes, object store containers), give it a name that ends in the word "project" and your project number. For example, if I am in project group 0, I might launch a VM instance named "node1-project0". This is how you will protect your resources from premature deletion (since I proactively delete resources used for lab assignments!)
* **Lifecycle of compute resources**: You should not expect to persist *any* compute resources for the duration of the entire project! Once you have a data pipeline involving persistent storage + you have automated the infrastructure provisioning and bootstrapping process, then it becomes easy to bring up compute when you plan to actually work on it, and free up the compute when you are not activey working. For bare metal resources, see the guidelines below. For VM resources, you should not plan to leave these alive longer than one day at a time.
* **Lifecycle of network resources**: You *can* keep a private network alive for the duration of the project, so that you can attach and detach VMs easily as you launch/delete them. Within a project group, you should not use more than one floating IP per site at a time.
* **Persistent storage**: In many cases, you can use less persistent storage and also be more efficient by improving your data pipeline to include pre-training transformations such as resizing, that reduce the size of the data. If you are working with a very large data set, you should use this approach, mostly for your own sanity.

Some bare metal GPU resources are reserved for use by our class as a group, starting 4/12 through at least 5/1 (some extending a bit beyond this). You may use them as follows:

* A variable number of `gpu_rtx6000` nodes at CHI@UC, which each have one RTX6000 NVIDIA GPU. You may use these for general model training or inference jobs. 
* Four `compute_liqid` nodes at CHI@TACC, which each have an A100 40GB NVIDIA GPU. You may use these for general model training or inference jobs, especially if your inference job involves an NVIDIA Triton service. 
* Two `gpu_mi100` nodes at CHI@TACC, which each have 2 MI100 AMD GPUs. You may use these for general model training or inference jobs.
* A variable number of `compute_gigaio` nodes at CHI@UC, which each have one A100 80GB NVIDIA GPU. Use these for model training or inference jobs with very large models, where it is not practical to use a GPU with less memory.
* A `gpu_a100_pcie` (either `J0BG3Q3` or `307G3Q3`) at CHI@UC. These are 4x A100 80GB NVIDIA GPU nodes. We have one reserved from 4/12 through 5/6. You should use these only if you are using distributed training to train a very large model that is not practical to train on a single GPU. 

For now, you may reserve up to 6 hours at a time on these bare metal nodes. (Once we get closer to the end of the semester, this time limit will be smaller.)

## What you should be working on now

Updated 4/10 
{: .label .label-yellow}

* **Mode training team member**: develop the model training infrasructure/platform, e.g. the basic setup for experiment tracking. Put together a minimal model for other team members to develop against (for example: your base model with the correct classification head on top, without actually training it).
* **Model serving and evaluation team member**: develop the model serving/evaluation/monitoring platform. Set up a serving endpoint using the minimal model. Start preparing specific data sets for offline evaluations.
* **Data team member**: Prepare the data ingestion pipeline (for some, this is more involved than others). Make sure to set aside some "late" data for evaluation and for simulating production data. Set up persistent storage for other team members to use (block storage for application, object store for large training data sets).
* **Continuous X team member**: Work with other teams to identify infrastructure provisioning and bootstrapping needs, and start to de-duplicate these.