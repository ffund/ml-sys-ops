---
title: Model training at scale
layout: page
parent: Units
nav_order: 4
---


# Model training at scale


In this week's lecture, we introduced techniques for training large-scale machine learning models.

We described a selection of techniques to allow us to train models that would not otherwise fit in the memory of a single GPU, or to fit a larger batch in memory:

* gradient accumulation
* reduced precision/mixed precision
* parameter efficient fine tuning (LoRA, QLoRA)

and we also talked about strategies for distributed training across multiple GPUs:

* distributed data parallelism, which allows us to achieve a larger effective batch size,
* fully sharded data parallelism, which allows us to train models that might otherwise not fit into memory,
* and model parallelism, including tensor and pipeline parallelism, which distribute computation across GPUs

In a future lesson, we will see how to offer some of these strategies as part of a model training "service" (e.g. as part an organization's core ML capabilities).

[Slides: Model training at scale](https://link.excalidraw.com/p/readonly/zMwrCvRBneDGH71cqjxj){: .btn .btn-purple }


## Lab assignment

Due 2/27
{: .label .label-yellow}

This week's lab assignment is:

[Lab manual: Large-scale model training on Chameleon](https://teaching-on-testbeds.github.io/llm-chi/){: .btn .btn-green }


You will submit screenshots and answer questions about this assignment in Gradescope. The link to the Gradescope submission is in Brightspace. You should review the Gradescope assignment before you begin, so that you know in advance exactly what you will need to submit.

{:.important }
> Resource usage notes for this lab assignment:
> 
> * For this experiment, you will need to reserve time on a GPU node in advance. There is certainly not enough capacity for the entire class, or even a substantial fraction of the class, to access 4x A100 80GB nodes in the last few days before the deadline, so you should not anticipate that you can do this lab just before it is due. It is your responsibility to plan ahead, make an advance reservation, and use that time effectively.
> * Read the rest of these resource usage notes, then refer to the first section of the lab manual for instructions on making a reservation.
> * There is one x4 A100 GPU node (`307G3Q3`) reserved for our course from now until the lab deadline. You may reserve a 3-hour block on that node in advance, then complete the entire lab in that 3-hour block.
> * Alternatively, if you make your reservation later/not on `307G3Q3`, you will make two separate reservations and do the lab in two parts, at two separate times:
>   * one 2-hour block on a single A100 80GB node that is reserved for our course in the last week before the deadline (`gigaio-compute-07`, `gigaio-compute-02`, or `gigaio-compute-03`). You will be able to make a reservation on these nodes starting on 2/20.
>   * AND one 2-hour block on a different x4 A100 GPU (`JOBG3Q3`) or a x4 V100 GPU node (`P3-GPU-009` or `P3-GPU-012`) that is reserved for our course in the last week before the deadline. You will be able to make a reservation on these nodes starting on 2/20.
> * Please start your lease on hour boundaries whenever possible, and end your lease five minutes before the hour boundary, since this simplifies scheduling (e.g. start at XX:00 and end at YY:55).
> * The lab assignment is designed to be completed in one 3-hour block or two 2-hour blocks. We do not have enough resources for students to use more than one 3-hour block or more than two 2-hour blocks during daytime hours. (Your lease will be deleted by course staff, if you try.) But if you need additional time, you may schedule another 3-hour block or 2-hour block during the overnight hours from 1AM to 7AM.


## Reading

The techniques from this week's lecture are described in the following papers:

#### Parameter efficient fine tuning

* (LoRA): Edward J. Hu, Yelong Shen, Phillip Wallis, Zeyuan Allen-Zhu, Yuanzhi Li, Shean Wang, Lu Wang, Weizhu Chen. 2022. "LoRA: Low-Rank Adaptation of Large Language Models." in ICLR 2022. [arXiv version](https://arxiv.org/abs/2106.09685), [OpenReview](https://openreview.net/forum?id=nZeVKeeFYf9).
* (QLoRA): Tim Dettmers, Artidoro Pagnoni, Ari Holtzman, Luke Zettlemoyer. 2023. "QLoRA: Efficient Finetuning of Quantized LLMs". In NeurIPS 2023. [Link](https://proceedings.neurips.cc/paper_files/paper/2023/hash/1feb87871436031bdc0f2beaa62a049b-Abstract-Conference.html).

#### Distributed model training with data parallelism

* (DeepSpeed/ZeRO): Samyam Rajbhandari, Jeff Rasley, Olatunji Ruwase, and Yuxiong He. 2020. "ZeRO: memory optimizations toward training trillion parameter models." In Proceedings of the International Conference for High Performance Computing, Networking, Storage and Analysis (SC '20). IEEE Press, Article 20, 1–16. [arXiv version](https://arxiv.org/abs/1910.02054)

* (PyTorch DDP): Shen Li, Yanli Zhao, Rohan Varma, Omkar Salpekar, Pieter Noordhuis, Teng Li, Adam Paszke, Jeff Smith, Brian Vaughan, Pritam Damania, and Soumith Chintala. 2020. "PyTorch distributed: experiences on accelerating data parallel training." Proc. VLDB Endow. 13, 12 (August 2020), 3005–3018. https://doi.org/10.14778/3415478.3415530. [arXiv version](https://arxiv.org/abs/2006.15704)
* (PyTorch FSDP): Yanli Zhao, Andrew Gu, Rohan Varma, Liang Luo, Chien-Chin Huang, Min Xu, Less Wright, Hamid Shojanazeri, Myle Ott, Sam Shleifer, Alban Desmaison, Can Balioglu, Pritam Damania, Bernard Nguyen, Geeta Chauhan, Yuchen Hao, Ajit Mathews, and Shen Li. 2023. "PyTorch FSDP: Experiences on Scaling Fully Sharded Data Parallel." Proc. VLDB Endow. 16, 12 (August 2023), 3848–3860. https://doi.org/10.14778/3611540.3611569. [arXiv version](https://arxiv.org/abs/2304.11277)


#### Ring all-reduce

* Ring all-reduce was described in 2009, in Pitch Patarasuk and Xin Yuan. 2009. "Bandwidth optimal all-reduce algorithms for clusters of workstations". J. Parallel Distrib. Comput. 69, 2 (February, 2009), 117–124. https://doi.org/10.1016/j.jpdc.2008.09.002 [PDF](https://www.cs.fsu.edu/~xyuan/paper/09jpdc.pdf). 
* It was applied to distibruted deep learning by Baidu in 2017, see [Bringing HPC Techniques to Deep Learning
](https://andrew.gibiansky.com/blog/machine-learning/baidu-allreduce/). 
* Then, it gained more widespread use after it was implemented in a framework called Horovod, developed at Uber: Alexander Sergeev and Mike Del Balso. 2018. "Horovod: fast and easy distributed deep learning in TensorFlow." arXiv preprint arXiv:1802.05799. (It's still around as an open source project: [Horovod](https://github.com/horovod/horovod).) 
* It has since been included in various other deep learning frameworks.
