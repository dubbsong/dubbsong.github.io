---
layout: post
title: "arrayOfObjects.js"
categories: dev
tags: algo
---

##### 객체(object) + 배열(array) + 반복문(for loop) + 조건문(if) + 불린(boolean) 알고리즘 문제

<br>

## problem

We often deal with arrays of objects.

Add the object representing yourself

to this array of people.

<br>

Write a function that,

when passed an array of people as an argument,

returns an array of their full names.

<br>

Write a function that finds the average age

of the people array.

<br>

Write a function that,

when given people and an age as arguments,

returns an array of just the people

that are older than the specified age.

<br>

## data

```javascript
const people = [
   { name: { first: 'Sam', middle: 'D.', last: 'Azor' }, age: 25 },
   { name: { first: 'Ralph', last: 'Donovan' }, age: 35 },
   { name: { first: 'Becky', last: 'Daniel' }, age: 30 },
   { name: { first: 'Lauren', middle: 'E.', last: 'Hernandez' }, age: 30 }
];
```

<br>

## function (getFullNames)

```javascript
function getFullNames(people) {
   let result = [];
   
   for (let person of people) {
      if (person.name.middle) {
         result.push(person.name.first + ' ' + person.name.middle + ' ' + person.name.last);
      } else {
         result.push(person.name.first + ' ' + person.name.last);
      }
   }
   return result;
}


getFullNames(people);
// [ 'Sam D. Azor', 'Ralph Donovan', 'Becky Daniel', 'Lauren E. Hernandez' ]
```

<br>

## function (averageAge)

```javascript
function averageAge(people) {
   let result = 0;
   
   for (let person of people) {
      result += person.age;
   }
   return result / people.length;
}


averageAge(people);	// 30
```

<br>

## function (filterMinimumAge)

```javascript
function filterMinimumAge(people, age) {
   let result = [];
   
   for (let person of people) {
      if (person.age > age) {
         result.push(person);
      }
   }
   return result;
}


filterMinimumAge(people, 30);
// [ { name: { first: 'Ralph', last: 'Donovan' }, age: 35 } ]
```

