---
layout: post
title: "(8kyu.js) Even or Odd"
categories: codewars
---

<br>

## problem

- Create a function that takes an integer as an argument and returns `Even` for even numbers or `Odd` for odd numbers.
  - 정수를 인수로 가져오고, 짝수의 경우 `Even`을, 홀수의 경우 `Odd`를 반환하는 함수를 생성해라.

------

<br>

### solution 01

```js
function even_or_odd(number) {
   if (number % 2 === 0) {
      return 'Even';
   } else {
      return 'Odd';
   }
}


even_or_odd(2);	// Even
even_or_odd(1);	// Odd
```

<br>

### solution 02

```js
function even_or_odd(number) {
   return number % 2 === 0 ? 'Even' : 'Odd';
}


even_or_odd(2);	// Even
even_or_odd(1);	// Odd
```

<br>

### solution 03

```js
function even_or_odd(number) {
   return number % 2 ? 'Odd' : 'Even';
}


even_or_odd(2);	// Even
even_or_odd(1);	// Odd
```

<br>

### solution 04

```js
const even_or_odd = number => number % 2 ? 'Odd' : 'Even';


even_or_odd(2);	// Even
even_or_odd(1);	// Odd
```

------

<br>
