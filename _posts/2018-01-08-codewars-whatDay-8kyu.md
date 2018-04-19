---
layout: post
title: "whatDay.js (8kyu)"
categories: codewars
tags: Algorithm Codewars
---

#### 배열(array) + 조건문(switch) 알고리즘 문제

<br>

## problem

Write a function called '`whatDay()`'

which returns the day according to the number.

<br>

> 1 returns 'Sunday'
>
> 2 returns 'Monday'
>
> 3 returns 'Tuesday'
>
> 4 returns 'Wednesday'
>
> 5 returns 'Thursday'
>
> 6 returns 'Friday'
>
> 7 returns 'Saturday'

<br>

If it's not a number between 1-7

return 'Wrong, between 1-7'.

<br>

## solution 01

```javascript
function whatDay(number) {
   const days = [
      'Sunday',
      'Monday',
      'Tuesday',
      'Wednesday',
      'Thursday',
      'Friday',
      'Saturday'
   ];
   return days[number - 1] || 'Wrong, between 1-7';
}


whatDay(1);	// Sunday
whatDay(2);	// Monday
whatDay(4);	// Wednesday
whatDay(8);	// Wrong, between 1-7
```

<br>

## solution 02

```javascript
function whatDay(number) {
   switch (number) {
      case 1: return 'Sunday';
      case 2: return 'Monday';
      case 3: return 'Tuesday';
      case 4: return 'Wednesday';
      case 5: return 'Thursday';
      case 6: return 'Friday';
      case 7: return 'Saturday';
      default: return 'Wrong, between 1-7';
   }
}


whatDay(1);	// Sunday
whatDay(2);	// Monday
whatDay(4);	// Wednesday
whatDay(8);	// Wrong, between 1-7
```

