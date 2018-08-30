---
layout: post
title: "06. while loop (Conditionals and Loops)"
categories: javascript
tags: js
---

###### [SoloLearn](https://www.sololearn.com) JS 번역

<br>

# JavaScript while loop

###### JavaScript while 반복문

<br>

- The `while` loop repeats through a block of code, as long as a specified condition is `true`.
  - `while` loop는 지정된 조건이 `true`인 동안, 코드 블록을 반복한다.

<br>

- Syntax:

```js
while (condition) {
   코드 블록
}
```

<br>

> The `condition` can be any conditional statement that returns true or false.
>
> `condition`은 true 또는 false를 반환하는 모든 조건문이 될 수 있다.

<br>

<br>

- Consider the following example.
  - 다음 예제를 살펴보자.

```js
var i = 0;
while (i <= 10) {
   document.write(i + "<br />");
   i++
}
```

[코드 실행 확인 링크](https://code.sololearn.com/671/#js)

<br>

- The loop will continue to run as long as i is less than, or equal to, 10.
  - loop는 i가 10보다 작거나 같은 동안, 계속 실행된다.
- Each time the loop runs, it will increase by 1.
  - loop가 실행될 때마다, 1씩 증가한다.

<br>

- This will output the values from 0 to 10.
  - 이는 0에서 10까지의 값을 출력한다.

![sololearn img](/assets/img/sololearn-js-conditionals and loops-06-01.png)

<br>

> Be careful writing conditions.
>
> 작성 조건을 주의해라.

> If a condition is always true, the loop will run forever.
>
> 조건이 항상 true면, loop가 영원히 실행된다.

<br>

<br>

- If you forget to increase the variable used in the condition, the loop will never end.
  - 조건에 사용된 변수 증가를 잊으면, loop가 끝나지 않는다.

<br>

> Make sure that the condition in a while loop eventually becomes `false`.
>
> while loop의 조건이 결국 `false`가 되는지를 확인해라.

------

<br>

## QUIZ

- The result of the condition statement is always:
  - 조건문의 결과는 항상 다음과 같다.

> `A Boolean value (true or false)`

<br>

- Fill in the blanks to print x's values from 1 to 5.
  - x의 값을 1에서 5까지 출력해라.

```js
var x = 1;
while (x <= 5) {
   document.write(x + "<br />");
   x = x + 1;
}
```

<br>

- How many times will the while loop run, if we remove the counting variable increment statement:
  - 카운팅 변수 증가문을 제거하면, while loop가 몇 번 실행되는가?

> `Infinite`

<br>