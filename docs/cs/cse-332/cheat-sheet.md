---
layout: default
title: Cheat Sheet
parent: CSE 332
grand_parent: Computer Science
nav_order: 3
---

# Cheat Sheet (Final Exam Study Guide)
{: .no_toc }

CSE 332
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

## Sorts

| Sort | Runtime | Stability | In-Place |
| Insertion Sort | Best Case: $$\mathcal{O}(n)$$. Worst Case: $$\mathcal{O}(n^2)$$. Average case: $$\mathcal{O}(n^2)$$ | Stable | In-Place |
| Selection Sort | $$\mathcal{O}(n^2)$$ | Stable | In-Place |
| Heap Sort | $$\mathcal{O}(n\log n)$$ | Not Stable | In-Place |
| Merge Sort | $$\mathcal{O}(n\log n)$$ | Stable | Not In-Place |
| Quick Sort (Hoare Partition) | Best Case: $$\mathcal{O}(n\log n)$$. Worst Case: $$\mathcal{O}(n^2)$$. Average case: $$\mathcal{O}(n\log n)$$ | Not Stable | In-Place |
| Bucket Sort | $$\mathcal{O}(n+k)$$ | Stable | Not In-Place |
| Radix Sort | $$\mathcal{O}(d \cdot (n+k))$$ | Stable | Not In-Place |

### Insertion Sort
Main a sorted subarray at the beginning of the array.
1. Sort the first 2 elements.
2. Insert the third element, in order.
3. Insert the fourth element, in order.
4. ...

```
5 2 3 1 4 9 8 7 6 0     i = 0
2 5 3 1 4 9 8 7 6 0     i = 1
2 3 5 1 4 9 8 7 6 0     i = 2
1 2 3 5 4 9 8 7 6 0     i = 3
1 2 3 4 5 9 8 7 6 0     i = 4
1 2 3 4 5 9 8 7 6 0     i = 5
1 2 3 4 5 8 9 7 6 0     i = 6
1 2 3 4 5 7 8 9 6 0     i = 7
1 2 3 4 5 6 7 8 9 0     i = 8
0 1 2 3 4 5 6 7 8 9     i = 9
```

### Selection Sort
Maintain a sorted subarray at the   end of the array.
1. Find the smallest element in the array.
2. Swap it with the first element. (of the unsorted subarray)
3. Repeat.

```
5 2 3 1 4 9 8 7 6 0     i = 0
0 2 3 1 4 9 8 7 6 5     i = 1
0 1 3 2 4 9 8 7 6 5     i = 2
0 1 2 3 4 9 8 7 6 5     i = 3
0 1 2 3 4 9 8 7 6 5     i = 4
0 1 2 3 4 5 8 7 6 9     i = 5   
0 1 2 3 4 5 6 7 8 9     i = 6
0 1 2 3 4 5 6 7 8 9     i = 7
0 1 2 3 4 5 6 7 8 9     i = 8
0 1 2 3 4 5 6 7 8 9     i = 9
```

### Heap Sort
1. Build a max heap.
2. Swap the first and last elements.
3. Remove the last element from the heap.
4. Repeat.

### Merge Sort
1. Split the array in half.
2. Recursively sort each half.
3. Merge the two sorted halves.

### Quick Sort
1. Pick a pivot.
2. Partition the array around the pivot.
3. Recursively sort each half.

Hoare partition

### Bucket Sort

### Radix Sort

---

## Graphs

### Dijkstra's Algorithm

### Prim's Algorithm

### Kruskal's Algorithm

