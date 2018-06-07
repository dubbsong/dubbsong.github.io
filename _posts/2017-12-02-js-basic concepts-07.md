---
layout: post
title: "SoloLearn 번역 - 07. String Operators (Basic Concepts)"
categories: javascript
tags: JS
---

## String Operators (문자열 연산자)

- The most useful operator for strings is *concatenation*, represented by the + sign.
  - 문자열에 가장 유용한 연산자는 + 기호로 표시되는 *연결*이다.
- Concatenation can be used to build strings by joining together multiple strings, or by joining strings with other types:
  - 여러 문자열을 결합하거나, 다른 타입과 합쳐서 문자열을 구성하는 데 연결을 사용할 수 있다.

```js
var mystring1 = "I am learning";
var mystring2 = "JavaScript with SoloLearn.";
document.write(mystring1 + mystring2);
```

<br>

- The above example declares and initializes two string variables, and then concatenates them.
  - 위의 예제에서는 두 개의 문자열 변수를 선언하고 초기화 한 다음, 연결한다.

![SoloLearn](/assets/img/sololearn-js-basic concepts-07-01.png)

<br>

> Numbers in quotes are treated as strings: "42" is not the number 42, it is a string that includes two characters, 4 and 2.
>
> 따옴표로 묶인 숫자는 문자열로 처리된다: "42"는 숫자 42가 아니고, 두 문자 4와 2가 포함된 문자열이다.

------

<br>

## QUIZ

- What is the output of the following code:
  - Null
  - 150
  - **50100**
  - 5000

```js
var x = "50";
var y = "100";
document.write(x + y);
```

<br>