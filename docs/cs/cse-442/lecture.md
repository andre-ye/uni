---
layout: default
title: Lecture Notes
parent: CSE 442
grand_parent: Computer Science
nav_order: 1
---

# Lecture Notes
{: .no_toc }

CSE 442
{: .fs-6 .fw-300 }

---

<details open markdown="block">
  <summary>
    Table of contents
  </summary>
  {: .text-delta }
1. TOC
{:toc}
</details>

---

## Week 2 Tuesday: Data and Image Models

- Task, data, and domain $$\to $$ processing algorithms and mapping $$\to$$ image

Data Models / Conceptual Models
- Data models are formal descriptions
- Conceptual models are mental constructions
- Schneiderman 1996: one-dimensional (sets and sequences), temporal, two-dimensional (maps), three-dimensional (shapes), n-dimensional (relational), trees (hierarchies), networks (graphs)
- Nominal, ordinal, quantiative (interval, ratio)
- Dimensions: discrete, usually independent, variables describing data
- Measures: dependent variables, data values that can be aggregated (usually quantiative)

Relational Data Model
- Represent data as a table or relation
- Relational algebra (Codd 1970) -- operations on data tables, table in table out
- Roll-up (data along desired dimensions) and drill-down

Tidy Data (Wickham 2014)
- Every variable forms a column
- Every observation forms a row
- Every type of observational unit forms a table
- 'Normalized forms'in database theory

Common Data Formats
- CSV
- JSON


Image Models
- Jacques Bertin -- *The Semiology of Graphics*, using imagery to encode information, the first theoretical work in visual encoding
- Visual language is a sign system
- "Resemblance, order, and proportional are the three signfields in graphics." 
- Visual encoding variables: position, size, value, texture, color, orientation, shape, tlransparency, blur/focus, length/area/volume

Formalizing Design
- Assuming $$k$$ visual encodings and $$n$$ data attributes
- We want to pick the best encoding among $$(n+1)^k$$ possible encodings
- Principle of consistency, principle of importance ordering
- Design criteria (Mackinlay 1986): expressiveness and effectiveness
- "tell the truth and nothing but the truth"
- Effectiveness of encodings by data type
- Mackinlay's design algorithm, 1986 "A Presentation Tool"; user formally specifies data model and type, tests expressiveness, and generates encodings that pass test
- 