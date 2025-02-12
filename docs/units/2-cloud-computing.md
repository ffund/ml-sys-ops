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

Due 2/13
{: .label .label-yellow}

This week's lab assignment is:

[Lab manual: Cloud Computing on Chameleon](https://teaching-on-testbeds.github.io/cloud-chi/){: .btn .btn-green }

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


The estimated time to complete this lab assignment is 5 hours, broken down as follows:

* about 1.5 hours for part 1 "Provision resources using the GUI" and part 2 "Provision resources using the openstack CLI" together
* another 1.5 hours for part 3  "Deploy a service in a Docker container"
* and 2 hours for part 4  "Deploy on Kubernetes" (some of this is not active time - e.g. while your cluster is installing itself.)

If you prefer to complete this lab assignment in two sessions, instead of all at once, my recommendation is:

* Do part 0 "Intro", part 1 "Provision resources using the GUI", part 3 "Deploy a service in a Docker container", then part 5 "Delete resources" in one session. 
* Do part 1 "Provision resources using the GUI", then part 2 "Provision resources using the openstack CLI", then part 4 "Deploy on Kubernetes", then part 5 "Delete resources" in the second session.
