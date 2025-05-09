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

- [ ] **Offline evaluation of model**: You will define an automated offline evaluation plan, and it will run immediately after model training with results logged to MLFlow. Your offline evaluation must include: (1) evaluation on appropriate "standard" and "domain specific" use cases for your particular model (2) evaluation on populations and slices of special relevance, including an analysis of fairness and bias if relevant (3) test on known failure modes (4) and, unit tests based on templates. Depending on the test results, you will automatically register an updated model in the model registry, or not.

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


## Instructions for project "lightning talk" on 5/1



Lightning presentation:

* On 5/1, one member of your team will have a 60-second slot to present your project proposal in class.
* For this presentation you will prepare a single slide following the template below. You will submit this as a PDF in Brightspace, due at midnight on 4/30.
* You can present using the following "template", filling in the blanks as appropriate for your own project:

> We are team **[team name]**, and we are developing a system for **[name of ONE specific customer]** to **[very briefly describe the goal of your system, and the value add, in no more than one sentence]**.
> 
> We are using **[name of dataset(s)]** to train a model **[name of model and brief description of it]**. First, we **[describe any transformations applied to the data before input to the model]**, then the following features: **[list features]** are input to the model, and the output is **[name/brief description of the direct model output]**. **[If you have multiple models, repeat for each model.]**
> 
> Here is the diagram of our system as deployed on Chameleon. 
> * **[ Describe each physical resource and container involved in data processing. ]** 
> * **[Describe each physical resource and container involved in model training.]** 
> * **[Describe each physical resources and container involved in model serving, evaluation, and monitoring.]** 
> * **[ Describe each physical resource and container involved in orchestrating a "continuous X" pipeline. ]**

You can access the slide template here: 

