---
layout: post
title: "humanCatDogYears.js (8kyu)"
categories: codewars
tags: Algorithm Codewars
---

#### 조건문(if) + 반복문(for loop) + 불린(boolean) 알고리즘 문제

<br>

## problem

I have a cat and dog.

I got them at the same time as kitten/puppy.

That was 'humanYears' years ago.

<br>

Return their respective ages now as

[humanYears, catYears, dogYears]

<br>

> Cat Years
>
> '`15`' cat years for first year
>
> '`+9`' cat years for second year
>
> '`+4`' cat years for each year after that

<br>

> Dog Years
>
> '`15`' dog years for first year
>
> '`+9`' dog years for second year
>
> '`+5`' dog years for each year after that

<br>

## solution 01

```javascript
function humanCatDogYears(humanYears) {
   let catYears = 0;
   let dogYears = 0;
   
   for (let i = 0; i <= humanYears; i++) {
      if (i === 1) {
         catYears += 15;
         dogYears += 15;
      } else if (i === 2) {
         catYears += 9;
         dogYears += 9;
      } else {
         catYears += 4;
         dogYears += 5;
      }
   }
   return [humanYears, catYears, dogYears];
}


humanCatDogYears(1);	// [1, 15, 15]
humanCatDogYears(1);	// [2, 24, 24]
humanCatDogYears(10);	// [10, 56, 64]
```

<br>

## solution 02

```javascript
function humanCatDogYears(humanYears) {
   let catYears = humanYears <= 1 ? humanYears * 15 : humanYears * 4 + 16;
   let dogYears = humanYears <= 1 ? humanYears * 15 : humanYears * 5 + 14;
}


humanCatDogYears(1);	// [1, 15, 15]
humanCatDogYears(1);	// [2, 24, 24]
humanCatDogYears(10);	// [10, 56, 64]
```

