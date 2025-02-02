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

Due 3/20 
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
