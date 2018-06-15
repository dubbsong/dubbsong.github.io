---
layout: post
title: "SoloLearn 번역 - 08. Break and Continue (Conditionals and Loops)"
categories: javascript
tags: JS
---

## Break (break 문)

- The **break** statement "jumps out" of a loop and continues executing the code after the loop.
  - **break** 문은 loop에서 "밖으로 나와" 코드를 계속 실행한다.

```js
for (i = 0; i <= 10; i++) {
   if (i == 5) {
      break;
   }
   document.write(i + "<br />");
}
```

<br>

- Once i reaches 5, it will break out of the loop.
  - i가 5에 도달하면 loop에서 벗어날 것이다.

![SoloLearn img](/assets/img/sololearn-js-conditionals and loops-08-01.png)

------

<br>

## Continue (continue 문)

- The **continue** statement breaks only one iteration in the loop, and continues with the next iteration.
  - **continue** 문은 loop에서 한 번의 반복만 중단하고 다음 반복을 계속한다.

```js
for (i = 0; i <= 10; i++) {
   if (i == 5) {
      continue;
   }
   document.write(i + "<br />");
}
```

<br>

- Result:

![SoloLearn img](/assets/img/sololearn-js-conditionals and loops-08-02.png)

<br>

> The value 5 is not printed, because **continue** skips that iteration of the loop.
>
> **continue**는 loop의 반복을 건너뛰기 때문에 값 5가 출력되지 않는다.

------

<br>

## QUIZ

- The "break" statement:
  - **Ends the execution of the loop**
  - Ignores the current iteration and passes to the next
  - Stops the whole script

<br>

- What is the output of this code?

```js
var sum = 0;

for (i = 4; i < 8; i++) {
   if (i == 6) {
      continue;
   }
   sum += i;
}


document.write(sum);	// 16
```

<br>