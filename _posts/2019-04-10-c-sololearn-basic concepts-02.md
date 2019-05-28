---
layout: post
title: "(Basic Concepts 02) Hello World"
categories: dev
tags: c
---

###### [SoloLearn](https://www.sololearn.com) C 번역

<br>

### Hello World

<br>

- As when learning any new language, the place to start is with the classic "Hello World" program:
  - 새로운 언어를 배울 때와 마찬가지로, 시작은 "Hello World" 프로그램이다.

```c
#include <stdio.h>

int main() {
  printf("Hello World\n");
  return 0;
}
```

[코드 실행 확인](https://code.sololearn.com/1619/#c)

<br>

- The function used for generating output is defined in `stdio.h`.
  - 출력 생성에 사용되는 함수는 `stdio.h`에 정의되어 있다.
- In order to use the `printf` function, we need to first include the required file, also called a `header file`.
  - `printf` 함수를 사용하기 위해서는, `header file`이라는 필수 파일을 먼저 포함해야 한다.
- The `main()` function is the entry point to a program.
  - `main()` 함수는 프로그램의 입구 (시작점, 진입점)이다.
- Curly brackets {} indicate the beginning and end of a function (also called a code block).
  - 중괄호 {}는 함수의 시작과 끝을 나타낸다.
  - (코드 블록이라고도 한다.)
- The statements inside the brackets determine what the function does when executed.
  - 괄호 내의 명령문(statement)은, 함수가 실행될 때 수행하는 것을 결정한다.

- The `printf` function is used to generate output:
  - `printf` 함수는 출력을 생성하는 데 사용된다.
- The \n `escape sequence` outputs a newline character.
  - \n `escape sequence`는 개행 문자를 출력한다.
- Escape sequences always begin with a backslash \\.
  - escape sequence는 항상 백슬래시 \\로 시작한다.
- The semicolon ; indicates the end of the statement.
  - 세미콜론 ;은 명령문의 끝을 나타낸다.
- Each statement must end with a semicolon.
  - 각 명령문은 세미콜론으로 끝나야 한다.
- `return 0;` statement terminates the `main()` function and returns the value 0 to the calling process.
  - `return 0;` 명령문은 `main()` 함수를 종료하고, 호출 프로세스에 값 0을 반환한다.
- The number 0 generally means that our program has successfully executed.
  - 숫자 0은 일반적으로 프로그램이 성공적으로 실행되었음을 의미한다.
- Any other number indicates that the program has failed.
  - 다른 숫자는 프로그램이 작동하지 않았음을 나타낸다.

------

<br>

### QUIZ

- Fill in the blanks to include the \<stdio.h> header.
  - \<stdio.h> header를 포함시켜라.

```c
#include <stdio.h>
```

<br>

- Fill in the blanks to output "Hi, everyone!" to the screen:
  - 화면에 "Hi, everyone!"을 출력해라.

```c
printf("Hi, everyone!");
```

<br>