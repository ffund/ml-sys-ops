---
title: Instructor Guid
layout: page
nav_order: 5
---

# Instructor Guide to Teaching on Chameleon Cloud

This page includes some notes for instructors who want to use these materials in their own courses.

## Things that are known to be broken

Since this course was first offered in Spring 2025, some things have changed:

* Starting August 1, 2025, KVM@TACC [requires reservations](https://chameleoncloud.org/blog/2025/07/01/chameleon-changelog-for-june-2025/) for VM instances. The instructions for lab assignments involving VMs have not yet been updated to include reservation.
* DockerHub has changed its rate limit for anonymous "docker pull" operations. If many students are deploying Kubernetes (as in: "Cloud Computing", "MLOps Pipeline" labs) at the same time, since they all appear to be coming from the same public IP, they will exceed that rate limit. A workaround is for the instructor to set up a [pull-through Dockerhub cache](https://github.com/teaching-on-testbeds/dockerhub-pull-through-cache) and then for students to [configure Docker](https://github.com/teaching-on-testbeds/gourmetgram-iac/blob/main/ansible/pre_k8s/pre_k8s_configure.yml#L39) to use that cache. 
  * The "MLOps Pipeline" lab assumes that this pull-through cache is set up. If you don't set up the cache, it won't work.
  * The "Cloud Computing" lab needs to be adapted for this, or you will hit the rate limit.


## Before the class begins

Before the class begins an instructor should:


#### Set up a project

Create an account on Chameleon Cloud, and create a project for the course.

From the project page, click "Add multiple users" and then copy the "request to join" link which you can distribute to your students.

#### Increase project quota

Use the "Help Desk" feature on Chameleon to request a quota increase for KVM@TACC for your project.

For network access:

* request unlimited private networks and subnets,
* "floating IPs" increased to 1.5x the expected enrollment,
*  and 50 security groups.

If you are using "Cloud computing" and/or "MLOps Pipeline" labs, you need the quota to permit up to **3** `m1.medium` instances per student at a time:

 * The "number of instances" quota should be increased to 3x the expected enrollment
 * "number of cores" should be increased to 6x the expected enrollment
 * "RAM" should be increased to 4GB x 3 x expected enrollment
 * "number of routers" increased to 1x the expected enrollment.

 If you are not using "Cloud computing" or "MLOps Pipeline" labs, but you *are* using "Persistent data", you need the quota to permit 1 `m1.large` instances per student at a time:

 * The "number of instances" quota should be increased to 1x the expected enrollment
 * "number of cores" should be increased to 4x the expected enrollment
 * "RAM" should be increased to 8GB x expected enrollment

 If you are using "Persistent data", you **also** need one 2GB block storage volume per student at a time:

 * "number of block storage volumes" should be increased to the expected enrollment, and total block storage should be increased to 2GB x expected enrollment. 

 If you are not using "Cloud computing", "MLOps Pipeline," or "Persistent data", labs, but you are using "Evaluation and Monitoring," you need the quota to permit 1 `m1.medium` instances per student at a time:

 * The "number of instances" quota should be increased to 1x the expected enrollment
 * "number of cores" should be increased to 2x the expected enrollment
 * "RAM" should be increased to 4GB x expected enrollment

If students will develop open-ended projects, you may need to request additional quota increases depending on their needs. However, you can do this later on an as-needed basis, if you keep an eye on usage.

#### Reserve GPU nodes

To ensure that your students will be able to access GPU resources as needed, you will pre-reserve the bare metal hosts you need leading up to the relevant due dates for labs. The following table shows the GPU types and expected number of hours per student for each lab:

<table>
  <thead>
    <tr>
      <th>#</th>
      <th>Assignment</th>
      <th>Instance Type(s)</th>
      <th>Number of Hours per Student</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>4</td>
      <td>Train at Scale (Multi GPU)</td>
      <td><code>gpu_a100_pcie</code>, <code>gpu_v100</code></td>
      <td>2</td>
    </tr>
    <tr>
      <td>4</td>
      <td>Train at Scale (One GPU)</td>
      <td><code>compute_gigaio</code> at CHI@UC only (needs A100 80GB)</td>
      <td>2</td>
    </tr>
    <tr>
      <td>5</td>
      <td>Training in a Cluster (Multi GPU)</td>
      <td><code>gpu_mi100</code></td>
      <td>3</td>
    </tr>
    <tr>
      <td>5</td>
      <td>Experiment Tracking (One GPU)</td>
      <td><code>compute_liqid</code> at CHI@TACC or <code>compute_gigaio</code> at CHI@UC</td>
      <td>3</td>
    </tr>
    <tr>
      <td>6</td>
      <td>Model Serving Optimizations</td>
      <td><code>compute_liqid</code> at CHI@TACC or <code>compute_gigaio</code> at CHI@UC</td>
      <td>3</td>
    </tr>
    <tr>
      <td>6</td>
      <td>Serving from the Edge</td>
      <td><code>rpi5</code> on CHI@Edge (you may need to BYOD)</td>
      <td>2</td>
    </tr>
    <tr>
      <td>6</td>
      <td>System Serving Optimizations</td>
      <td><code>gpu_p100</code></td>
      <td>3</td>
    </tr>
  </tbody>
</table>


Then, use the "Help Desk" feature on Chameleon. Give the list of reservations you have made, and ask for these resources to be allocated for exclusive use for your course during the times you have reserved.

If students will do open-ended projects that require GPU, you may want to make additional advance reservations to support this.

## During the course

#### Communication to students

* Give students explicit instructions about expected resource usage, and what they can expect to happen if they ignore these instructions (e.g "if you make a reservation that is longer than 4 hours for X resource, course staff will delete it"). Also remind students that the infrastructure cannot support all of them doing the assignment at the same time in the last few hours before the deadline. 
* If you have a large class, you may want to assign days to smooth peak usage for lab assignments, e.g. "if your student ID ends in an even number you can use the infrastructure on Monday, Wednesday, Friday, or Saturday; if your student ID ends in an odd number you can use the infrastructure on Tuesday, Thursday, Friday, or Sunday".


#### Managing resources

* Keep an eye on resource usage, to make sure nobody has excessive use and to make sure resources are available to students who need them.
* At the beginning of your advance reservations, after Chameleon staff have re-configured the resource to be exclusively available to your project, you will delete your "placeholder" reservation so that students can then make their own reservations.
