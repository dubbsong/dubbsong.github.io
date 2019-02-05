---
layout: post
title: "(Core Object 05) Math 객체"
categories: js
---

###### [SoloLearn](https://www.sololearn.com/) JS 번역

<br>

## The Math Object

###### Math 객체

<br>

- The `Math object` allows you to perform mathematical tasks, and includes several properties.
  - `Math 객체`를 사용해서 수학적 작업을 수행할 수 있고, 여러 속성도 포함한다.

![img](/assets/img/js-sololearn-core objects-01-01.png)

<br>

- For example:

```js
document.write(Math.PI);	// 3.141592653589793
```

[코드 실행 확인](https://code.sololearn.com/701/#js)

<br>

> Math has no constructor.
>
> Math에는 생성자가 없다.

> There's no need to create a Math object first.
>
> Math 객체를 먼저 생성할 필요가 없다.

<br>

## Math Object Methods

###### Math 객체 메소드

<br>

- The Math object contains a number of methods that are used for calculations:
  - Math 객체에는 계산에 사용되는 여러 메소드가 포함되어 있다.

![img](/assets/img/js-sololearn-core objects-01-02.png)

<br>

- For example, the following will calculate the `square root` of a number.
  - 예를 들어, 다음은 숫자의 `제곱근`을 계산한다.

```js
var number = Math.sqrt(4);
document.write(number);	// 2
```

[코드 실행 확인](https://code.sololearn.com/702/#js)

<br>

> To get a random number between 1-10, use Math.random(), which gives you a number between 0-1.
>
> 1-10 사이의 난수를 얻으려면, Math.random()을 사용한다.

> Then multiply the number by 10, and then take Math.ceil() from it: Math.ceil(Math.random() * 10).
>
> Math.random()에 숫자 10을 곱하고, Math.ceil()로 가져온다.
>
> 예: Math.ceil(Math.random() * 10)

------

<br>

## The Math Object

###### Math 객체

<br>

- Let's create a program that will ask the user to input a number and alert its square root.
  - 사용자에게 숫자를 입력하게 하고, 제곱근을 alert 하는 프로그램을 생성해보자.

```js
var n = prompt("Enter a number", "");
var answer = Math.sqrt(n);
alert("The square root of " + n + " is " + answer);
```

[코드 실행 확인](https://code.sololearn.com/703/#js)

<br>

- Result:

![img](/assets/img/js-sololearn-core objects-01-03.png)

<br>

- Enter a number, such as 64.
  - 64를 입력한다.

![img](/assets/img/js-sololearn-core objects-01-04.png)

<br>

> Math is a handy object.
>
> Math는 유용한 객체이다.

> You can save a lot of time using Math, instead of writing your own functions every time.
>
> 매번 자신만의 함수를 작성하는 대신, Math를 사용해서 많은 시간을 절약할 수 있다.

------

<br>

## QUIZ

- In the Math Object, which of the following constants does NOT exist?
  - 다음 상수 중 Math 객체에 존재하지 않는 것은 무엇인가?

> [ ] Math.PI
>
> [ ] Math.E
>
> [ ] `Math.ABC`

<br>

- In the Math Object, which of the following methods is used to calculate the square root?
  - 다음 메소드 중 Math 객체에서 제곱근을 계산하는 데 사용되는 메소드는 무엇인가?

> [ ] round
>
> [ ] ceil
>
> [ ] `sqrt`
>
> [ ] root

<br>

- What is the result of the following expression:
  - 다음 표현식의 결과는 무엇인가?

```js
Math.sqrt(81);
```

> `9`

<br>