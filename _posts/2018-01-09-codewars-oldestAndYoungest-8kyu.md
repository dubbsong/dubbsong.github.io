---
layout: post
title: "oldestAndYoungest.js (8kyu)"
categories: codewars
tags: Algorithm Codewars
---

#### 배열(array) + 조건문(if) + 반복문(for loop) 알고리즘 문제

<br>

## problem

Return a new array

with [`youngest age`, `oldest age`,

`difference between the youngest and oldest age`].

<br>

## solution 01

```javascript
function oldestAndYoungest(ages) {
   let max = ages[0];
   let min = ages[0];
   
   for (let i = 0; i < ages.length; i++) {
      if (max < ages[i]) {
         max = ages[i];
      }
      
      if (min > ages[i]) {
         min = ages[i];
      }
   }
   return [min, max, max - min];
}


oldestAndYoungest([4, 19, 25, 31]);	// [4, 31, 27]
```

<br>

## solution 02

```javascript
function oldestAndYoungest(ages) {
   let max = ages[0];
   let min = ages[0];
   
   for (let i = 0; i < ages.length; i++) {
      if (max < ages[i]) max = ages[i];
      if (min > ages[i]) min = ages[i];
   }
   return [min, max, max - min];
}


oldestAndYoungest([4, 19, 25, 31]);	// [4, 31, 27]
```

<br>

## solution 03

```javascript
function oldestAndYoungest(ages) {
   let max = Math.max(...ages);
   let min = Math.min(...ages);
   return [min, max, max - min];
}


oldestAndYoungest([4, 19, 25, 31]);	// [4, 31, 27]
```

<br>

## solution 04

```javascript
const oldestAndYoungest = ages => (min = Math.min(...ages), max = Math.max(...ages), [min, max, max - min]);


oldestAndYoungest([4, 19, 25, 31]);	// [4, 31, 27]
```

