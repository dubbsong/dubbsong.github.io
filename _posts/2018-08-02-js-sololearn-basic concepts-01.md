---
layout: post
title: "(Basic Concepts 01) 변수"
categories: js
---

###### [SoloLearn](https://www.sololearn.com/) JS 번역

<br>

## Variables

###### 변수

<br>

- `Variables` are containers for storing data values.
  - `변수`는 데이터 값을 저장하는 컨테이너이다.
- The value of a variable can change throughout the program.
  - 변수 값은 프로그램 전역에서 변경할 수 있다.
- Use the `var` keyword to declare a variable:
  - `var` 키워드를 사용해서 변수를 선언한다.

```js
var x = 10;
```

<br>

- In the example above, the value `10` is assigned to the variable `x`.
  - 위 예제에서, 값 `10`은 변수 `x`에 할당된다.

<br>

> JavaScript is case sensitive.
>
> JS는 대소문자를 구분한다.

> For example, the variables *lastName* and *lastname*, are two different variables.
>
> *lastName*과 *lastname*은 두 개의 다른 변수이다.

------

<br>

### The Equal Sign

###### 등호

<br>

- In JavaScript, the equal sign (=) is called the `"assignment"` operator, rather than an "equal to" operator.
  - JS에서 등호 (=)는 `"할당"` 연산자라고 한다.
- For example, `x = y` will assign the value of `y` to `x`.
  - 예를 들어, `x = y`는 `y`의 값을 `x`에 할당한다.

<br>

> A variable can be declared without a value.
>
> 변수는 값 없이 선언될 수 있다.

> The value might require some calculation, something that will be provided later, like user input.
>
> 이 값은 계산을 필요로 한다.
>
> 사용자 input과 같이, 나중에 제공된다.

> A variable declared without a value will have the value `undefined`.
>
> 값 없이 선언된 변수는, `undefined` 값을 가진다.

------

<br>

### Using Variables

###### 변수 사용하기

<br>

- Let's assign a value to a variable and output it to the browser.
  - 변수에 값을 할당하고, 브라우저에 출력해보자.

```js
var x = 100;
document.write(x);
```

[코드 실행 확인](https://code.sololearn.com/647/#js)

<br>

- Using variables is useful in many ways.
  - 변수를 사용하는 것은 여러모로 유용하다.
- You might have a thousand lines of code that may include the variable x.
  - 변수 x를 포함하는 1000 줄의 코드가 있을 수 있다.
- When you change the value of x `one time`, it will automatically be changed in `all places` where you used it.
  - x 값을 `한 번` 변경하면, 이를 사용했던 `모든 위치`에서 자동으로 변경된다.

<br>

> Every written "instruction" is called a `statement`.
>
> 작성된 모든 "명령"을 `statement(문)`라고 한다.

> JavaScript statements are separated by `semicolons`.
>
> JS 문은 `세미콜론`으로 구분된다.

------

<br>

### Naming Variables

###### 변수 네이밍

<br>

- JavaScript variable names are case-sensitive.
  - JS 변수 이름은 대소문자를 구분한다.
- In the example below we changed x to uppercase:
  - 아래 예제에서 x를 대문자로 변경했다.

```js
var x = 100;
document.write(X);
```

[코드 실행 확인](https://code.sololearn.com/648/#js)

<br>

- This code will not result in any output, as x and X are two different variables.
  - x와 X는 다른 변수이므로, 위 코드는 어떤 출력도 하지 않는다.

<br>

#### Naming rules:

###### 네이밍 규칙:

<br>

- The first character `must be` a letter, an underscore (_), or a dollar sign ($).
  - 첫 번째 글자는 문자, 밑줄 또는 달러 기호여야 한다.
- Numbers are `not allowed` as the first character.
  - 숫자는 첫 번째 글자로 사용할 수 없다.
- Variable names `cannot` include a `mathematical` or `logical operator` in the name.
  - 변수 이름은 `수학적` 또는 `논리 연산자`를 포함할 수 없다.
- JavaScript names `must not contain spaces`.
  - 공백이 없어야 한다.

<br>

> Hyphens are not allowed in JavaScript.
>
> JS에서 하이픈 (-)을 사용할 수 없다.

> It is reserved for subtractions.
>
> 하이픈은 뺄셈을 위해 예약되어 있다.

<br>

<br>

- There are some other rules to follow when naming your JavaScript variables:
  - JS 변수의 이름을 지정할 때 따라야 할 몇 가지 규칙이 있다.

<br>

- You `must not` use any `special symbols`, like *my#num*, *num%*, etc.
  - *my#num*, *num%* 등과 같은 `특수 기호`를 사용하면 안 된다.
- Be sure that you do not use any of the following JavaScript reserved words.
  - 다음 JS 예약어를 사용하지 않는다.

![img](/assets/img/js-sololearn-basic%20concepts-01-01.png)

------

<br>

## QUIZ

- Which keyword is used to tell JavaScript that we're going to work with a variable?
  - JS에게 변수를 사용한다는 것을 알리는 키워드는 무엇인가?

> `var`

<br>

- What is the "=" called in JavaScript?
  - JS에서 "="는 무엇인가?

> `Assignment operator (할당 연산자)`

<br>

- Use the corresponding keyword to complete the statement.
  - 해당 키워드를 사용해서 statement(문)를 완성해라.

```js
var my_variable = 32;
```

<br>

- What characters can be used to start a variable?
  - 변수를 시작하는 데 사용할 수 있는 글자는 무엇인가?
- Select all that apply.
  - 해당되는 모든 것을 선택해라.

> [ ] Numbers
>
> [ ] Mathematical operators
>
> [ ] `Letters`
>
> [ ] `Underscore sign`

<br>

- What characters cannot be used in variable names?
  - 변수 이름에 사용할 수 없는 글자는 무엇인가?

> `special symbols` (%, \#, etc.)

<br>