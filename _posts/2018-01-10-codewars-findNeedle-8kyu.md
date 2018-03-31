---
layout: post
title: "findNeedle.js (8kyu)"
categories: codewars
tags: Algorithm Codewars
---

#### 배열(array) 알고리즘 문제

<br>

## problem

Can you find the needle in the haystack?

<br>

Write a function '`findNeedle`'

that takes an array full of junk

but containing one 'needle'.

<br>

After your function finds the needle

it should return a message that says:

"found the needle at position" plus the index

it found the needle.

<br>

## haystack

```javascript
const haystack_1 = [4, '8688', undefined, 'needle', 'ssup'];
const haystack_2 = [false, 'a piece of hay', 4, true, 'needle'];
const haystack_3 = [1, 2, 3, 4, 8, 6, 8, 8, 'needle', 4, 2, 9, 4];
```

<br>

## solution 01

```javascript
function findNeedle(haystack) {
   return `found the needle at position ${haystack.indexOf('needle')}`;
}


findNeedle(haystack_1);	// found the needle at position 3
findNeedle(haystack_2);	// found the needle at position 4
findNeedle(haystack_3);	// found the needle at position 8
```

<br>

## solution 02

```javascript
const findNeedle = haystack => `found the needle at position ${haystack.indexOf('needle')}`;


findNeedle(haystack_1);	// found the needle at position 3
findNeedle(haystack_2);	// found the needle at position 4
findNeedle(haystack_3);	// found the needle at position 8
```

