---
layout: post
title: "busStop.js (8kyu)"
categories: codewars
tags: Algorithm Codewars
---

#### 반복문(for loop) + 배열(array) 알고리즘 문제

<br>

## problem

There is a bus moving in the city,

and it takes and drop some people in each bus stop.

<br>

You are provided with a list(or array) of integer arrays.

Each integer array has two items

which represent number of people get into bus

and number of people get off the bus

in a bus stop.

<br>

Your task is to return number of people

who are still in the bus

after the last bus station(after the last array).

<br>

## solution 01

```javascript
function busStop(number) {
   let result = 0;
   
   for (let i = 0; i < number.length; i++) {
      result += number[i][0];
      result -= number[i][1];
   }
   return result;
}


busStop([[10, 0], [3, 5], [5, 8]]);	// 5
```

<br>

## solution 02

```javascript
function busStop(number) {
   let result = 0;
   
   for (let i = 0; i < number.length; i++) {
      result += number[i][0] - number[i][1];
   }
   return result;
}


busStop([[10, 0], [3, 5], [5, 8]]);	// 5
```

<br>

## solution 03

```javascript
const busStop = number => number.reduce((people, [on, off]) => people + on - off, 0);


busStop([[10, 0], [3, 5], [5, 8]]);	// 5
```

