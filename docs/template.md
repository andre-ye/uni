---
layout: default
title: Template
nav_exclude: true
---

# Templates

Discipline-Level:

```
---
layout: default
title: Mathematics
nav_order: 3
has_children: true
permalink: /docs/math
---

# Mathematics Notes

Calculus, Linear Algebra, Abstract Algebra+ Classes
{: .fs-6 .fw-300 }

```

Class-Level:

```
---
layout: default
title: MATH 124
parent: Mathematics
nav_order: 1
permalink: /docs/math/math-124
has_children: true
---

# MATH 124

Calculus w/ Analytic Geometry I
{: .fs-6 .fw-300 }

Natalie Naehrig
{: .label }

Fall 2021
{: .label .label-green }

5 Credits
{: .label .label-purple }
```

Note-Level:

```
---
layout: default
title: Lecture Notes
parent: MATH 125
grand_parent: Mathematics
nav_order: 1
---

# Lecture Notes

MATH 125
{: .fs-6 .fw-300 }

---

## Navigation

---


## Week 1 Monday - Antiderivatives and Syllabus
```
