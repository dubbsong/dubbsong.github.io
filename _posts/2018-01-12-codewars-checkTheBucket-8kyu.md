---
layout: post
title: "checkTheBucket.js (8kyu)"
categories: codewars
tags: Algorithm Codewars
---

#### 조건문(if) + 반복문(for loop) + 메소드 활용 알고리즘 문제

<br>

## problem

You need to check if there is '`gold`' in the bucket,

and if so, return '`true`'.

If not, return '`false`'.

<br>

## solution 01

```javascript
function checkTheBucket(bucket) {
   let result = false;
   
   for (let i = 0; i < bucket.length; i++) {
      if (bucket[i] === 'gold') {
         result = true;
      }
   }
   return result;
}


checkTheBucket(['stone', 'stone', 'stone']);	// false
checkTheBucket(['stone', 'stone', 'gold']);	// true
```

<br>

## solution 02

```javascript
function checkTheBucket(bucket) {
   return bucket.includes('gold');
}


checkTheBucket(['stone', 'stone', 'stone']);	// false
checkTheBucket(['stone', 'stone', 'gold']);	// true
```

<br>

## solution 03

```javascript
const checkTheBucket = bucket => bucket.includes('gold');


checkTheBucket(['stone', 'stone', 'stone']);	// false
checkTheBucket(['stone', 'stone', 'gold']);	// true
```

