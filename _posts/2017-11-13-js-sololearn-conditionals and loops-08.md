---
layout: post
title: "08. break 문 & continue 문 (Conditionals and Loops)"
categories: javascript
tags: js
---

###### [SoloLearn](https://www.sololearn.com) JS 번역

<br>

# JavaScript break and continue

###### JavaScript break 문 & continue 문

------

<br>

<br>

## Break

###### break 문

<br>

- The `break` statement "jumps out" of a loop and continues executing the code after the loop.
  - `break` 문은 loop에서 "튀어 나와", loop 다음 코드를 계속 실행한다.

```js
for (i = 0; i <= 10; i++) {
   if (i == 5) {
      break;
   }
   document.write(i + "<br />");
}
```

[코드 실행 확인 링크](https://code.sololearn.com/673/#js)

<br>

- Once i reaches 5, it will break out of the loop.
  - i가 5에 도달하면, loop에서 빠져나온다.

![sololearn img](/assets/img/sololearn-js-conditionals and loops-08-01.png)

<br>

> You can use the return keyword to return some value immediately from the loop inside of a function.
>
> return 키워드를 사용해서, 함수 내 loop에서 즉시 값을 반환할 수 있다.

> This will also break the loop.
>
> 이는 loop도 빠져나온다.

------

<br>

## Continue

###### continue 문

<br>

- The `continue` statement breaks only one iteration in the loop, and continues with the next iteration.
  - `continue` 문은 loop에서 하나의 반복만 중단하고, 다음 반복을 계속한다.

```js
for (i = 0; i <= 10; i++) {
   if (i == 5) {
      continue;
   }
   document.write(i + "<br />");
}
```

[코드 실행 확인 링크](https://code.sololearn.com/674/#js)

<br>

- Result:

![sololearn img](/assets/img/sololearn-js-conditionals and loops-08-02.png)

<br>

> The value 5 is not printed, because `continue` skips that iteration of the loop.
>
> `continue`는 loop의 반복을 건너뛰기 때문에, 값 5는 출력되지 않는다.

------

<br>

## QUIZ

- The "break" statement:
  - "break" 문은:

> `Ends the execution of the loop`
>
> loop의 실행을 종료한다

<br>

- What is the output of this code?
  - 이 코드의 출력은 무엇인가?

```js
var sum = 0;
for (i = 4; i < 8; i++) {
   if (i == 6) {
      continue;
   }
   sum += i;
}
document.write(sum);
```

> `16`

<br>