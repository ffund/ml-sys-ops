--- 
title: Cloud computing
layout: page
parent: Units
nav_order: 2
---

# Cloud computing

In this week's lecture, we are primarily concerned with the underlying *infrastructure* that our machine learning system will run on.

We talked about how to *build* a cloud - we identified key ingredients including:

* hardware and connectivity (of course)
* compute (bare metal, VM, container), network, and storage (block, file, object) services
* shared services (authentication and authorization, bootable images)
* user interfaces (GUI, CLI, Python SDK)

and as an example, we named the OpenStack components that handle each of these. This semester we are going to spend a lot of time on Chameleon, which is an OpenStack cloud.

We said that besides for providing access to compute, storage, and network resources, cloud infrastructure providers can also offer managed services in which the infrastructure provider assumes responsibility for parts of the stack that were previously the user's responsibility. We named some cloud service models, and described what the infrastructure provider is responsible for providing and maintaining, in each case.

We also talked about how the virtualization of compute, storage, and networking resources in the cloud provides opportunities to manage our services like "cattle" instead of like "pets" - with systems in place to handle their lifecycles at scale. We introduced containers (e.g. Docker) and container orchestration frameworks (e.g. Kubernetes) as tools for managing services at scale.


[Slides: Cloud computing overview](https://link.excalidraw.com/p/readonly/4lOcDZjTOcR0AUTrMck9){: .btn .btn-purple }


## Lab assignment

Due TBD
{: .label .label-yellow}

Because of an outage affecting the Chameleon JupyterHub service, we are deferring this lab assignment - keep an eye out for an announcement early next week.

<!-- 
This week's lab assignment is:

[Lab manual: Deploy a machine learning service on Kubernetes](){: .btn .btn-green }


{:.important }
> Resource usage notes for this lab assignment:
> * If your net ID ends in an even number (0, 2, 4, 6, 8) you may bring up your cluster on Chameleon on Saturday, Monday, or Wednesday before the due date.
> * If your net ID ends in an odd number (1, 3, 5, 7, 9) you may bring up your cluster on Chameleon on Friday, Sunday, Tuesday, or Thursday before the due date.
> * (Next week, the odds and evens will swap weekdays.)
> * You should plan to start and finish the assignment within an eight-hour period - so block some time accordingly. Your resource may not be "active" for more than eight hours. It may be deleted by course staff if it is active for longer than eight hours.
> * Delete your compute instance as soon as you are done with the experiment, to free the resources for other students.

## Reading

-->


