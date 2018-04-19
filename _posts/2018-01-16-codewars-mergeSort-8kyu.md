---
layout: post
title: "mergeSort.js (8kyu)"
categories: codewars
tags: Algorithm Codewars
---

#### 조건문(if) + 반복문(for loop) + 메소드 활용 알고리즘 문제

<br>

## problem

You are given two sorted arrays

that contain only integers.

<br>

Your task is to find a way

to merge them into a single one,

sorted in '`ascending order`'.

<br>

> \* '`array1`' and '`array2`' may be sorted in different orders.
>
> \* '`array1`' and '`array2`' may have same integers.
>
> \* Remove duplicated in the returned result.

<br>

## solution 01

```javascript
function mergeSort(array1, array2) {
   let merged = array1.concat(array2);
   let sorted = merged.sort((a, b) => a - b);
   let result = [];
   
   for (let i = 0; i < sorted.length; i++) {
      if (!result.includes(sorted[i])) {
         result.push(sorted[i]);
      }
   }
   return result;
}


mergeSort([1, 2], [3, 4]);	// [1, 2, 3, 4]
mergeSort([1, 3], [2, 4]);	// [1, 2, 3, 4]
mergeSort([1, 3], [1, 10]);	// [1, 3, 10]
```

<br>

## solution 02

```javascript
function mergeSort(array1, array2) {
   let mergeSorted = array1.concat(array2).sort((a, b) => a - b);
   let result = [];
   
   for (let i = 0; i < mergeSorted.length; i++) {
      if (!result.includes(mergeSorted[i])) {
         result.push(mergeSorted[i]);
      }
   }
   return result;
}


mergeSort([1, 2], [3, 4]);	// [1, 2, 3, 4]
mergeSort([1, 3], [2, 4]);	// [1, 2, 3, 4]
mergeSort([1, 3], [1, 10]);	// [1, 3, 10]
```

<br>

## solution 03

```javascript
function mergeSort(array1, array2) {
   let merged = [...array1, ...array2];
   let sorted = merged.sort((a, b) => a - b);
   let result = [];
   
   for (let i = 0; i < sorted.length; i++) {
      if (!result.includes(sorted[i])) {
         result.push(sorted[i]);
      }
   }
   return result;
}


mergeSort([1, 2], [3, 4]);	// [1, 2, 3, 4]
mergeSort([1, 3], [2, 4]);	// [1, 2, 3, 4]
mergeSort([1, 3], [1, 10]);	// [1, 3, 10]
```

<br>

## solution 04

```javascript
function mergeSort(array1, array2) {
   return array1.concat(array2).sort((a, b) => a - b).filter((element, index, arr) => arr.indexOf(element) === index);
}


mergeSort([1, 2], [3, 4]);	// [1, 2, 3, 4]
mergeSort([1, 3], [2, 4]);	// [1, 2, 3, 4]
mergeSort([1, 3], [1, 10]);	// [1, 3, 10]
```

<br>

## solution 05

```javascript
function mergeSort(array1, array2) {
   return Array.from(new Set(array1.concat(array2).sort((a, b) => a - b)));
}


mergeSort([1, 2], [3, 4]);	// [1, 2, 3, 4]
mergeSort([1, 3], [2, 4]);	// [1, 2, 3, 4]
mergeSort([1, 3], [1, 10]);	// [1, 3, 10]
```

