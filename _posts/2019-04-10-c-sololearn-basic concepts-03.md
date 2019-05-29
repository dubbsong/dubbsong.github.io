---
layout: post
title: "(Basic Concepts 03) 데이터 타입"
categories: dev
tags: c
---

###### [SoloLearn](https://www.sololearn.com) C 번역

<br>

### Data Types

###### 데이터 타입

- C supports the following basic data types:
  - C는 다음과 같은 기본 데이터 타입을 지원한다.

<br>

- `int`: integer, a whole number.
  - 정수
- `float`: floating point, a number with a fractional part.
  - 부동 소수점, 분수
- `double`: double-precision floating point value.
  - 배정밀도 부동 소수점 값
- `char`: single character.
  - 단일 문자

<br>

- The amount of storage required for each of these types varies by platform.
  - 각각의 타입에 필요한 저장 용량은 플랫폼에 따라 다양하다.
- C has a built-in `sizeof` operator that gives the memory requirements for a particular data type.
  - C에는 내장된 `sizeof` 연산자가 있다.
  - 특정 데이터 타입에 대한 메모리 요구 사항을 제공한다.

```c
#include <stdio.h>

int main() {
  printf("int: %d \n", sizeof(int));
  printf("float: %d \n", sizeof(float));
  printf("double: %d \n", sizeof(double));
  printf("char: %d \n", sizeof(char));
  
  return 0;
}

// int: 4
// float: 4
// double: 8
// char: 1
```

