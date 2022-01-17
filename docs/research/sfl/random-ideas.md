---
layout: default
title: Random Ideas
parent: Social Futures Lab
grand_parent: Research
nav_order: 100
---

# Random Ideas

Social Futures Lab
{: .fs-6 .fw-300 }

Unorganized seedlings of ideas, perhaps promising or stupid or both.

---

## Modeling Schools of Thought in a Dynamic, End-to-End Manner
Many tasks often have multiple plausible answers. As such, crowdsourced data annotated by large crowds on organized platforms like Amazon Mechanical Turk or unstructured platforms like Twitter or social media broadly. Data like this is often full of disagreement depending on the annotators' backgrounds, beliefs, and reasoning systems. In this case, the goal should be to model and represent multiple voices in the annotated dataset rather than a single output to be interpreted as the 'golden truth'.

Consider *UnnamedNet*, an end-to-end neural network architecture trained directly on individual samples or batches of annotations (rather than aggregate-level distribution prediction). Inputs are interpreted through $$n$$ different *extractive branches*, which extract and interpret features according to different 'belief systems'. The resulting features are processed by the same universal processing branch, with weight sharing implemented. The network produces $$n$$ outputs, representing $$n$$ schools of thought.

![image](https://user-images.githubusercontent.com/73039742/149686232-a8b7da6e-b9f3-4225-a2b3-c5df9f4b837e.png)

The architecture weights are optimized by a custom loss, which is equal to the loss incurred between the best prediction (out of any output) and the annotated label. The loss can also be modified to incorporate the performance of other branches into the calculation with weighted influence by closeness. The goal of this loss function is to allow for multiple different output schemes to exist and match to similar labels.

Guan et al. describe a similar approach of a multi-output model in ["Who Said What: Modeling Individual Labelers Improves Classification"](https://arxiv.org/pdf/1703.08774.pdf){:target="_blank"}; a network predicts the outputs of each individual labeler, and in the second training phase the optimal weighting for each labeler is learned. However, Guan's approach - while suitable in the context of 'expert annotation' - does not scale to large crowdsourcing operations, with many more labelers. Instead, a multi-output model should ideally model *'schools of thought'*.

One problem in the architecture is the optimal determination of $$n$$. It becomes a bit of a clustering problem. We can dynamically size $$n$$ throughout training or attempt to introduce regularization penalties for the network to find the best $$n$$ by itself.

To use the final model, we can make use of Guan et al.'s method of learning optimal weights. Alternatively, developers using the application can perform analysis on the behavior of each branch (i.e. the systems and beliefs it generally encompasses) and isolate individual branches while excluding others, which may represent undesirable, toxic, or incorrect viewpoints/annotation methods.

---

## Discretized Distribution Modeling for Regression Confidence


