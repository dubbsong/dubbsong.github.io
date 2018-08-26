---
layout: post
title: "07. 문자열 연산자 (Basic Concepts)"
categories: javascript
tags: js
---

###### [SoloLearn](https://www.sololearn.com) JS 번역

<br>

# JavaScript String Operators

###### JavaScript 문자열 연산자

<br>

- The most useful operator for strings is *concatenation*, represented by the + sign.
  - 문자열에 가장 유용한 연산자는 + 기호로 표시되는 *concatenation*이다.
- Concatenation can be used to build strings by joining together multiple strings, or by joining strings with other types:
  - 여러 문자열을 결합하거나, 여러 다른 타입과 결합해서 문자열을 구성하는 데 concatenation을 사용할 수 있다.

```js
var mystring1 = "I am learning";
var mystring2 = "JavaScript with SoloLearn.";
document.write(mystring1 + mystring2);
```

[코드 실행 확인 링크](https://code.sololearn.com/659/#js)

<br>

- The above example declares and initializes two string variables, and then concatenates them.
  - 위의 예제에서는, 두 문자열 변수를 선언하고 초기화한 다음 연결한다.

![sololearn img](/assets/img/sololearn-js-basic concepts-07-01.png)

<br>

> Numbers in quotes are treated as strings: "42" is not the number 42, it is a string that includes two characters, 4 and 2.
>
> 따옴표로 묶인 숫자는 문자열로 처리된다.
>
> "42"는 숫자 42가 아니며, 두 문자 4와 2가 포함된 문자열이다.

------

<br>

## QUIZ

- What is the output of the following code:
  - 다음 코드의 결과는 무엇인가?

```js
var x = "50";
var y = "100";
document.write(x + y);
```

> `50100`

<br>