[코드 실행 확인](https://code.sololearn.com/1620/#c)

<br>

- The program output displays the corresponding size in bytes for each data type.
  - 프로그램 출력은, 각 데이터 타입에 대한 해당 크기를 bytes(바이트)로 보여준다.
- The `printf` statements in this program have two `arguments`.
  - 위 프로그램의 `printf` 명령문에는 두 개의 `인수`가 있다.
- The first is the output string with a `format specifier` (%d), while the next argument returns the `sizeof` value.
  - 첫 번째 인수는 `서식 서식자`인 출력 문자열이다.
  - 두 번째 인수는 `sizeof` 값을 반환한다.
- In the final output, the `%d` (for decimal) is replaced by the value in the second argument.
  - 최종 출력에서, `%d`는 두 번째 인수의 값으로 대체된다.

<br>

> Note that C does not have a boolean type.
>
> C에는 boolean 타입이 없다.

> A `printf` statement can have multiple format specifiers with corresponding arguments to replace the specifiers.
>
> `printf` 명령문은 여러 서식 지정자를 가질 수 있다.

> Format specifiers are also referred to as conversion specifiers.
>
> 서식 지정자는 변환 지정자라고도 한다.

------

<br>

### Variables

###### 변수

<br>

- A variable is a name for an area in memory.
  - 변수는 메모리에 있는 영역의 이름이다.
- The name of a variable (also called the `identifier`) must begin with either a letter or an underscore and can be composed of letters, digits, and the underscore character.
  - 변수 이름(`식별자`라고도 한다)은 문자나 밑줄로 시작해야 한다.
  - 문자, 숫자, 밑줄로 구성될 수 있다.
- Variable naming conventions differ, however using lowercase letters with an underscore to separate words is common (snake_case).
  - 변수 네이밍 규칙은 차이가 있지만, 단어를 구분해서 밑줄이 있는 소문자를 사용하는 것이 일반적이다. (snake_case)
- Variables must also be declared as a data type before they are used.
  - 변수는 사용하기 전에 데이터 타입으로 선언되어야 한다.

<br>

- The value for a declared variable is changed with an `assignment statement`.
  - 선언된 변수에 대한 값은 `할당 명령문`과 함께 변경된다.
- For example, the following statements declare an integer variable `my_var` and then assigns it the value 42:
  - 예를 들어, 다음 명령문은 정수 변수 `my_var`를 선언한 후, 값 42를 할당한다.

```c
int my_var;
my_var = 42;
```

<br>

- You can also declare and `initialize` (assign an initial value) a variable in a single statement.
  - 단일 명령문에서 변수를 선언하고 `초기화`할 수도 있다.

```c
int my_var = 42;
```

<br>

- Let's define variables of different types, do a simple math operation, and output the results:
  - 다른 타입의 변수를 정의한 다음, 간단한 수학 연산을 하고, 결과를 출력해보자.

```c
#include <stdio.h>

int main() {
  int a, b;
  float salary = 56.23;
  char letter = 'Z';
  a = 8;
  b = 34;
  int c = a+b;
  
  printf("%d \n", c);
  printf("%f \n", salary);
  printf("%c \n", letter);
  
  return 0;
}

// 42
// 56.230000
// Z
```

[코드 실행 확인](https://code.sololearn.com/1621/#c)

<br>

- As you can see, you can declare multiple variables on a single line by separating them with a `comma`.
  - 보다시피, 여러 변수를 `쉼표`로 구분해서 한 줄에 선언할 수 있다.
- Also, notice the use of format specifiers for float (%f) and char (%c) output.
  - float과 char 출력에 대한 서식 지정자 사용에 주의해라.

<br>

> The C programming language is `case-sensitive`, so `my_Variable` and `my_variable` are two different identifiers.
>
> C 프로그래밍 언어는 `대소문자를 구분`하므로, `my_Variable`과 `my_variable`은 다른 식별자이다.

------

<br>

### Constants

###### 상수

<br>

- A `constant` stores a value that cannot be changed from its initial assignment.
  - `상수`는 초기 할당에서 변경할 수 없는 값을 저장한다.
- By using constants with meaningful names, code is easier to read and understand.
  - 의미 있는 이름의 상수를 사용하면, 코드를 읽고 이해하기가 더 쉬워진다.
- To distinguish constants from variables, a common practice is to use uppercase identifiers.
  - 일반적으로 변수에서 상수를 구별하기 위해, 대문자 식별자를 사용한다.

<br>

- One way to define a constant is by using the `const` keyword in a variable declaration:
  - 상수를 정의하는 한 가지 방법은, 변수 선언에서 `const` 키워드를 사용하는 것이다.

```c
#include <stdio.h>

int main() {
  const double PI = 3.14;
  printf("%f", PI);
  
  return 0;
}

// 3.140000
```

[코드 실행 확인](https://code.sololearn.com/1618/#c)

<br>

- The value of PI cannot be changed during program execution.
  - PI 값은 프로그램 실행 중에 변경될 수 없다.
- For example, another assignment statement, such as PI = 3.141 will generate an error.
  - 예를 들어, PI = 3.141과 같은 다른 할당 명령문은 에러를 발생시킨다.

<br>

> Constants must be initialized with a value when declared.
>
> 상수는 선언될 때 값으로 초기화되어야 한다.

<br>

- Another way to define a constant is with the `#define` preprocessor directive.
  - 상수를 정의하는 또 다른 방법은, `#define` 전처리기 지시문을 사용하는 것이다.
- The `#define` directive uses macros for defining constant values.
  - `#define` 지시문은 상수 값을 정의하기 위해 매크로를 사용한다.

```c
#include <stdio.h>

#define PI 3.14

int main() {
  printf("%f", PI);
  return 0;
}

// 3.140000
```

[코드 실행 확인](https://code.sololearn.com/1635/#c)

<br>

- Before compilation, the preprocessor replaces every macro identifier in the code with its corresponding value from the directive.
  - 컴파일 전에, 전처리기는 모든 매크로 식별자를 지시문의 해당 값으로 대체한다.
- In this case, every occurrence of `PI` is replaced with `3.14`.
  - 위 코드의 경우, `PI`가 발생할 때마다 `3.14`로 대체한다.
- The final code sent to the compiler will already have the constant values in place.
  - 컴파일러에 전송된 최종 코드에는 이미 상수 값이 있다.

<br>

- The difference between `const` and `#define` is that the former uses memory for storage and the latter does not.
  - `const`와 `#define`의 차이점은, 전자는 저장하기 위한 메모리를 사용하고, 후자는 사용하지 않는다는 것이다.

<br>

> Do NOT put a semicolon character at the end of `#define` statements.
>
> `#define` 명령문의 끝에 세미콜론을 사용하지 마라.

> This is a common mistake.
>
> 이는 흔한 실수이다.

------

<br>

### QUIZ

- Which of the following are valid data types in C?
  - C에서 유효한 데이터 타입은 무엇인가?

> `int`, `float`, `double`, `char`

<br>

- Fill in the blanks to declare an integer variable num and assign it the value 42.
  - 정수 변수 num을 선언하고, 값 42를 할당해라.

```c
int num;
num = 42;
```

<br>

- Fill in the blanks to declare a constant variable PI of type double.
  - double 타입의 상수 변수 PI를 선언해라.

```c
const double PI = 3.14;
```

<br>