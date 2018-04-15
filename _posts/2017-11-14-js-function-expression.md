---
layout: post
title: "함수 표현식 / 익명 함수 / 화살표 함수"
categories: javascript
tags: JavaScript
---

## 함수 표현식 (function expression)

- 함수의 일급 객체(first-class object) 특성을 이용하여 `함수 리터럴` 방식으로 함수를 정의하고 변수에 할당할 수 있다.

```javascript
var foo = function multiply(a, b) {
   return a * b;
}
```

<br>

## 익명 함수 (anonymous function)

- `함수 표현식`에서는 함수명을 생략하는 것이 일반적이다.
- 이러한 함수를 `익명 함수`라 한다.

```javascript
var foo = function(a, b) {
   return a * b;
}
```

<br>

## Arrow function(=>) 호출

- Arrow function은 `익명 함수`로만 사용할 수 있다.
- 따라서 `=>`을 호출하기 위해서는 `함수 표현식`을 사용한다.

```javascript
// ES5

var foo = function(x) { return x * x };
```

```javascript
// ES6

const foo = x => x * x;
```

