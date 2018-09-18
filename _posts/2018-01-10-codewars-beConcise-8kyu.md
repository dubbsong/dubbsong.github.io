---
layout: post
title: "beConcise.js (8kyu)"
categories: codewars
tags: Algorithm Codewars
---

#### 조건문(if) + 불린(boolean) 알고리즘 문제

<br>

## problem

Refactor and shorten the function.

<br>

## original function

```javascript
function describeAge(age) {
   if (age <= 12) {
      return "You're a(n) kid";
   } else if (age >= 13 && age <= 17) {
      return "You're a(n) teenager";
   } else if (age >= 18 && age <= 64) {
      return "You're a(n) adult";
   } else {
      return "You're a(n) elderly";
   }
}


describeAge(8);		// You're a(n) kid
describeAge(17);	// You're a(n) teenager
describeAge(19);	// You're a(n) adult
describeAge(65);	// You're a(n) elderly
```

<br>

## solution 01

```javascript
function describeAge(age) {
   return "You're a(n) " + (age < 13 ? "kid" : age < 18 ? "teenager" : age < 65 ? "adult" : "elderly");
}


describeAge(8);		// You're a(n) kid
describeAge(17);	// You're a(n) teenager
describeAge(19);	// You're a(n) adult
describeAge(65);	// You're a(n) elderly
```

<br>

## solution 02

```javascript
const describeAge = age => `You're a(n) ${age < 13 ? 'kid' : age < 18 ? 'teenager' : age < 65 ? 'adult' : 'elderly'}`;


describeAge(8);		// You're a(n) kid
describeAge(17);	// You're a(n) teenager
describeAge(19);	// You're a(n) adult
describeAge(65);	// You're a(n) elderly
```



