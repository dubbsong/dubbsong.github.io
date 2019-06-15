---
layout: post
title: "(Basic Concepts 05) 주석"
categories: dev
tags: c
---

###### [SoloLearn](https://www.sololearn.com/) C 번역

<br>

### Comments

###### 주석

<br>

- Comments are explanatory information that you can include in a program to benefit the reader of your code.
  - 주석은 설명하기 위한 정보이다.
  - 코드를 읽는 사람에게 도움이 되기 위해 프로그램에 포함할 수 있다.
- The compiler ignores comments, so they have no affect on a program.
  - 컴파일러는 주석을 무시한다.
  - 프로그램에 영향을 미치지 않는다.
- A comment starts with a slash asterisk `/*` and ends with an asterisk slash `*/` and can be anywhere in your code.
  - 주석은 슬래시 별표 `/*`로 시작해서, 별표 슬래시 `*/`로 끝난다.
  - 코드 내 어디든 있을 수 있다.
- Comments can be on the same line as a statement, or they can span several lines.
  - 주석은 명령문과 같은 줄에 있거나, 여러 줄로 걸쳐 있을 수 있다.

```c
#include <stdio.h>

/* A simple C program
Version 1.0
*/

int main() {
  /* Output a string */
  printf("Hello World");
  
  return 0;
}
```

[코드 실행 확인](https://code.sololearn.com/1616/#c)

------

<br>

### Single-line Comments

###### 한 줄 주석

<br>

- C++ introduced a double slash comment `//` as a way to comment single lines.
  - C++에서는 한 줄 주석을 처리하는 방법으로 이중 슬래시 주석 `//`을 도입했다.
- Some C compilers also support this comment style.
  - 일부 C 컴파일러도 이중 슬래시 주석 스타일을 지원한다.

```c
#include <stdio.h>

int main() {
  int x = 42;	// int for a whole number
  
  // %d is replaced by x
  printf("%d", x);
  
  return 0;
}
```

[코드 실행 확인](https://code.sololearn.com/1617/#c)

<br>

> Adding comments to your code is good programming practice.
>
> 코드에 주석을 추가하는 것은 좋은 프로그래밍 습관이다.

------

<br>

### QUIZ

- Fill in the blanks to create a multi-line comment.
  - 여러 줄 주석을 생성해라.

```c
/* This is a 
comment that spans
multiple lines
*/
```

<br>

- Fill in the blank to create a single-line comment:
  - 한 줄 주석을 생성해라.

```c
// This is a single line comment
```

<br>