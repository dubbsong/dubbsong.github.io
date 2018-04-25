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

<br>

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


bouncer('Leo', 20);	// Go home, Leo.
bouncer('Sam', 21);	// Welcome, Sam!
```

> `조건문 (if/else)`
>
> `if` (조건식) `{` return true; `}`
>
> `else` `{` return false; `}`

<br>

## solution 02

```javascript
function bouncer(name, age) {
   return age >= 21 ? `Welcome, ${name}!` : `Go home, ${name}.`;
}


bouncer('Leo', 20);	// Go home, Leo.
bouncer('Sam', 21);	// Welcome, Sam!
```

> `삼항 연산자 (ternary operator)`
>
> 조건식 `?` 조건이 true일 때 반환하는 값 `:` 조건이 false일 때 반환하는 값

<br>

## solution 03

```javascript
const bouncer = (name, age) => age >= 21 ? `Welcome, ${name}!` : `Go home, ${name}.`;


bouncer('Leo', 20);	// Go home, Leo.
bouncer('Sam', 21);	// Welcome, Sam!
```

> `Arrow function`(`=>`)은 [함수 표현식](https://dubbsong.github.io/javascript/2017/11/14/js-function-expression/)을 사용한다.
>
> `const` 변수명 `=` 매개변수 `=>` 조건식 `?` true `:` false

<br>