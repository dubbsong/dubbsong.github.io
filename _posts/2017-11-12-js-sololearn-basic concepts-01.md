---
layout: post
title: "01. 변수 (Basic Concepts)"
categories: dev
tags: js
---

###### [SoloLearn](https://www.sololearn.com) JS 번역

<br>

# JavaScript Variables

###### JavaScript 변수

<br>

- `Variables` are containers for storing data values.
  - `변수`는 데이터 값을 저장하기 위한 컨테이너이다.
  - `variable`: Defined using the var keyword, variables are used to store data values (var 키워드를 사용해서 정의된 변수는 데이터 값을 저장하는 데 사용된다)
- The value of a variable can change throughout the program.
  - 변수 값은 프로그램 전체에서 변경될 수 있다.

- Use the `var` keyword to declare a variable:
  - 변수를 선언하기 위해 `var` 키워드를 사용해라.

```js
var x = 10;
```

<br>

- In the example above, the value `10` is assigned to the variable `x`.
  - 위의 예제에서, 값 `10`은 변수 `x`에 할당된다.

<br>

> JavaScript is case sensitive.
>
> JavaScript는 대소문자를 구분한다.

> For example, the variables *lastName* and *lastname*, are two different variables.
>
> 예를 들어, *lastName*과 *lastname* 변수는 다른 변수이다.

------

<br>

## The Equal Sign

###### 등호 (=)

<br>

- In JavaScript, the equal sign (=) is called the `"assignment"` operator, rather than an "equal to" operator.
  - JavaScript에서 등호(=)는 "동일" 연산자가 아니라, `"할당"` 연산자라고 한다.
- For example, `x = y` will assign the value of `y` to `x`.
  - 예를 들어, `x = y`는 `y`의 값을 `x`에 할당한다.

<br>

> A variable can be declared without a value.
>
> 변수는 값 없이 선언될 수 있다.

> The value might require some calculation, something that will be provided later, like user input.
>
> 값에는 계산이 필요하며, 사용자 input과 같이 나중에 제공된다.

> A variable declared without a value will have the value `undefined`.
>
> 값 없이 선언된 변수는 `undefined` 값을 가진다.
>
> `undefined`: A predefined global variable that is the value of a variable or object that has not been initialized, or of a function that returns no value (초기화되지 않은 변수나 객체의 값인 미리 정의된 전역 변수, 값을 반환하지 않는 함수의 미리 정의된 전역 변수)

------

<br>

## Using Variables

###### 변수 사용하기

<br>

- Let's assign a value to a variable and output it to the browser.
  - 변수에 값을 할당하고, 브라우저에 출력해보자.

```js
var x = 100;
document.write(x);
```

<br>

- Result:

![sololearn img](/assets/img/sololearn-js-basic concepts-01-01.png)

<br>

- Using variables in useful in many ways.
  - 변수를 사용하는 것은 여러 면에서 유용하다.
- You might have a thousand lines of code that may include the variable x.
  - 변수 x를 포함할 수 있는 1000 줄의 코드가 있을 수 있다.
- When you change the value of x `one time`, it will automatically be changed in `all places` where you used it.
  - x 값을 `한 번` 변경하면, 사용했던 `모든 장소`에서 x 값이 자동으로 변경된다.

<br>

> Every written "instruction" is called a `statement`.
>
> 모든 "명령(지시)"은 `명령문(statement)`이라고 한다.

> JavaScript statements are separated by `semicolons`.
>
> JavaScript 문은 `세미콜론`으로 구분된다.

------

<br>

## Naming Variables

###### 변수 네이밍하기

<br>

- JavaScript variable names are case-sensitive.
  - JavaScript 변수 이름은 대소문자를 구분한다.
- In the example below we changed x to uppercase:
  - 아래 예제에서, x를 대문자로 변경해보자.

```js
var x = 100;
document.write(X);
```

<br>

- This code will not result in any output, as x and X are two different variables.
  - x와 X는 서로 다른 변수이므로, 위의 코드는 어떤 출력도 하지 않는다.

<br>

#### Naming rulse:

###### 네이밍 규칙:

<br>

> The first character `must be` a letter, an underscore (_), or a dollar sign ($).
>
> 첫 번째 문자는 문자, 밑줄(_), 달러 기호($) 여야 한다.
>
> Subsequent characters may be letters, digits, underscores, or dollar signs.
>
> 그다음 문자는 문자, 숫자, 밑줄, 달러 기호일 수 있다.

> Numbers are `not allowed` as the first character.
>
> 숫자는 첫 번째 문자로 사용할 수 없다.

> Variable names `cannot` include a `mathematical or logical operator` in the name.
>
> 변수 이름은 이름에 `수학적 또는 논리적 연산자`를 포함할 수 없다.
>
> For instance, *2\*something* or *this+that*;
>
> 예를 들어, *2\*something* 또는 *this+that*;

> JavaScript names `must not contain spaces`.
>
> JavaScript 이름에는 공백이 포함될 수 없다.

<br>

<br>

- There are some other rules to follow when naming your JavaScript variables:
  - JavaScript 변수를 네이밍 할 때, 따라야 할 몇 가지 규칙이 있다.

<br>

- You `must not` use any `special symbols`, like *my#num*, *num%*, etc.
  - *my#num*, *num%* 등과 같이 `특수 기호`를 사용하면 안 된다.
- Be sure that you do not use any of the following JavaScript reserved words.
  - 다음 JavaScript 예약어를 사용하지 마라.

![sololearn img](/assets/img/sololearn-js-basic concepts-01-02.png)

<br>

> When you get more familiar with JavaScript, remembering these keywords will be much easier.
>
> JavaScript에 익숙해지면, 이러한 키워드를 기억하는 것이 훨씬 쉬울 것이다.

------

<br>

## QUIZ

- Which keyword is used to tell JavaScript that we're going to work with a variable?
  - 변수로 작업할 것이라는 것을 JavaScript에게 알리는 데 사용되는 키워드는 무엇인가?

> `var`

<br>

- What is the "=" (equal sign) called in JavaScript?
  - JavaScript에서 호출되는 "=" (등호)는 무엇인가?

> `Assignment operator`

<br>

- Use the corresponding keyword to complete the statement.
  - 해당 키워드를 사용해서 명령문을 완성해라.

```js
var my_variable = 32;
```

<br>

- What characters can be used to start a variable?
  - 변수를 시작하는 데 사용할 수 있는 문자는 무엇인가?
  - 모두 골라라.

> [ ] `Underscore sign (_)`
>
> [ ] Mathematical operator
>
> [ ] `Letters`
>
> [ ] Numbers

<br>

- What characters cannot be used in variable names?
  - 변수 이름에는 어떤 문자를 사용할 수 없나?

> `Special symbols (%, #, etc.)`

<br>
