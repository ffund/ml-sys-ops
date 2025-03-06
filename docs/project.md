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
- [ ] **Value proposition**: Your will propose a machine learning system that can be used in an existing business or service. (You should not propose a system in which a *new* business or service would be developed around the machine learning system.) Describe the value proposition for the machine learning system. What's the (non-ML) status quo used in the business or service? What business metric are you going to be judged on? (Note that the "service" does not have to be for general users; you can propose a system for a science problem, for example.)
- [ ] **Outside materials**: You are probably going to use outside materials that you did not create - almost definitely data, and depending on the project, you may use a foundation model or an embedding model. For any outside materials you use, you need to understand and document their lineage and the conditions of their use. For example, if you are using a data set: who created this data set, and when? Under what conditions was it collected? (Is there an academic paper documenting its collection?) Are there privacy, fairness, and/or ethics concerns underlying its use? Is the version of the data we are using pre-processed in any way? Under what conditions is it legally allowed to be used (what is the license)? etc.

For extra "difficulty points":

- [ ] **Composed of multiple models**: Your system may be composed of three or more machine learning models that work together (not just in parallel!), in order to realize some goal that cannot be achieved with fewer models.

### Unit 2: Cloud computing

Requirements that your project *must* satify:

- [ ] **Infrastructure**: Your project will run on the Chameleon infrastructure. (Although we will practice using some commercial clouds later in the semester, we want our project to run on Chameleon.)
- [ ] **Cloud-native**: You will be expected to develop your project as a "cloud-native" service, but we'll discuss what this means specifically in Unit 3.

### Unit 3: DevOps

TBD after the lab assignment is released.

<!-- 

Requirements that your project *must* satify:

- [ ] **Cloud-native**: You will be expected to develop your project as a "cloud-native" service, but we'll discuss what this means specifically in Unit 3.
- [ ] **CI/CD and continuous training**: You will include an automated pipeline that, in response to a trigger, will re-train your model, test its integration with the overall service, package it for the deployment environment, and deploy it to a staging area for further testing.

For extra "difficulty points":

- [ ] **ArgoCD**: [ArgoCD](https://argo-cd.readthedocs.io/en/stable/) is a tool for continuous delivery that is integrated with Kubernetes. 


<!--

- [ ] **Demo UI**: This isn't a frontend course, but you will need some sort of demo UI in front of your service. [Streamlit](https://github.com/streamlit/streamlit) and [Gradio](https://github.com/gradio-app/gradio) are popular options for putting together a quick demo.
-->


### Unit 4: Model training at scale

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

## Project proposal template

```

## Title of project

<!-- 
Discuss: Value proposition: Your will propose a machine learning system that can be used in an existing business or service. (You should not propose a system in which a new business or service would be developed around the machine learning system.) Describe the value proposition for the machine learning system. What’s the (non-ML) status quo used in the business or service? What business metric are you going to be judged on? (Note that the “service” does not have to be for general users; you can propose a system for a science problem, for example.)
-->

### Contributors

<!-- Table of contributors and their roles. First row: define responsibilities that are shared by the team. Then each row after that is: name of contributor, their role, and in the third column you will link to their contributions. If your project involves multiple repos, you will link to their contributions in all repos here. -->

| Name                            | Responsible for | Link to their commits in this repo |
|---------------------------------|-----------------|------------------------------------|
| All team members                |                 |                                    |
| Team member 1                   |                 |                                    |
| Team member 2                   |                 |                                    |
| Team member 3                   |                 |                                    |
| Team member 4 (if there is one) |                 |                                    |



### System diagram

<!-- Overall digram of system. Doesn't need polish, does need to show all the pieces. Must include: all the hardware, all the containers/software platforms, all the models, all the data. -->

### Summary of outside materials

<!-- In a table, a row for each dataset, foundation model. Name of data/model, conditions under which it was created (ideally with links/references), conditions under which it may be used. -->

|              | How it was created | Conditions of use |
|--------------|--------------------|-------------------|
| Data set 1   |                    |                   |
| Data set 2   |                    |                   |
| Base model 1 |                    |                   |
| etc          |                    |                   |


### Summary of infrastructure requirements

<!-- Itemize all your anticipated requirements: What (`m1.medium` VM, `gpu_mi100`), how much/when, justification. Include compute, floating IPs, persistent storage. The table below shows an example, it is not a recommendation. -->

| Requirement     | How many/when                                     | Justification |
|-----------------|---------------------------------------------------|---------------|
| `m1.medium` VMs | 3 for entire project duration                     | ...           |
| `gpu_mi100`     | 4 hour block twice a week                         |               |
| Floating IPs    | 1 for entire project duration, 1 for sporadic use |               |
| etc             |                                                   |               |

### Detailed design plan

<!-- In each section, you should describe (1) your strategy, (2) the relevant parts of the diagram, (3) justification for your strategy, (4) relate back to lecture material, (5) include specific numbers. -->

#### Model training and training platforms

<!-- Make sure to clarify how you will satisfy the Unit 4 and Unit 5 requirements, and which optional "difficulty" points you are attempting. -->

#### Model serving and monitoring platforms

<!-- Make sure to clarify how you will satisfy the Unit 6 and Unit 7 requirements,  and which optional "difficulty" points you are attempting. -->

#### Data pipeline

<!-- Make sure to clarify how you will satisfy the Unit 8 requirements,  and which optional "difficulty" points you are attempting. -->

#### Continuous X

<!-- Make sure to clarify how you will satisfy the Unit 3 requirements,  and which optional "difficulty" points you are attempting. -->


```

