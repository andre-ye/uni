---
layout: default
title: PHIL 120
parent: Philosophy
nav_order: 120
permalink: /docs/phil/phil-120
has_children: true
---

# PHIL 120

Introduction to Logic
{: .fs-6 .fw-300 }

Ian Schnee
{: .label }

Spring 2022
{: .label .label-green }

5 Credits
{: .label .label-purple }

My favorite BOOL proof:

```
1.  PvQ           Premise
2.  QvR           Premise
3.  | P           Assume
4.  || Q          Assume
5.  || Qv(P&R)    vIntro;4
6.  || R          Assume
7.  || P&R        &Intro;3,6
8.  || Qv(P&R)    vIntro;7
9.  | Qv(P&R)     vElim;2,4-5,6-8
10. | Q           Assume
11. | Qv(P&R)     vIntro;10
12. Qv(P&R)       vElim;1,3-9,10-11
```
