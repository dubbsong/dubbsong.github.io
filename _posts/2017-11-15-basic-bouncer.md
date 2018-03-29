---
layout: post
title: "bouncer.js"
categories: dev
tags: algo
---

#### 조건문(if) + 불린(boolean) 알고리즘 문제

<br>

Write a function called '`bouncer`'.

Given a string and an integer,

in this case a name and an age,

'bouncer' returns a message that welcomes the patron,

or tells them to go away.

\* <u>The legal drinking age in the United States is 21.</u>

\* <u>Pay close attention to the puncuation in your answer.</u>

<br>

## solution 01

```javascript
function bouncer(name, age) {
   if (age >= 21) {
      return `Welcome, ${name}!`;
   } else {
      return `Go home, ${name}.`;
   }
}


bouncer('Leo', 26);	// Welcome, Leo!
bouncer('Sam', 19);	// Go home, Sam.
```

<br>

## solution 02

```javascript
function bouncer(name, age) {
   return age >= 21 ? `Welcome, ${name}!` : `Go home, ${name}.`;
}


bouncer('Leo', 26);	// Welcome, Leo!
bouncer('Sam', 19);	// Go home, Sam.
```

