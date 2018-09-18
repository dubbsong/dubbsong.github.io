---
layout: post
title: "betterThanAverage.js (8kyu)"
categories: codewars
tags: Algorithm Codewars
---

#### 반복문(for loop) 알고리즘 문제

<br>

## problem

You got an array with your colleges' points.

Now calculate the average to your points.

<br>

Return '`True`' if you're better,

else '`False`';

<br>

## solution 01

```javascript
function betterThanAverage(classPoints, yourPoints) {
   let result = 0;
   
   for (let i = 0; i < classPoints.length; i++) {
      result += classPoints[i];
   }
   result = result / classPoints.length;
   return yourPoints > result;
}


betterThanAverage([20, 40, 60, 80], 50);	// false
betterThanAverage([20, 40, 60, 80], 51);	// true
```

<br>

## solution 02

```javascript
function betterThanAverage(classPoints, yourPoints) {
   return yourPoints > classPoints.reduce((a, b) => a + b, 0) / classPoints.length;
}


betterThanAverage([20, 40, 60, 80], 50);	// false
betterThanAverage([20, 40, 60, 80], 51);	// true
```

