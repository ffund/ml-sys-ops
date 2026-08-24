---
title: Instructor Guide
layout: page
nav_order: 5
---

# Instructor Guide to Teaching on Chameleon Cloud

This page includes some notes for instructors who want to use these materials in their own courses.

## Overview of available lab materials

{: .note }
> Some lab materials are available in multiple versions tuned for different hardware types. If you have a large class, you can spread capacity across the available hardware by assigning students to different versions.

Instructors can refer to the "Before the class begins" section to understand how to get started on Chameleon and prepare for their class.

Instructors are advised to test each lab shortly before assigning it to their class, since the software and hardware on Chameleon and the software stack used in the lab are regularly updated. Feel free to contact [ffund@nyu.edu](mailto:ffund@nyu.edu) with any questions or problems.

<style>
  tr.variant-continues > td:not([rowspan]) {
    border-bottom: 0;
  }

  tr.variant-continuation > td:first-child {
    border-left: 1px solid #eeebee;
  }
</style>

<table>
  <thead>
    <tr>
      <th>Lab Instructions</th>
      <th>Trovi Artifact</th>
      <th>Compute Instance Type</th>
      <th>GitHub Repo</th>
    </tr>
  </thead>
  <tbody>

    <!-- Week 1 -->
    <tr>
      <td>
        <a href="https://teaching-on-testbeds.github.io/hello-chameleon">Hello, Chameleon</a>
        <div>(Intro)</div>
      </td>
      <td>
        <a href="https://trovi.chameleoncloud.org/dashboard/artifacts/a10a1b51-51d7-4c6e-ba83-010a5cf759d6">
          <img src="../assets/images/run-on-chameleon-badge.svg" alt="Run on Chameleon">
        </a>
      </td>
      <td><code>m1.small</code></td>
      <td>
        <a href="https://github.com/teaching-on-testbeds/hello-chameleon">
          <img src="../assets/images/github-badge.svg" alt="GitHub">
        </a>
      </td>
    </tr>
    <tr>
      <td>
        <a href="https://teaching-on-testbeds.github.io/hello-linux/index-chi">Hello, Linux</a>
        <div>(Intro)</div>
      </td>
      <td>
        (Use "Hello, Chameleon" artifact)
      </td>
      <td><code>m1.small</code></td>
      <td>
        <a href="https://github.com/teaching-on-testbeds/hello-linux">
          <img src="../assets/images/github-badge.svg" alt="GitHub">
        </a>
      </td>
    </tr>

    <!-- Week 2 -->
    <tr>
      <td>
        <a href="https://teaching-on-testbeds.github.io/cloud-chi/">Cloud computing on Chameleon</a>
        <div>(Cloud computing)</div>
      </td>
      <td>
        <a href="https://trovi.chameleoncloud.org/dashboard/artifacts/a5efb034-917e-4fdd-b83d-1a7f8930d960">
          <img src="../assets/images/run-on-chameleon-badge.svg" alt="Run on Chameleon">
        </a>
      </td>
      <td>3 x <code>m1.medium</code></td>
      <td>
        <a href="https://github.com/teaching-on-testbeds/cloud-chi">
          <img src="../assets/images/github-badge.svg" alt="GitHub">
        </a>
      </td>
    </tr>

    <!-- Week 3 -->
    <tr>
      <td>
        <a href="https://teaching-on-testbeds.github.io/mlops-chi/">Build an MLOps pipeline on Chameleon</a>
        <div>(DevOps and continuous X for ML systems)</div>
      </td>
      <td>
        <a href="https://trovi.chameleoncloud.org/dashboard/artifacts/1eb302de-4707-4ae9-ae2d-391b9b8e5261">
          <img src="../assets/images/run-on-chameleon-badge.svg" alt="Run on Chameleon">
        </a>
      </td>
      <td>3 x <code>m1.large</code></td>
      <td>
        <a href="https://github.com/teaching-on-testbeds/mlops-chi">
          <img src="../assets/images/github-badge.svg" alt="GitHub">
        </a>
      </td>
    </tr>

    <!-- Week 4 -->
    <tr>
      <td>
        <a href="https://teaching-on-testbeds.github.io/data-platform-chi/">Data platforms on Chameleon</a>
        <div>(Large scale data systems)</div>
      </td>
      <td>
        <a href="https://trovi.chameleoncloud.org/dashboard/artifacts/3aca301f-22f7-4929-88c4-4b666f3d4c92">
          <img src="../assets/images/run-on-chameleon-badge.svg" alt="Run on Chameleon">
        </a>
      </td>
      <td><code>m1.xlarge</code></td>
      <td>
        <a href="https://github.com/teaching-on-testbeds/data-platform-chi">
          <img src="../assets/images/github-badge.svg" alt="GitHub">
        </a>
      </td>
    </tr>
    <tr>
      <td>
        <a href="https://teaching-on-testbeds.github.io/data-persist-chi/">Persistent storage on Chameleon</a>
        <div>(Large scale data systems)</div>
      </td>
      <td>
        <a href="https://trovi.chameleoncloud.org/dashboard/artifacts/a1c68238-81f8-498d-8323-9d6c46cb0a78">
          <img src="../assets/images/run-on-chameleon-badge.svg" alt="Run on Chameleon">
        </a>
      </td>
      <td><code>m1.medium</code> (block), <code>m1.large</code> (object)</td>
      <td>
        <a href="https://github.com/teaching-on-testbeds/data-persist-chi">
          <img src="../assets/images/github-badge.svg" alt="GitHub">
        </a>
      </td>
    </tr>

    <!-- Week 5 -->
    <tr class="variant-continues">
      <td rowspan="2">
        <a href="https://teaching-on-testbeds.github.io/llm-chi/">Large-scale model training on Chameleon</a>
        <div>(Model training at scale)</div>
      </td>
      <td>
        A100 Version:<br>
        <a href="https://trovi.chameleoncloud.org/dashboard/artifacts/39a536c6-6070-4ccf-9e91-bc47be9a94af">
          <img src="../assets/images/run-on-chameleon-badge.svg" alt="Run on Chameleon">
        </a>
      </td>
      <td>
        A100 Version:<br>
        <code>compute_gigaio</code> (single GPU), <code>gpu_a100_pcie</code> (multi-GPU)
      </td>
      <td rowspan="2">
        <a href="https://github.com/teaching-on-testbeds/llm-chi">
          <img src="../assets/images/github-badge.svg" alt="GitHub">
        </a>
      </td>
    </tr>
    <tr class="variant-continuation">
      <td>
        H100 Version:<br>
        <a href="https://trovi.chameleoncloud.org/dashboard/artifacts/bd06bd6d-d94f-4297-ad5d-c9b7e1f02575">
          <img src="../assets/images/run-on-chameleon-badge.svg" alt="Run on Chameleon">
        </a>
      </td>
      <td>
        H100 Version:<br>
        <code>g1.h100.pci.1</code> (single GPU), <code>g1.h100.pci.4</code> (multi-GPU)
      </td>
    </tr>

    <!-- Week 6 -->
    <tr class="variant-continues">
      <td rowspan="3">
        <a href="https://teaching-on-testbeds.github.io/mlflow-chi/">ML experiment tracking with MLFlow</a>
        <div>(Model training infrastructure and platforms)</div>
      </td>
      <td>
        NVIDIA GPU Version:<br>
        <a href="https://trovi.chameleoncloud.org/dashboard/artifacts/aefd5288-b99c-455d-8a85-028d4aad3209">
          <img src="../assets/images/run-on-chameleon-badge.svg" alt="Run on Chameleon">
        </a>
      </td>
      <td>
        NVIDIA GPU Version:<br>
        <code>compute_liqid</code> or <code>compute_gigaio</code>
      </td>
      <td rowspan="3">
        <a href="https://github.com/teaching-on-testbeds/mlflow-chi">
          <img src="../assets/images/github-badge.svg" alt="GitHub">
        </a>
      </td>
    </tr>
    <tr class="variant-continues variant-continuation">
      <td>
        AMD GPU Version:<br>
        <a href="https://trovi.chameleoncloud.org/dashboard/artifacts/9955458e-49b8-47b7-92e3-a6a84a70e0e4">
          <img src="../assets/images/run-on-chameleon-badge.svg" alt="Run on Chameleon">
        </a>
      </td>
      <td>
        AMD GPU Version:<br>
        <code>gpu_mi100</code>
      </td>
    </tr>
    <tr class="variant-continuation">
      <td>
        NVIDIA VM Version:<br>
        <a href="https://trovi.chameleoncloud.org/dashboard/artifacts/0f7d4c62-a65a-4571-9b45-16b692af3ee2">
          <img src="../assets/images/run-on-chameleon-badge.svg" alt="Run on Chameleon">
        </a>
      </td>
      <td>
        NVIDIA VM Version:<br>
        <code>g1.h100.pci.1</code>
      </td>
    </tr>


    <tr class="variant-continues">
      <td rowspan="2">
        <a href="https://teaching-on-testbeds.github.io/mltrain-chi/">Building a model training cluster with Ray</a>
        <div>(Model training infrastructure and platforms)</div>
      </td>
      <td>
        NVIDIA GPU Version:<br>
        <a href="https://trovi.chameleoncloud.org/dashboard/artifacts/b4578c82-e84a-4353-83d2-fbecf153eefd">
          <img src="../assets/images/run-on-chameleon-badge.svg" alt="Run on Chameleon">
        </a>
      </td>
      <td>
        NVIDIA GPU Version:<br>
        <code>compute_liqid</code>, with 2 GPUs
      </td>
      <td rowspan="2">
        <a href="https://github.com/teaching-on-testbeds/mltrain-chi">
          <img src="../assets/images/github-badge.svg" alt="GitHub">
        </a>
      </td>
    </tr>
    <tr class="variant-continuation">
      <td>
        AMD GPU Version:<br>
        <a href="https://trovi.chameleoncloud.org/dashboard/artifacts/d48d7684-cf6d-4c33-bcd6-5504266bc3d4">
          <img src="../assets/images/run-on-chameleon-badge.svg" alt="Run on Chameleon">
        </a>
      </td>
      <td>
        AMD GPU Version:<br>
        <code>gpu_mi100</code>, with 2 GPUs
      </td>
    </tr>


    <!-- Week 7 -->
    <tr class="variant-continues">
      <td rowspan="2">
        <a href="https://teaching-on-testbeds.github.io/serve-model-chi/">Model optimizations for serving</a>
        <div>(Model serving)</div>
      </td>
      <td>
        NVIDIA GPU Version:<br>
        <a href="https://trovi.chameleoncloud.org/dashboard/artifacts/f5acccf8-f2cb-4d1e-8918-4c8fd97bfc32">
          <img src="../assets/images/run-on-chameleon-badge.svg" alt="Run on Chameleon">
        </a>
      </td>
      <td>
        NVIDIA GPU Version:<br>
        <code>compute_liqid</code> or <code>compute_gigaio</code>
      </td>
      <td rowspan="2">
        <a href="https://github.com/teaching-on-testbeds/serve-model-chi">
          <img src="../assets/images/github-badge.svg" alt="GitHub">
        </a>
      </td>
    </tr>
    <tr class="variant-continuation">
      <td>
        AMD GPU Version:<br>
        <a href="https://trovi.chameleoncloud.org/dashboard/artifacts/c6c0c3b6-ca57-475c-924b-9c248a0055f2">
          <img src="../assets/images/run-on-chameleon-badge.svg" alt="Run on Chameleon">
        </a>
      </td>
      <td>
        AMD GPU Version:<br>
        <code>gpu_mi100</code>
      </td>
    </tr>
    <tr>
      <td>
        <a href="https://teaching-on-testbeds.github.io/serve-edge-chi/">Serving on edge devices</a>
        <div>(Model serving)</div>
      </td>
      <td>
        <a href="https://trovi.chameleoncloud.org/dashboard/artifacts/a1662022-9017-45b1-9b96-31705ca20358">
          <img src="../assets/images/run-on-chameleon-badge.svg" alt="Run on Chameleon">
        </a>
      </td>
      <td><code>rpi5</code></td>
      <td>
        <a href="https://github.com/teaching-on-testbeds/serve-edge-chi">
          <img src="../assets/images/github-badge.svg" alt="GitHub">
        </a>
      </td>
    </tr>
    <tr>
      <td>
        <a href="https://teaching-on-testbeds.github.io/serve-system-chi/">System optimizations for model serving</a>
        <div>(Model serving)</div>
      </td>
      <td>
        <a href="https://trovi.chameleoncloud.org/dashboard/artifacts/45097b76-3b24-472d-9b23-d522e795b2e0">
          <img src="../assets/images/run-on-chameleon-badge.svg" alt="Run on Chameleon">
        </a>
      </td>
      <td><code>gpu_p100</code></td>
      <td>
        <a href="https://github.com/teaching-on-testbeds/serve-system-chi">
          <img src="../assets/images/github-badge.svg" alt="GitHub">
        </a>
      </td>
    </tr>

    <!-- Week 8 -->
    <tr>
      <td>
        <a href="https://teaching-on-testbeds.github.io/eval-offline-chi">Offline evaluation of ML systems</a>
        <div>(Monitoring and evaluating ML systems)</div>
      </td>
      <td>
        <a href="https://trovi.chameleoncloud.org/dashboard/artifacts/3785c5f5-4c98-4dae-b66d-9e693544a269">
          <img src="../assets/images/run-on-chameleon-badge.svg" alt="Run on Chameleon">
        </a>
      </td>
      <td><code>m1.medium</code></td>
      <td>
        <a href="https://github.com/teaching-on-testbeds/eval-offline-chi">
          <img src="../assets/images/github-badge.svg" alt="GitHub">
        </a>
      </td>
    </tr>
    <tr>
      <td>
        <a href="https://teaching-on-testbeds.github.io/eval-online-chi">Online evaluation of ML systems</a>
        <div>(Monitoring and evaluating ML systems)</div>
      </td>
      <td>
        <a href="https://trovi.chameleoncloud.org/dashboard/artifacts/4e7c43ef-31be-46c5-bb64-4d358608b3b8">
          <img src="../assets/images/run-on-chameleon-badge.svg" alt="Run on Chameleon">
        </a>
      </td>
      <td><code>m1.medium</code></td>
      <td>
        <a href="https://github.com/teaching-on-testbeds/eval-online-chi">
          <img src="../assets/images/github-badge.svg" alt="GitHub">
        </a>
      </td>
    </tr>
    <tr>
      <td>
        <a href="https://teaching-on-testbeds.github.io/eval-loop-chi/">Closing the feedback loop</a>
        <div>(Monitoring and evaluating ML systems)</div>
      </td>
      <td>
        <a href="https://trovi.chameleoncloud.org/dashboard/artifacts/285f3758-3df2-4226-99ab-c243aa715b8e">
          <img src="../assets/images/run-on-chameleon-badge.svg" alt="Run on Chameleon">
        </a>
      </td>
      <td><code>m1.medium</code></td>
      <td>
        <a href="https://github.com/teaching-on-testbeds/eval-loop-chi">
          <img src="../assets/images/github-badge.svg" alt="GitHub">
        </a>
      </td>
    </tr>

  </tbody>