[Lightning talk slide template](https://link.excalidraw.com/l/2qkLiEmqaLK/1GjYZOQysDB){: .btn .btn-blue }

On the left side of this slide, you will have a diagram of all the infrastructure resources and systems included in your project:

* Indicate every object store container your project uses as a red block, with the name of the object store (as deployed on CHI@TACC or CHI@UC) and the name of the dataset that you store in it.
* Indicate every block storage volume your project uses as a red block, with the name of the volume (as deployed on KVM@TACC) and a brief description of what's stored on it.
* Indicate every compute instance that your project uses (including "ephemeral" instances that you don't use all the time!) as an orange block, with the name of the instance when it is deployed, and its flavor (for VM instances) and machine type (for bare metal instances).
* Indicate every private network that your project uses as a green block, with the name of the network, and show which instances are connected to the private network.
* Indicate every floating IP that your project uses as a blue block, and indicate which compute instance it is associated with.
* *Inside* each orange compute instance, list every container that runs on this instance as a purple block. If some containers run inside a Kubernetes cluster, where specific pods are not necessarily mapped to specific nodes, then you can just list them alongside the Kubernetes cluster.
* For any resouce type (storage, network, compute, and container): if you have already implemented it in your project **and the code/configuration to implement it is in your Git repository by the time you submit your slide**, leave it as a saturated color. If you do not have the code/configuration to implement it in your Git repository by the time you submit your slide, set it to a light, de-saturated color.

On the right side of this slide, you will have a diagram of each model and each dataset your project uses:

* For each model, show which dataset(s) are used to train it. Show an example of one input to the model from each dataset. Also indicate any transformations applied to the data between its "raw" original state and how it appears at input to the model. Also show an example of a single model output. (Show the direct model output, before any post-processing applied at the system level.)

## Instructions for project submission on 5/11 and presentations on 5/12, 5/13, 5/14

* You will "submit" your project via the README in your project repository, due at midnight on 5/11. Your README should explain all the parts of your project, **with reference to specific files in your Git repository** - I'm not just going to read the README, I want to follow links in it to see your actual implementation of each piece; and it should include instructions for *running* your project on Chameleon.
* Your project presentation will be on 5/12, 5/13, or 5/14; the presentation schedule is listed in Brightspace. You will prepare a 15-minute presentation. You won't use slides; instead, you should prepare a live walkthrough of your project repository and demo your running systems. It's OK if you only demo "persistent" parts of your system, e.g. experiment tracking, monitoring, workflow management, online data, and serving if it is not on GPU; you don't have to demo the parts that only run on GPU instaces.
* Each team member should present the part of the project that they "own", following the "Group work expectations" listed on this page. 

The requirements above are the only hard requirements, read on if you also want to hear my recommendations!

For both your project README and your presentation, it is helpful if you follow the lifecycle of the system from "nothing" to "deployed in production", and also make sure to hit all of the project requirements along the way. If you follow the recommended structure (in both README and presentation), it will make it easy for me to check off and credit you for the requirements that you satisfy. 

I have clarified in brackets who is expected to present each part, and how long it should take (for the presentation).

Unit 1: ANY PERSON - 1 minute

1. **Value proposition**:  Describe the ONE specific customer you are targeting in your design. (Not a category of customers, not a list of several potential customers....) You will briefly describe the value proposition of your system, for this specific customer. Next, you will describe the specific details of the customer that influence your system design (including the data, deployment, and evaluation plans).
2. **Scale**: describe the size of the data (in GB), the size of the model/how long it takes to train a model, and the size of the deployment (how many inference requests per day? per hour?)

Unit 2/3: CONTINUOUS X (4 person team) or ANY (3 person team) - 1 minute

3. **Cloud-native**: Show an updated diagram of your infrastructure and all the systems it runs, just like the lightning talk; you don't have to explain it.
4. **Infrastructure** and **Infrastructure-as-code**: Show how to provision and set up the infrastructure required for your project (i.e. all the systems in your diagram).

Unit 8: DATA PERSON - 2 minutes

5. **Persistent storage**: Describe the persistent storage allocated for your project, and what is in it. Show the contents of each persistent storage bucket/volume and its size (as deployed on Chameleon).
6. **Offline data**: Identify the training data set, and describe the data lineage. Show an example sample of one sample from each dataset that you use. Relate the data sample to the specific customer.  If relevant, describe what is known about a production sample over its lifetime. (example: are some features only known later? is there a natural ground truth label?)
7. **Data pipeline**: Show the pipeline that retrieves the data from its original source and loads it into what object store or whatever data repository you are using. Describe how you divide the data into training, evaluation, and one or more production sets, avoiding data leakage if relevant. Describe any pre-processing steps that are part of the offline data pipeline.
8. **Optional: Data dashboard**: if you have a "data dashboard" (note: not a "model dashboard" or "service dashboard", but a dashboard devoted to data and data quality), show it and explain an example of how your customer will gain insight from it.

Unit 4 and 5: MODEL TRAINING PERSON - 3 minutes

9. **Modeling**: Describe how you set up the modeling problem. What are the inputs to the model? What are the outputs (target variable)? Make sure to clarify how it is used by your customer. Describe the model itself. Why did you choose this model, for this particular use case and customer?
10. **Train and re-train**: Show your training code, including whatever code is used to re-train the model as part of a non-interactive pipeline.
11. **Experiment tracking**: Bring up your experiment tracking server, and show a comparison of the main experiments you ran.
12. **Scheduling training jobs**: Show your training and re-training setup.
13. **Optional: Training strategies for large models/Use distributed training to increase velocity**: If you hit these difficulty points, explain what you did! Include numbers (e.g. "training time decreased from X to Y due to training strategy Z.")
14. **Optional: Using Ray Train or Ray Tune features**: If you hit these difficulty points, show off the relevant section of your code! Make sure I realize that you did it!

Unit 6 and 7: MODEL SERVING AND EVALUATION PERSON - 2 minutes

15. **Serving from an API endpoint**: Describe how you set up the API endpoint. What is the input? What is the output? 
16. **Identify requirements**: Discuss requirements with respect to the specific customer.
17. **Model optimizations**: Show the part of your repo that implements this, and discuss the results!
18. **System optimizations**: Show the part of your repo that implements this, and discuss the results!
19. **Offline evaluation of model**: Show your offline test suite in your repository, including all of the types of tests discussed in the requirements, and show results for the most recent model (in MLFlow or your workflow manager or wherever results are logged).
20. **Load test in staging**: Show your load test suite in your repository, and show results for the most recent model (wherever results are logged).
21. **Define a business-specific evaluation**: Describe this hypothetical evaluation; it's not something you actually implement.
22. **Optional: Develop multiple options for serving**: If you attempt this difficulty point, make sure I know it! Show the parts of the repo that implement each option, and show a comparison of the options with respect to performance and cost of deployment on a commercial cloud. (You can use a commercial cloud cost calculator to estimate costs. Show your work.)


Unit 2/3: CONTINUOUS X (4 person team) or ANY (3 person team) - 1 minute

23. **Staged deployment**: Show how a model progresses from "training" to "staging" to "canary" deployment.

Unit 8: DATA PERSON - 1 minutes

24. **Online data**: Show how "new" data is sent to the inference endpoint during "production" use.

Unit 6 and 7: MODEL SERVING AND EVALUATION PERSON - 1 minute

25. **Online evaluation/Close the loop**: Show how you evaluate and monitor your model in production, and especially how you "close the loop" and get feedback and/or labels during production use. Show me your "online" monitoring dashboards.
26. **Optional: Monitor for data drift**: If you are doing this, make sure I know it! Show me your "data drift" dashboard/refer to the part of the code that implements it.
27. **Optional: Monitor for model degradation**: If you are doing this, make sure I know it! Show me your "model quality" dashboard/refer to the part of the code that implements it.

Unit 2/3: CONTINUOUS X (4 person team) or ANY (3 person team) - 1 minute

28. **CI/CD and continuous training**: Show me how the cycle starts again - what triggers re-training? Show me the re-training to re-deployment pipeline.

## Using resources on Chameleon

As you know, your projects will be developed, hosted, and evaluated entirely on Chameleon. The only external hosted service you are permitted to use is Github (for version control and source code hosting only; you are *not* allowed to use Github-hosted runners for CI actions, for example), and potentially external data APIs.

Please follow these guidelines when using resource on Chameleon:

* **Naming convention**: Whenever you create a resource (including: VMs, bare metal compute instances, bare metal leases, edge device containers, edge device leases, block storage volumes, object store containers, networks, security groups), give it a name that ends in the word "project" and your project number. For example, if I am in project group 0, I might launch a VM instance named "node1-project0". This is how you will protect your resources from premature deletion (since I proactively delete resources used for lab assignments!)
* **Lifecycle of storage resources**: You can create one object store container per training data set and one volume per project, and these may persist for the lifetime of the project.
* **Lifecycle of network resources**: You can keep a network at KVM@TACC alive for the duration of the project, so that you can attach and detach VMs easily as you launch/delete them. Within a project group, you should not use more than one floating IP per site at a time. (You can "jump" through the node with the floating IP to reach the others over a network.)
* **Lifecycle of compute resources**: You should not expect to persist *any* compute resources for the duration of the entire project! Once you have a data pipeline involving persistent storage + you have automated the infrastructure provisioning and bootstrapping process, then it becomes easy to bring up compute when you plan to actually work on it, and free up the compute when you are not actively working. For bare metal resources, see the guidelines below. For VM resources, you should not plan to leave these alive longer than one day at a time.
* **Secrets**: Do not put secrets that allow access to Chameleon, such as SSH private keys or application credentials, in your Git repository (even if the repository is private).

Also, here are some recommendations:

* **Shared key**: For convenience, you may want to create a key pair (public and private SSH key) for your project, and distribute it to all team members. Everyone should get the public and private key; everyone should upload the public key to their Chameleon profile on CHI@UC, CHI@TACC, and KVM@TACC (in addition to, not replacing, your existing keys). Then, when you create resources for the project, all project members will be able to access the resources with that key.
* **Persistent storage**: In many cases, you can use less persistent storage and also be more efficient by improving your data pipeline to include pre-training transformations such as resizing, that reduce the overall size of the data. If you are working with a very large data set, you should use this approach, mostly for your own sanity (it will make it much easier to work with the data!).

Some bare metal GPU resources are reserved for use by our class as a group, starting 4/12. You may use them as follows:

* A variable number of `gpu_rtx6000` nodes at CHI@UC, which each have one RTX6000 NVIDIA GPU. You may use these for general model training or inference jobs. 
* Four `compute_liqid` nodes at CHI@TACC, which each have an A100 40GB NVIDIA GPU. You may use these for general model training or inference jobs, especially if your inference job involves an NVIDIA Triton service. 
* Two `gpu_mi100` nodes at CHI@TACC, which each have 2 MI100 AMD GPUs. You may use these for general model training or inference jobs.
* A variable number of `compute_gigaio` nodes at CHI@UC, which each have one A100 80GB NVIDIA GPU. Use these for model training or inference jobs with very large models, where it is not practical to use a GPU with less memory.
* A `gpu_a100_pcie` (either `J0BG3Q3` or `307G3Q3`) at CHI@UC. These are 4x A100 80GB NVIDIA GPU nodes. We have one reserved from 4/12 through 5/6. You should use these only if you are using distributed training to train a very large model that is not practical to train on a single GPU. 

For now, you may reserve up to 6 hours at a time on these bare metal nodes. (Once we get closer to the end of the semester, this time limit will be smaller.)

