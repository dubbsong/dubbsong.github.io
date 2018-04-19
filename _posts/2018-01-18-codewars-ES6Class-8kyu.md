---
layout: post
title: "ES6 Class.js (8kyu)"
categories: codewars
tags: Algorithm Codewars
---

#### about ES6 Class (아직 이해안감)

<br>

## problem

Define a `class Person` with the following properties:

<br>

A `constructor` that accepts 4 arguments:

- `firstName` (defaults to 'John' if not set),
- `lastName` (defaults to 'Doe' if not set),
- `age` (defaults to '0' if not set),
- `gender` (defaults to 'Male' if not set).

<br>

These should be stored in

`this.firstName`, `this.lastName`, `this.age`, `this.gender` respectively.

<br>

A method `sayFullName`

that accepts no arguments

and returns the full name.

<br>

A class/static method `greetExtraTerrestrials`

that accepts one parameter `raceName`

and returns `Welcome to Planet Earth raceName`.

<br>

## solution 01

```javascript
class Person {
   constructor(firstName = 'John', lastName = 'Doe', age = 0, gender = 'Male') {
      Object.assign(this, {firstName, lastName, age, gender});
   }
   sayFullName() {
      return `${this.firstName} ${this.lastName}`;
   }
   static greetExtraTerrestrials(raceName) {
      return `Welcome to Planet Earth ${raceName}`;
   }
}


console.log(new Person().firstName);	// John
console.log(new Person('Coco', 'Song', 31, 'Male').firstName);	// Coco
```

<br>

## solution 02

```javascript
class Person {
   constructor(firstName = 'John', lastName = 'Doe', age = 0, gender = 'Male') {
      this.firstName = firstName;
      this.lastName = lastName;
      this.age = age;
      this.gender = gender;
   }
   sayFullName() {
      return `${this.firstName} ${this.lastName}`;
   }
   static greetExtraTerrestrials(raceName) {
      return `Welcome to Planet Earth ${raceName}`;
   }
}


console.log(new Person().firstName);	// John
console.log(new Person('Coco', 'Song', 31, 'Male').firstName);	// Coco
```

