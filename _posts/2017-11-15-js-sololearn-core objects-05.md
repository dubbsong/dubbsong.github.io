---
layout: post
title: "(Core Objects 05) Math 객체"
categories: js
---

###### [SoloLearn](https://www.sololearn.com/) JS 번역

<br>

# JavaScript Math Object

###### Math 객체

<br>

- The `Math object` allows you to perform mathematical tasks, and includes several properties.
  - `Math 객체`를 사용하면 수학적 작업을 수행할 수 있으며, 여러 가지 속성이 포함된다.

![img](/assets/img/js-sololearn-core objects-05-01.png)

<br>

- For example:

```js
document.write(Math.PI);	// Outputs 3.141592653589793
```

[코드 실행 확인](https://code.sololearn.com/701/#js)

<br>

> Math has no constructor.
>
> Math에는 생성자가 없다.

> There's no need to create a Math object first.
>
> 먼저 Math 객체를 생성할 필요가 없다.

------

<br>

## Math Object Methods

###### Math 객체 메소드

<br>

- The `Math object` contains a number of methods that are used for calculations:
  - `Math 객체`는 계산에 사용되는 여러 가지 메소드를 포함한다.

![img](/assets/img/js-sololearn-core objects-05-02.png)

<br>

- For example, the following will calculate the `square root` of a number.
  - 예를 들어, 다음은 숫자의 `제곱근`을 계산한다.

```js
var number = Math.sqrt(4);
document.write(number);	// Outputs 2
```

[코드 실행 확인](https://code.sololearn.com/702/#js)

<br>

> To get a random number between 1-10, use Math.random(), which gives you a number between 0-1.
>
> 1-10 사이의 임의의 숫자를 얻으려면, Math.random()을 사용해라.
>
> 이는 0-1 사이의 숫자가 주어진다.

> Then multiply the number by 10, and then take Math.ceil() from it: Math.ceil(Math.random() * 10).
>
> 그런 다음, 숫자에 10을 곱하고, Math.ceil()을 Math.ceil(Math.random() * 10)으로 가져온다.

------

<br>

## The Math Object

###### Math 객체

<br>

- Let's create a program that will ask the user to input a number and alert its square root.
  - 사용자에게 숫자를 입력하고, 제곱근을 alert 하도록 요청하는 프로그램을 생성해보자.

```js
var n = prompt("Enter a number", "");
var answer = Math.sqrt(n);
alert("The square root of " + n + " is " + answer);
```

[코드 실행 확인](https://code.sololearn.com/703/#js)

<br>

- Result:

![img](/assets/img/js-sololearn-core objects-05-03.png)

<br>

- Enter a number, such as 64.
  - 64와 같은 숫자를 입력해라.

![img](/assets/img/js-sololearn-core objects-05-04.png)

<br>

> Math is a handy object.
>
> Math는 편리한 객체이다.

> You can save a lot of time using Math, instead of writing your own functions every time.
>
> 매번 자신만의 함수를 작성하는 대신, Math를 사용해서 많은 시간을 절약할 수 있다.

------

<br>

## QUIZ

- In the Math Object, which of the following constants does NOT exist?
  - Math 객체에서, 다음 상수 중 어느 것이 존재하지 않는가?

> [ ] Math.E
>
> [ ] Math.PI
>
> [ ] `Math.ABC`

<br>

- In the Math Object, which of the following methods is used to calculate the square root?
  - Math 객체에서, 다음 중 어느 메소드가 제곱근을 계산하는 데 사용되는가?

> [ ] ceil
>
> [ ] round
>
> [ ] root
>
> [ ] `sqrt`

<br>

- What is the result of the following expression:
  - 다음 표현식의 결과는 무엇인가?

```js
Math.sqrt(81);
```

> `9`

<br>