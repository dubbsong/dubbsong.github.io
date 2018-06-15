---
layout: post
title: "SoloLearn 번역 - 06. The While Loop (Conditionals and Loops)"
categories: javascript
tags: JS
---

## The While Loop (while 반복문)

- The **while** loop repeats through a block of code, as long as a specified condition is **true**.
  - **while** loop는 지정된 조건이 **true**인 동안에는 코드 블록을 반복한다.

<br>

- Syntax:

```js
while (condition) {
   code block
}
```

<br>

> The **condition** can be any conditional statement that returns true or false.
>
> **condition**은 true 또는 false를 반환하는 모든 조건문이 될 수 있다.

------

<br>

## The While Loop 02

- Consider the following example.
  - 다음 예제를 보자.

```js
var i = 0;

while (i <= 10) {
   document.write(i + "<br />");
   i++;
}
```

<br>

- The loop will continue to run as long as i is less than, or equal to, 10.
  - loop는 i가 10보다 작거나 같은 한 계속 실행된다.
- Each time the loop runs, it will increase by 1.
  - loop가 실행될 때마다 1씩 증가한다.

<br>

- This will output the values from 0 to 10.
  - 0부터 10까지의 값이 출력된다.

![SoloLearn img](/assets/img/sololearn-js-conditionals and loops-06-01.png)

------

<br>

## The While Loop 03

- If you forget to increase the variable used in the condition, the loop will never end.
  - 조건에 사용된 변수 증가를 잊어버리면, loop가 끝나지 않는다.

<br>

> Make sure that the condition in a while loop eventually becomes **false**.
>
> while loop의 조건이 결국 **false**가 되는지 확인해라.

------

<br>

## QUIZ

- The result of the condition statement is always:
  - **A Boolean value (true or false)**
  - A string value
  - A numeric value

<br>

- Fill in the blanks to print x's values from 1 to 5.

```js
var x = 1;

while (x <= 5) {
   document.write(x + "<br />");
   x = x + 1;
}
```

<br>

- How many times will the while loop run, if we remove the counting variable increment statement:
  - 4
  - 1
  - **Infinite**

<br>