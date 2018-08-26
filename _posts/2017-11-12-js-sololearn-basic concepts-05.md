---
layout: post
title: "05. 비교 연산자 (Basic Concepts)"
categories: dev
tags: js
---

###### [SoloLearn](https://www.sololearn.com) JS 번역

<br>

# JavaScript Comparison Operators

###### JavaScript 비교 연산자

<br>

- Comparison operators are used in logical statements to determine equality or difference between variables or values.
  - 비교 연산자는 변수 또는 값의 동일성 또는 차이를 결정하기 위해 논리 문에서 사용된다.
- They return `true` or `false`.
  - `true` 또는 `false`를 반환한다.

<br>

- The `equal to (==)` operator checks whether the operands' values are equal.
  - `equal to (==)` 연산자는 피연산자의 값이 같은지 여부를 확인한다.

```js
var num = 10;
document.write(num == 8);

// num == 8 will return false
```

[코드 실행 확인 링크](https://code.sololearn.com/656/#js)

<br>

<br>

- The table below explains the comparison operators.
  - 아래 테이블은 비교 연산자를 설명한다.

![sololearn img](/assets/img/sololearn-js-basic concepts-05-01.png)

<br>

> When using operators, be sure that the arguments are of the same data type; numbers should be compared with numbers, strings with strings, and so on.
>
> 연산자를 사용할 때, 인수가 동일한 데이터 타입인지 확인해라.
>
> 숫자는 숫자, 문자열이 있는 문자열 등과 비교되어야 한다.

------

<br>

## QUIZ

- The comparison operators return:
  - 비교 연산자는 다음을 반환한다.

> `true` and `false`

<br>

- Please enter the corresponding operators according to the comments at right.
  - 오른쪽에 있는 주석에 따라, 해당 연산자를 입력해라.

```js
var1 == var2	// are equal
var1 != var 2	// not equal
var1 < var2	// less than
var1 === val2	// are strict equal (identical)
```

<br>