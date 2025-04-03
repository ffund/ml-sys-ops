---
title: Evaluation and monitoring
layout: page
parent: Units
nav_order: 7
---

# Evaluation and monitoring

In the lifecycle of a machine learning model, between "training" and "deployment to production" there is an evaluation stage! In this week's lesson, we talked about evaluating a model, including:

* evaluation on general optimizing metrics (e.g. loss, accuracy) and domain-specific metrics (e.g. perplexity, BLEU, ROUGE for text generation)
* evaluation on those same metrics, for slices and populations of interest
* evaluation on operational metrics (e.g. inference latency on a single sample, batch throughput, time/cost to retrain model, memory required for inference)
* behavioral testing, with template-based unit tests to make sure that the model is robust to perturbations that should NOT change its output, and has the correct behavior for perturbations that SHOULD change its output
* sanity-checking via explainability techniques (e.g. feature importance, SHAP, LIME, saliency maps, attention-based explanations)
* and regression testing for previous "known errors"

The tests above should be run in an automated way as part of a "continuous X" pipeline, but we may also want human-in-the-loop testing ("red teaming") or even GenAI-in-the-loop testing.

We further discussed use-case specific tests, with many examples; and tests of the overall model serving system, not just the model in isolation.

For a model that passes "offline" tests, we may then proceed to an online evaluation, including:

* shadow testing, where user requests are duplicated to both the old system and new system (responses from the new system are not shown to users!)
* canary testing, where a small fraction of user requests are served by the new system
* A/B testing, where user requests are routed to either the old or new system, and we compare them on business-specific metrics. As an example, we looked at how Target did an online evaluation of a [new model for bundled product recommendations](https://tech.target.com/blog/bundled-product-recommendations). Through A/B testing, they were able to directly attribute an increase in "click-based revenue" to the new model.

Once a model is deployed in production, we will be concerned with prediction monitoring in production. We anticipate that over time, the performance of a model may degrade due to various types of drift, including covariate shift, label shift, and concept drift. When the model becomes "stale", we will want to know that its performance has degraded, and re-train it on new data. Therefore, we must monitor the quality of predictions.

However, this is challenging because in production, we do not necessarily have ground truth labels for new data:

* *some* use cases may have natural ground truth labels
* sometimes we may have a delayed natural ground truth label, and in the meantime, we may be able to use a proxy label but it is not necessarily valid or helpful for optimizing
* we may rely on user feedback, but it is often sparse and/or incorrect
* for use cases where it is possible for a human to label new samples, we may get human labels for a random fraction of new samples, for samples where the model has low confidence, or for samples where the user provides feedback that the model was incorrect

Finally, we discussed many other tests of the overall machine learning pipeline. 

[Slides: Evaluation and monitoring](https://link.excalidraw.com/p/readonly/ou20L4JKbnqIPG4CiuaO){: .btn .btn-purple }

## Lab assignment

Due TBD
{: .label .label-yellow}

This lab assignment is in three parts (which you can do in any order):

[Lab: Part 1: Offline evaluation of ML systems](https://teaching-on-testbeds.github.io/eval-offline-chi/){: .btn .btn-green } 
[Lab: Part 2: Online evaluation of ML systems](https://teaching-on-testbeds.github.io/eval-online-chi/){: .btn .btn-green } 
[Lab: Part 3: Closing the feedback loop](){: .btn .btn-outline }

The first two parts are released in "Preview" mode, until the last part is also released; the due date will be set and the Gradescope submission will open when all parts are ready.

{:.important }
> Resource usage notes for this lab assignment:
> 
> * You will do this lab assignment on KVM@TACC, which does not require reservation.
> * You can do the parts in any order, but you should only do one at a time - you must delete resources from a previous part before you start another part.
> * Your resources may not be “active” for more than eight daytime (8AM - 11:59PM) hours. They may be deleted by course staff otherwise.



## Reading

Our main reference this week was:

* E. Breck, S. Cai, E. Nielsen, M. Salib and D. Sculley, "The ML test score: A rubric for ML production readiness and technical debt reduction," 2017 IEEE International Conference on Big Data (Big Data), Boston, MA, USA, 2017, pp. 1123-1132, doi: 10.1109/BigData.2017.8258038. [Link](https://research.google/pubs/the-ml-test-score-a-rubric-for-ml-production-readiness-and-technical-debt-reduction/)

You may also be interested in:

* this paper about template-based unit tests: Ribeiro, Marco Tulio, Wu, Tongshuang, Guestrin, Carlos, and Singh, Sameer. "Beyond Accuracy: Behavioral Testing of NLP Models with CheckList". In Proceedings of the 58th Annual Meeting of the Association for Computational Linguistics (ACL 2020). [Link](https://idl.uw.edu/papers/check-list) [Github](https://github.com/marcotcr/checklist)
* this paper on GenAI-in-the-loop testing for language tasks:  Marco Tulio Ribeiro and Scott Lundberg. "Adaptive Testing and Debugging of NLP Models" . In Proceedings of the 60th Annual Meeting of the Association for Computational Linguistics (ACL 2022). [Link](https://aclanthology.org/2022.acl-long.230/) [Github](https://github.com/microsoft/adaptive-testing)
* or, this one on GenAI-in-the-loop testing for computer vision tasks: Irena Gao, Gabriel Ilharco, Scott Lundberg, Marco Tulio Ribeiro. "Adaptive Testing of Computer Vision Models". In Proceedings of the IEEE/CVF International Conference on Computer Vision (ICCV 2023). [Link](https://openaccess.thecvf.com/content/ICCV2023/html/Gao_Adaptive_Testing_of_Computer_Vision_Models_ICCV_2023_paper.html)
