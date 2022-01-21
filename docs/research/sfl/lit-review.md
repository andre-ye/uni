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

## The Risk of Racial Bias in Hate Speech Detection
Maarten Sap, Dallas Card, Saadia Gabriel, Yejin Choi, NOah A. Smith.

Access [here](https://homes.cs.washington.edu/~msap/pdfs/sap2019risk.pdf){:target="_blank"}

- Annotator insensitivity to differences in dialect can lead to racial bias in automatic hate speech detection models.
- Models acquire biases in toxicity datasets.

**Perosnal Notes**
- The authors propose 'dialect and race priming' in annotation to show that annotators are significantly less likely to label a tweet as offensive when presented with the tweeter's dialect.
- Is this problematic?
  - People are not judging by what they think is offensive, they are now judging how they think other people may find a tweet offensive. That may be more dangerous. 
  - What if you want a model that goes by certain standards/practices?
  - The authors note that reclaimed language (e.g. 'queer', n-word) are used by communities to describe themselves but are unacceptable when an outsider is saying them. Does the user's race/sexuality need to be built into the model now? HOw does one quantify or demarcate these ideas when other scholarship suggests they are continuous or entirely discretized?
- How are the authors getting ground truth labels to measure bias when toxicity is subjective?

---

## Learning Supervised Topic Models for Classification and Regression from Crowds
Filipe Rodrigues, Mariana Lourenco, Bernardete Ribeiro, Francisco C. Pereira.

Access [here](https://arxiv.org/pdf/1808.05902.pdf){:target="_blank"}

**Introduction**
- Topic models like LDA allow us to analyze large collections of documetns by revealing their underlying themes.
- Topic models are a standard tool in data analysis.
- Documents are frequently associated with variables like labels, tags, or ratings. Supervised topic models jointly learn topic distributions and a classication or regression model.
- Supervised topic models require human labeled data.
- Quality od labels can vary significnalty due to task subjectivity and differences in annotator reliability or bias.
- Subjectiveness of an exercise is prone to generate distinct labels from different annotators.
- Propose a fully generative supervised topic model that is able to *account for different annotator reliabilities and account for biases.*

**State of the Art**
- LDA is a powerful tool for modeling documents and images by extracting underlying topics.
- sLDA includes a response variable that is linearly dependent on the mean topic assignments of words in a document.
- Learning from multiple annotators is becoming increasingly important.
- Learning classifiers from multi-annotator data.

**Classification Model**
- Batch variational inference algorithm - approximate the posterior distribution across latentt variables.

**Personal Thoughts and Notes**
- Very mathematically involved approach.
- Relies upon existence of a gold truth.
- In many cases we are not necessarily modeling something that is the truth.
- Don't know about prediction in very high prediction settings.

---

## Who Said What: Modeling Individual Labelers Improves Classification
Melody Guan (Stanford), Varun Gulshan (Google Brain), Andrew M. Dai (Google Brain), Geoffrey E. Hinton (Google Brain).

Access [here](https://arxiv.org/pdf/1703.08774.pdf){:target="_blank"}

**Introduction**
- Neural networks would ideally perform better than human experts because training labels are often unreliable; poor agreement between different experts.
- Main contribution: there are significantly better ways to use the opinions of multiple experts than to use the expert consensus or define a probability distribution.

**Beating the Teacher**
- MNIST dataset, testing out the performance of the model on validation dataset given a probability that the training labels are randomly switched to one of the other 9 classes. The model is actually very robust; until a certain point where the neural network does not "get the point".

![image](https://user-images.githubusercontent.com/73039742/149873774-4b2928e0-d88c-4df1-8652-3da2a5dc0c21.png)

- How many noisily labeled training examples are worth a correctly labeled training example?

**Methods**
- There is more information in particular labels proposed by particular annotators than is captured by simply taking the average of all doctors who have labeled an image and treating the distribution as correct.
- Instead of using a single softmax, uses as many $$K$$-way softmaxes as there are doctors; do not backpropagate error from softmaxes used to model doctors that did not annotate a sample.
- Weights for averaging doctor models should possibly be image-dependent.

![image](https://user-images.githubusercontent.com/73039742/149873585-9f015410-3fe6-4599-b572-6fec35368e98.png)

![image](https://user-images.githubusercontent.com/73039742/149876001-6ffe6707-0835-4b38-ac83-dd26233ed156.png)

**Results**
- Training with multi-class loss beats training with binary loss, *even on binary metrics*.
- Averaging modeled annotators beats modeling the average annotator. This makes sense intuitively; averaging is a reductive operation and ideally reductive operations should be performed at the end of a pipeline for maximum information retention.
- Learning averaging weights helps.

---

## Deep Learning From Crowds
Filipe Rodrigues, Francisco C. Pereira.

Access [here](https://arxiv.org/pdf/1709.01779.pdf){:target="_blank"}.

**Introduction**
- Labeled data is challenging to obtain
- Crowdsourcing provides a solution to obtain labeled data for human-like tasks
- Modern data-savvy methods are capable of handling crowdsourced data.
- Noise associated with labels can compromise applications.
- Attempting to mitigate the effects of noise and biases in heterogenous sources of data.
- Often, approaches with multiple annotators aggregfate data before training.
- This paper highlights the limitations of Expectation Maximization (EM) algorithms for learning from crowds and proposes a crowd layer. This allows neural networks to be trained end to end using noisy labels with backpropagation.
- Automatically distinguishes good from bad annotators to capture individual biases.
- Obtains superior performance on datasets via the crowd layer

**Related Work**
- Label aggregfawtion mechanisms are generally suboptimal compared to approaches that jointly learn the classifier.
- Albarqouni et al. proposed AggNet.
- Guan et al. propose modeling the outputs of individual annotators, then learning specific combinations of outputs based on the inputs.
  - No EM algorithm is required to estimate annotator weights.
  - Proposed approach has the ability to *correct* biases. 

**Crowd Layer**
- Special type of network layer that directly allows the training of a deep neural network on noisy labels with multiple annotators.
- Crowd layer takes in an input what would normally be the output of the neural network and learns an annotator-specific mapping. Output layer becomes a bottleneck layer shared by different annotators.
- The crow dlayer adjusts gradients coming from the labels of the annotator and adjusts their bias.
- Bottleneck layer aggregates and adjusts; accounts for unreliable annotators and corrects systematic biases in labeling.
- The crowd layer may need to be initialized with specific qualities.

**Personal Thoughts**
- Focus on distinguishing annotator 'reliability', trustworthiness.
- The connection between a shared output and the specific mapping is very shallow, narrow. May not be sufficient to capture difficult datasets with significant disagreement. Authors note overparametrization can damage presence of a ground truth. 



---

## AggNet: Deep Learning from Crowds for Mitosis Detection in Breast Cancer Histology Images
Shadi Albarqouni, Christoph Baur, Felix Achilles, Vasileios Belagiannis, et al.

Access [here](https://ieeexplore.ieee.org/document/7405343){:target="_blank"}

**Introduction**
- Crowdsourcing is a type of participative online activity in which multiple individuals of varying knowledge and heterogeneity undertake a task.
- Medical domain - crowdsourcing presented as a solution to lack of publicly available ground-truth data.
- Surprisingly, a crowd of non-professional, inexperienced users do not underperform medical exeprts.
- Redundnacy and Aggregation (R&A) via majority voitng.
- Questions:
  - Can deep CNNs be trained with data collected from crowdsourcing and is it robust against noisy labels?
  - How can CNNs be adapted when we have both the ground-truth label and multipel annotations that can potentially be noisy?
  - How is the accuracy compared to that obtained by ground truth or majority voting?
- AggNet - novel aggregation layer integrated into a multi-scale CNN.

![image](https://user-images.githubusercontent.com/73039742/149872737-a3a138d4-7d4e-43bd-9e51-41e20dda22e5.png)

*Fig 1 from paper. (1) the multi-scale CNN model is trained from gold-standard annotations. (2) then for any incoming unlabelled image, (3) the aggnet will produce a response map which is thresholded at selected optimal operating point. (4) these few resulting positive candidates are outsourced to crowds. (5) aggnet collects back the crowd votes and jointly aggregates the ground truth and refine the CNN model.*

**Methodology**
- Learning from crowd annotations exposes the presence of multiple different labels for the same sample.

![image](https://user-images.githubusercontent.com/73039742/149872835-0bdba726-759d-4695-ab99-47cb15cc1c71.png)

*AggNet architecture*

- The input image is downsampled into different scales.
- Patches are collected and passed into the model.
- The model is applied to augmented inputs and a final detection map is produced.
- Aggregation Layer: aggregate the ground truth from the crowdvotes matrix, compute sensitivity and specificity of each annotator, jointly learn the classifier.
- Use Expectation-Maximization algorithm

**Results**
Validated on MICCAI-AMIDA13 challenge dataset

![image](https://user-images.githubusercontent.com/73039742/149873254-0e828a94-aa06-4526-9158-70cf22ef5c23.png)

![image](https://user-images.githubusercontent.com/73039742/149873271-d0df0a1a-7381-4473-853a-3b5b972a17f2.png)

**Discussion**

- AggNet is robust to noisy labels and positive influences the performance of the CNN.
- Is it possible to learn from crowdsourced labels alone? Poor overall agreement among participatns and missing annotations renders aggregation and training impossible.
- Learn instead from expert labels with a wide but noisy crowd.

**Personal Notes**
- Applied to expert annotation tasks with theoretical (somewhat) golden standard
- Models on an annotator-by-annotator basis like many other approaches
- Pretty mathematically involved approach
- Slightly improves CNN performance, bigger gain seems to be information about annotator trustworthiness and quality.

---

## The Risk of Racial Bias in Hate Speech Detection

Access [here](https://homes.cs.washington.edu/~msap/pdfs/sap2019risk.pdf){:target="_blank"}

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
