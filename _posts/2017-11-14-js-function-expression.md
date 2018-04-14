---
layout: post
title: "함수 표현식 (function expression)"
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

- 함수 표현식에서는 함수명을 생략하는 것이 일반적이다.
- 이러한 함수를 `익명 함수(anonymous function)`라 한다.

```javascript
var foo = function(a, b) {
   return a * b;
}
```