</table>

## Overview of available lecture materials

| Topic | Links |
| --- | --- |
| Intro to ML Systems | [Chapter 1](https://ffund.github.io/ml-sys-ops-notes/chapters/01-designing-ml-systems/) |
| Cloud computing | [Chapter 2](https://ffund.github.io/ml-sys-ops-notes/chapters/02-cloud-computing/) |
| DevOps and continuous X for ML systems | [Chapter 3](https://ffund.github.io/ml-sys-ops-notes/chapters/03-mlops/) |
| Large scale data systems | [Chapter 4](https://ffund.github.io/ml-sys-ops-notes/chapters/04-large-scale-data/) |
| Model training at scale | [Chapter 5](https://ffund.github.io/ml-sys-ops-notes/chapters/05-large-model-training/) |
| Model training infrastructure and platforms | [Chapter 6](https://ffund.github.io/ml-sys-ops-notes/chapters/06-training-infra-platforms/) |
| Model serving | [Chapter 7](https://ffund.github.io/ml-sys-ops-notes/chapters/07-model-serving/) |
| Monitoring and evaluating ML systems | [Chapter 8](https://ffund.github.io/ml-sys-ops-notes/chapters/08-evaluation-monitoring/) |


## Things that are known to be broken

<!-- 

Since this course was first offered in Spring 2025, some things have changed:

* Starting August 1, 2025, KVM@TACC [requires reservations](https://chameleoncloud.org/blog/2025/07/01/chameleon-changelog-for-june-2025/) for VM instances. The instructions for lab assignments involving VMs have not yet been updated to include reservation.

* DockerHub has changed its rate limit for anonymous "docker pull" operations. If many students are deploying Kubernetes (as in: "Cloud Computing", "MLOps Pipeline" labs) at the same time, since they all appear to be coming from the same public IP, they will exceed that rate limit. A workaround is for the instructor to set up a [pull-through Dockerhub cache](https://github.com/teaching-on-testbeds/dockerhub-pull-through-cache) and then for students to [configure Docker](https://github.com/teaching-on-testbeds/gourmetgram-iac/blob/main/ansible/pre_k8s/pre_k8s_configure.yml#L39) to use that cache. 
  * The "MLOps Pipeline" lab assumes that this pull-through cache is set up. If you don't set up the cache, it won't work.
  * The "Cloud Computing" lab needs to be adapted for this, or you will hit the rate limit.
-->

* No notes at the moment.


## Before the class begins

Before the class begins an instructor should:


#### Set up a project

Create an account on Chameleon Cloud, and create a project for the course.

From the project page, click "Add multiple users" and then copy the "request to join" link which you can distribute to your students.

#### Reserve GPU nodes

{: .warning }
> Certain node types, especially <code>gpu_a100_pcie</code>, may be fully reserved far in advance. Make your reservations well before you will need the resources.

Some resources on Chameleon, especially certain types of bare-metal GPU nodes, are heavily utilized. To ensure capacity for your course, so that your students do not have to contend with other Chameleon users for scarce resources near a deadline, you should pre-reserve these scarce resources for the time intervals in which your class will need them.

You should anticipate roughly 3 hours of use per student for each lab assignment. Then, use the table above, with information about compute instance types, and your enrollment numbers to determine how many of each bare-metal instance type you will need, and for which time intervals.

Make an advance reservation yourself for these resources at the times your class will need them, to block reservations by other Chameleon users.

Then, use the "Help Desk" feature on Chameleon. Give the list of reservations you have made and the project number associated with your course, and ask for these resources to be allocated for exclusive use for your course during the times you have reserved.

At the beginning of each reservation, confirm via the Help Desk that the resources have been allocated for exclusive use by your project. Then, you can delete the "placeholder" reservations you made, and your students will be able to make their own reservations.

If students will do open-ended projects that require GPU, you may want to make additional advance reservations to support this.

## During the course

#### Communication to students

* Give students explicit instructions about expected resource usage, and what they can expect to happen if they ignore these instructions (e.g "if you make a reservation that is longer than 4 hours for X resource, course staff will delete it"). Also remind students that the infrastructure cannot support all of them doing the assignment at the same time in the last few hours before the deadline. 
* It is strongly encouraged to give students a preliminary deadline for each lab assignment by which they must have made a reservation for the resources required for that lab. This helps avoid students waiting until the day before the lab is due and then not having resources available.
* If you have a large class, you may want to assign days to smooth peak usage for lab assignments, e.g. "if your student ID ends in an even number you can use the infrastructure on Monday, Wednesday, Friday, or Saturday; if your student ID ends in an odd number you can use the infrastructure on Tuesday, Thursday, Friday, or Sunday".


#### Managing resources

* Keep an eye on resource usage, to make sure nobody has excessive use and to make sure resources are available to students who need them.
* At the beginning of your advance reservations, after Chameleon staff have re-configured the resource to be exclusively available to your project, you will delete your "placeholder" reservation so that students can then make their own reservations.
