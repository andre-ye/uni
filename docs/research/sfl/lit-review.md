---
layout: default
title: Literature Review Notes
parent: Social Futures Lab
grand_parent: Research
nav_order: 5
---

# Literature Review Notes

Social Futures Lab
{: .fs-6 .fw-300 }

Notes from relevant papers reviewed or cited for research.

---

## Navigation
* [Navigation](#navigation)
* [Learning from Disagreement: A Survey](#learning-from-disagreement--a-survey)
* [Learning Supervised Topic Models for Classification and Regression from Crowds](#learning-supervised-topic-models-for-classification-and-regression-from-crowds)
* [Who Said What: Modeling Individual Labelers Improves Classification](#who-said-what--modeling-individual-labelers-improves-classification)
* [AggNet: Deep Learning from Crowds for Mitosis Detection in Breast Cancer Histology Images](#aggnet--deep-learning-from-crowds-for-mitosis-detection-in-breast-cancer-histology-images)
* [Learning from Crowds in the Presence of Schools of Thought](#learning-from-crowds-in-the-presence-of-schools-of-thought)

---


## Learning from Disagreement: A Survey
Alexandra N. Uma (Queen Mary), Tommaso Fornaciari (Bocconi), Dirk Hovy (Bocconi), Silviu Paun (Queen Mary), Barbara Plank (IT @ Copenhagen), Massimo Poesio (Queen Mary)

Access [here](https://www.jair.org/index.php/jair/article/view/12752/26751){:target="_blank"}.


---

## Learning Supervised Topic Models for Classification and Regression from Crowds
Filipe Rodrigues, Mariana Lourenco, Bernardete Ribeiro, Francisco C. Pereira.

Access [here](https://arxiv.org/pdf/1808.05902.pdf){:target="_blank"}

---

## Who Said What: Modeling Individual Labelers Improves Classification
Melody Guan (Stanford), Varun Gulshan (Google Brain), Andrew M. Dai (Google Brain), Geoffrey E. Hinton (Google Brain).

Access [here](https://arxiv.org/pdf/1703.08774.pdf){:target="_blank"}

---

## AggNet: Deep Learning from Crowds for Mitosis Detection in Breast Cancer Histology Images
Shadi Albarqouni, Christoph Baur, Felix Achilles, Vasileios Belagiannis, et al.

Access [here](https://ieeexplore.ieee.org/document/7405343){:target="_blank"}

---

## Learning from Crowds in the Presence of Schools of Thought
Yuandong Tian (Carnegie Mellon) and Jun Zhu (Tsinghua).

Access [here](https://yuandong-tian.com/kdd2012-tian.pdf){:target="_blank"}.

**Introduction**

- Crowdsourcing has become popular as an effective way to collect large-scale experimental data from distributed workers.
- Key problem: reliable workers and unambiguous tasks.
- Goal: to estimate worker reliability and task clarity without resorting to a single gold standard assumption; this makes it applicable to subjective tasks with multiple reasonable answers.
- *Schools of Thought* - phenomenon caused by differing cultural and educational background.
- Worker reliability and task clarity.
- Assumptions in grouping behavior with schools of thought:
  1. Reliable workers tend to agree with other workers in many tasks.
  2. The answers to a clear task tend to form tight clusters.
- Apply nonparametric Bayesian clustering to bypass model selection problem of determining an unknown number of clusters/schools.

**A Low-Rank Schools of Thought Model**
Let:
- $$N$$ be the number of workers
- $$K$$ be the number of tasks
- $$\lambda_i > 0$$ be a scalar to model constant reliability of a worker $$i$$
- $$\mu_k > 0$$ be a scalar to model constant degree of clarity of a task $$k$$ for all workers

Assumptions:
1. A worker $$i$$ who is consistent with many other workers in most of the tasks is reliable. Thus, $$\lambda_i$$ is large.
2. A task $$k$$ whose answers form a few tight clusters is easy, well-addressed, and objective -- $$\mu_k$$ is large. A task whose ansers form lots of small clusters is complicated, confusing, and subjective -- $$\mu_k$$ is small.

Perform a rank-1 factorization of the $$N\times K$$ worker-task matrix.

Dirichlet Process mixture model to resolve unknown number of clusters $$M_k$$.

*Algorithm*: estimation of worker reliability and task calrity with schools of thoguht:
```
for k = 1 in K, do
  compute the posterior that worker i and j are in the same group,
  compute the expected group size.
end for
Run SVD on the expected worker-task matrix,
Determine the worker reliability and task clarity from decomposition.
```

**Personal Notes**
- Very statistically/mathematically inclined technique for estimating worker reliability and task clarity
- Unclear how to utilize worker reliability and task clarity in model training and development - potential area to look more into
- How can the metric be exploited to artificially increase worker reliability if deployed in a higher-reliability-higher-pay annotation model?
