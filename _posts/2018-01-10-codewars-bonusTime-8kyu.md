---
layout: post
title: "bonusTime.js (8kyu)"
categories: codewars
tags: Algorithm Codewars
---

#### 조건문(if) 알고리즘 문제

<br>

## problem

Build a function that takes in two arguments (salary, bonus).

Salary will be an integer, and bonus a boolean.

<br>

If bonus is true,

the salary should be multiplied by 10.

If bonus is false,

the fatcat did not make enough money

and must receive only his stated salary.

<br>

Return the total figure

the individual will reveive as a string prefixed

with '£' or '$'.

<br>

## solution 01

```javascript
function bonusTime(salary, bonus) {
   return bonus ? `£${salary * 10}` : `£${salary}`;
}


bonusTime(10, true);		// £100
bonusTime(4000, false);		// £4000
```

<br>

## solution 02

```javascript
function bonusTime(salary, bonus) {
   return '£' + salary * (bonus ? 10 : 1);
}


bonusTime(10, true);		// £100
bonusTime(4000, false);		// £4000
```

<br>

## solution 03

```javascript
const bonusTime = (salary, bonus) => `£${salary * (bonus ? 10 : 1)}`;


bonusTime(10, true);		// £100
bonusTime(4000, false);		// £4000
```



