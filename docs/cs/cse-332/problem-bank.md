---
layout: default
title: Problem Bank
parent: CSE 332
grand_parent: Computer Science
nav_order: 4
---

# Problem Bank
{: .no_toc }

CSE 332
{: .fs-6 .fw-300 }

---

## 2019 Winter Final

## 2019 Autumn Final

## 2015 Winter Final

## 2012 Winter Final

## 2012 Summer Final

## 2012 Spring Final

## 2010 Summer Final

## 2010 Spring Final

**Q1.** Suppose we sort an array of numbers, but it turns out every element of the array is the same, e.g.,
{17, 17, 17, ..., 17}. (So, in hindsight, the sorting is useless.)

*What is the asymptotic running time of insertion sort in this case?*

The runtime is $$\mathcal{O}(n)$$ because the algorithm begins from the first 2 elements and progressively inserts the $$i$$th element into the sorted subarray such that it remains sorted. Because all of the elements are the same this insertion is totally uneeded, and we end up just looping through the array. 

*What is the asymptotic running time of selection sort in this case?*

The runtime is $$\mathcal{O}(n^2)$$ because the algorithm begins from the first 2 elements and progressively swaps the $$i$$th element with the smallest element in the unsorted subarray. Because all of the elements are the same this swap is totally uneeded, and we end up just looping through the array. Selection sort always uses $$\mathcal{O}(n^2)$$ time because it always loops through the array at each index of the array.
   
*What is the asymptotic running time of merge sort in this case?*

The runtime is $$\mathcal{O}(n\log n)$$ because the algorithm recursively splits the array in half until it reaches the base case of an array of size 1. Then it merges the arrays back together. Because all of the elements are the same, the merge is totally uneeded, and we end up just splitting the array in half until we reach the base case. Merge sort always uses $$\mathcal{O}(n\log n)$$ time because it always splits the array in half $$\log n$$ times and merges the arrays back together $$n$$ times.

*What is the asymptotic running time of quick sort in this case?*

The runtime is $$\mathcal{O}(n^2)$$ because the algorithm recursively partitions the array into 2 subarrays based on a pivot element. Because all of the elements are the same, the partition is totally uneeded, and we end up just splitting the array in half until we reach the base case. Quick sort always uses $$\mathcal{O}(n^2)$$ time because it always splits the array in half $$\log n$$ times and partitions the arrays back together $$n$$ times.

