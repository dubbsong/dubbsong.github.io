---
layout: post
title: "05. for loop (Conditionals and Loops)"
categories: javascript
tags: js
---

###### [SoloLearn](https://www.sololearn.com) JS 번역

<br>

# JavaScript for loop

###### JavaScript for 반복문

------

<br>

<br>

## Loops

###### 반복문

<br>

- Loops can execute a block of code a number of times.
  - loop는 여러 번 코드 블록을 실행할 수 있다.
- They are handy in cases in which you want to run the same code repeatedly, adding a different value each time.
  - 매번 다른 값을 추가해서, 동일한 코드를 반복적으로 실행하려는 경우에 편리하다.

<br>

- JavaScript has three types of loops: `for`, `while`, and `do while`.
  - JavaScript에는 `for`, `while`, `do while` 세 가지 타입의 loop가 있다.

<br>

- The `for` loop is commonly used when creating a loop.
  - `for` loop는 일반적으로 loop를 만들 때 사용된다.

<br>

- The syntax:

```js
for (statement 1; statement 2; statement 3) {
   실행될 코드 블록
}
```

<br>

- `statement 1` is executed before the loop (the code block) starts.
  - `statement 1`은 loop(코드 블록)가 시작되기 전에 실행된다.
- `statement 2` defines the condition for running the loop (the code block).
  - `statement 2`는 loop(코드 블록)를 실행하기 위한 조건을 정의한다.
- `statement 3` is executed each time after the loop (the code block) has been executed.
  - `statement 3`는 loop(코드 블록)가 실행된 후에 매번 실행된다.

<br>

> As you can see, the `classic for loop` has `three` components, or statements.
>
> 보다시피, `classic for loop`에는 `세 가지` 컴포넌트 또는 `세 가지` 명령문이 있다.

------

<br>

## The For Loop

###### for loop

<br>

- The example below creates a `for` loop that prints numbers 1 through 5.
  - 아래 예제는, 1에서 5까지의 숫자를 출력하는 `for` loop를 생성한다.

```js
for (i = 1; i <= 5; i++) {
   document.write(i + "<br />");
}
```

<br>

- In this example, `statement 1` sets a variable before the loop starts (var i = 1).
  - 이 예제에서, `statement 1`은 loop가 시작되기 전에 변수를 설정한다.
  - (var i = 1)
- `statement 2` defines the condition for the loop to run (i must be less than or equal to 5).
  - `statement 2`는 loop 실행 조건을 정의한다.
  - (i는 5보다 작거나 같아야 한다)
- `statement 3` increases a value (i++) each time the code block in the loop has been executed.
  - `statement 3`은 loop의 코드 블록이 실행될 때마다 값(i++)을 증가시킨다.

<br>

- Result:

![sololearn img](/assets/img/sololearn-js-conditionals and loops-05-01.png)

<br>

- `statement 1` is optional, and can be omitted, if your values are set before the loop starts.
  - `statement 1`은 선택적이며, loop가 시작되기 전에 값이 설정되면 생략할 수 있다.

```js
var i = 1;
for (;i <= 5; i++) {
   document.write(i + "<br />");
}
```

[코드 실행 확인 링크](https://code.sololearn.com/668/#js)

<br>

- Also, you can initiate more than one value in `statement 1`, using `commas` to separate them.
  - `statement 1`에서 둘 이상의 값을 `쉼표`로 구분해서 시작할 수도 있다.

```js
for (i = 1, text = ""; i <= 5; i++) {
   text = i;
   document.write(i + "<br />");
}
```

[코드 실행 확인 링크](https://code.sololearn.com/669/#js)

<br>

> ES6 introduces other for loop types; you can learn about them in the ES6 course later.
>
> ES6에서는 다른 for loop 타입을 소개한다.
>
> 나중에 ES6 코스에서 학습할 수 있다.

<br>

<br>

- If `statement 2` returns true, the loop will start over again, if it returns false, the loop will end.
  - `statement 2`가 true를 반환하면 loop가 다시 시작되고, false를 반환하면 loop가 종료된다.
- statement 2 is also optional.
  - statement 2도 선택 사항이다.

<br>

> If you omit statement 2, you must provide a `break` inside the loop.
>
> statement 2를 생략하면, loop 내에서 `break`를 제공해야 한다.

> Otherwise, the loop will never end.
>
> 그렇지 않으면, loop가 끝나지 않는다.

<br>

- `statement 3` is used to change the initial variable.
  - `statement 3`는 초기 변수를 변경하는 데 사용된다.
- It can do anything, including negative increment (i--), positive increment (i = i + 15), or anything else.
  - 음수 증가(i--), 양수 증가(i = i + 15) 또는 그 외의 것을 포함해서 모든 작업을 수행할 수 있다.
- statement 3 is also optional, and it can be omitted if you increment your values inside the loop.
  - statement 3은 선택적이며, loop 내에서 값을 증가시키면 생략할 수 있다.

```js
var i = 0;
for (;i < 10;) {
   document.write(i);
   i++
}
```

[코드 실행 확인 링크](https://code.sololearn.com/670/#js)

<br>

> You can have multiple nested for loops.
>
> 여러 중첩된 for loop를 가질 수 있다.

------

<br>

## QUIZ

- The classic "for" loop consists of how many components?
  - classic "for" loop는 몇 개의 컴포넌트로 구성되는가?

> `3`

<br>

- Fill in the blanks to compose a valid for loop:
  - 유효한 for loop를 작성해라.

```js
var i = 1;
for (k = 1; k < 10; k++) {
   i += k;
}
```

<br>

- Fill in the blanks to print EVEN values from 0 to 20 using a for loop:
  - for loop를 사용해서 짝수(even) 값을 0에서 20까지 출력해라.

```js
var x = 0;
for (;x <= 20; x += 2) {
   document.write(x);
}
```

<br>