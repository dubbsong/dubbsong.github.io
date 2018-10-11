---
layout: post
title: "(Core Objects 03) 배열의 속성 & 메소드"
categories: js
---

###### [SoloLearn](https://www.sololearn.com/) JS 번역

<br>

# JavaScript Array Properties & Methods

###### 배열의 속성 & 메소드

------

<br>

<br>

## The length Property

###### length 속성

<br>

- JavaScript arrays have useful `built-in` properties and methods.
  - JavaScript 배열에는 `내장된` 유용한 속성과 메소드가 있다.

<br>

- An array's `length` property returns the number of it's elements.
  - 배열의 `length` 속성은 element의 수를 반환한다.

```js
var courses = ["HTML", "CSS", "JS"];
document.write(courses.length);	// Outputs 3
```

[코드 실행 확인](https://code.sololearn.com/698/#js)

<br>

> The `length` property is always one more than the highest array index.
>
> `length` 속성은 항상 가장 높은 배열 index보다 하나 더 크다.

> If the array is empty, the length property returns `0`.
>
> 배열이 비어있는 경우, length 속성은 `0`을 반환한다.

------

<br>

## Combining Arrays

###### 배열 결합

<br>

- JavaScript's `concat()` method allows you to join arrays and create an entirely new array.
  - JavaScript의 `concat()` 메소드를 사용하면 배열을 결합하거나, 완전히 새로운 배열을 생성할 수 있다.

<br>

- For example:

```js
var c1 = ["HTML", "CSS"];
var c2 = ["JS", "C++"];
var courses = c1.concat(c2);
```

[코드 실행 확인](https://code.sololearn.com/699/#js)

<br>

- The `courses` array that results contains 4 elements (HTML, CSS, JS, C++).
  - 결과에 해당하는 `courses` 배열에는 4가지 element(HTML, CSS, JS, C++)가 포함된다.

<br>

> The `concat` operation does not affect the *c1* and *c2* arrays - it returns the resulting concatenation as a new array.
>
> `concat` 연산은 *c1*과 *c2* 배열에 영향을 미치지 않는다.
>
> 연결의 결과로 초래된 배열을 새로운 배열로 반환한다.

------

<br>

## QUIZ

- Array has the "length" property, because it is:
  - 배열은 …이기 때문에 "length" 속성이 있다.

> `an object`

<br>

- The "concat" method takes two arrays and:
  - "concat" 메소드는 두 개의 배열을 사용해서,

> `combines them in one new array`
>
> 하나의 새로운 배열로 결합한다.

<br>