---
layout: post
title: "(Basic Concepts 04) 입력과 출력"
categories: dev
tags: c
---

###### [SoloLearn](https://www.sololearn.com/) C 번역

<br>

### Input

###### 입력

<br>

- C supports a number of ways for taking user input.
  - C는 사용자 입력을 받기 위한 여러 가지 방법을 지원한다.
- `getchar()` returns the value of the next single character input.
  - `getchar()`는 다음 단일 문자 입력의 값을 반환한다.

```c
#include <stdio.h>

int main() {
  char a = getchar();
  printf("You entered: %c", a);
  
  return 0;
}

// You entered: (직접 입력한 문자 중 한 글자만 출력된다)
```

[코드 실행 확인](https://code.sololearn.com/1622/#c)

<br>

- The input is stored in the variable `a`.
  - 입력은 변수 `a`에 저장된다.

<br>

- The `gets()` function is used to read input as ordered sequence of characters, also called a `string`.
  - `gets()` 함수는 입력을 정렬된 문자 시퀀스로 읽는 데 사용된다.
  - `문자열`이라고도 한다.
- A string is stored in a char array.
  - 문자열은 char 배열에 저장된다.

```c
#include <stdio.h>

int main() {
  char a[100];
  gets(a);
  printf("You entered: %s", a);
  
  return 0;
}

// You entered: (직접 입력한 문자열이 출력된다)
```

[코드 실행 확인](https://code.sololearn.com/1623/#c)

<br>

- Here we stored the input in an array of 100 characters.
  - 위 코드에서 100자의 배열에 입력을 저장했다.

<br>

- `scanf()` scans input that matches format specifiers.
  - `scanf()`는 서식 지정자와 일치하는 입력을 스캔한다.

```c
#include <stdio.h>

int main() {
  int a;
  scanf("%d", &a);
  printf("You entered: %d", a);
  
  return 0;
}

// You entered: (직접 입력한 숫자가 출력된다)
```

[코드 실행 확인](https://code.sololearn.com/1624/#c)

<br>

- The `&` sign before the variable name is the `address operator`.
  - 변수 이름 앞의 `&` 기호는 `주소 연산자`이다.
- It gives the address, or location in memory, of a variable.
  - 변수의 주소 또는 메모리 상의 위치를 제공한다.
- This is needed because `scanf` places an input value at a variable address.
  - `scanf`가 변수 주소에 입력 값을 저장하므로, 이 작업이 필요하다.

<br>

- As another example, let's prompt for two integer inputs and output their sum:
  - 또 다른 예로, 두 개의 정수 입력을 요구하고, 그 합을 출력해보자.

```c
#include <stdio.h>

int main() {
  int a, b;
  printf("Enter two numbers:");
  scanf("%d %d", &a, &b);
  printf("\nSum: %d", a + b);
  
  return 0;
}

// Enter two numbers:
// Sum: (두 개의 숫자를 띄어쓰기와 함께 입력하면 합이 출력된다)
```

[코드 실행 확인](https://code.sololearn.com/1625/#c)

<br>

> `scanf()` stops reading as soon as it encounters a space, so text such as "Hello World" is two separate inputs for `scanf()`.
>
> `scanf()`는 공백을 만나자마자 읽는 것을 중단한다.
>
> "Hello World"와 같은 텍스트는 `scanf()`에 대한 별도의 두 입력이다.

------

<br>

### Output

###### 출력

<br>

- `putchar()` outputs a single character.
  - `putchar()`는 단일 문자를 출력한다.

```c
#include <stdio.h>

int main() {
  char a = getchar();
  printf("You entered: ");
  putchar(a);
  
  return 0;
}

// You entered: (직접 입력한 문자 중 한 글자만 출력된다)
```

[코드 실행 확인](https://code.sololearn.com/2225/#c)

<br>

- This input is stored in the variable `a`.
  - 입력은 변수 `a`에 저장된다.

<br>

- The `puts()` function is used to display output as a `string`.
  - `puts()` 함수는 출력을 `문자열`로 보여주는 데 사용된다.
- A string is stored in a char array.
  - 문자열을 char 배열에 저장된다.

```c
#include <stdio.h>

int main() {
  char a[100];
  gets(a);
  printf("You entered: ");
  puts(a);
  
  return 0;
}

// You entered: (직접 입력한 문자열이 출력된다)
```

[코드 실행 확인](https://code.sololearn.com/2226/#c)

<br>

- Here we stored the input in an array of 100 characters.
  - 위 코드에서 100자의 배열에 입력을 저장했다.

------

<br>

### Formatted Input

###### 형식화 입력

<br>

- The `scanf()` function is used to assign input to variables.
  - `scanf()` 함수는 변수에 입력을 할당하는 데 사용된다.
- A call to this function scans input according to format specifiers that convert input as necessary.
  - 이 함수를 호출하면, 필요에 따라 입력을 변환하는 서식 지정자에 의해 입력을 스캔한다.
- If input can't be converted, then the assignment isn't made.
  - 입력을 변환할 수 없으면, 할당이 수행되지 않는다.
- The `scanf()` statement waits for input and then makes assignments:
  - `scanf()` 문은 입력을 기다린 다음 할당을 수행한다.

```c
int x;
float num;
char text[20];
scanf("%d %f %s", &x, &num, text);
```

<br>

- Typing 10 22.5 abcd and then pressing Enter assigns 10 to x, 22.5 to num, and abcd to text.
  - 10 22.5 abcd를 입력한 다음 Enter를 누르면 x에 10, num에 22.5, text에 abcd가 할당된다.
- Note that the `&` must be used to access the variable addresses.
  - 변수 주소에 액세스하기 위해 `&`를 사용해야 한다.
- The `&` isn't needed for a string because a string name acts as a pointer.
  - 문자열 이름이 포인터 역할을 하므로, 문자열에는 `&`가 필요하지 않다.

<br>

- Format specifiers begin with a percent sign % and are used to assign values to corresponding arguments after the control string.
  - 서식 지정자는 백분율 기호 %로 시작한다.
  - 제어 문자열 후, 해당 인수에 값을 할당하는 데 사용된다.
- Blanks, tabs, and newlines are ignored.
  - 공백, 탭, 줄 바꿈(개행)은 무시된다.

<br>

- A format specifier can include several options along with a conversion character:
  - 서식 지정자는 변환 문자와 함께 여러 옵션을 포함할 수 있다.

<br>

```c
%[*][max_field]conversion character
```

<br>

- The optional \* will skip the input field.
  - 선택 사항인 \*는, 입력 필드를 생략한다.
- The optional max_width gives the maximum number of characters to assign to an input field.
  - 선택 사항인 max_width는, 입력 필드에 지정할 최대 문자 수를 제공한다.

<br>

- The conversion character converts the argument, if necessary, to the indicated type:
  - 필요한 경우, 변환 문자는 표시된 타입으로 인수를 변환한다.
- `d`: decimal
  - 10진법
- `c`: character
  - 문자
- `s`: string
  - 문자열
- `f`: float
  - 부동 소수점
- `x`: hexadecimal
  - 16진법

<br>

- For example:

```c
#include <stdio.h>

int main() {
  int x, y;
  char text[20];
  scanf("2%d %d %*f %5s", &x, &y, text);
  /* input: 1234 5.7 elephant */
  printf("%d  %d  %s", x, y, text);
  /* output: 12 34 eleph */
  
  return 0;
}
```

[코드 실행 확인](https://code.sololearn.com/1753/#c)

------

<br>

### Formatting Output

###### 형식화 출력

<br>

- The `printf` function was introduced in your first Hello World program.
  - `printf` 함수는 처음 Hello World 프로그램에서 소개되었다.
- A call to this function requires a `format string` which can include escape sequences for outputting special characters and format specifiers that are replaced by values.
  - 이 함수를 호출하려면 `서식 문자열`이 필요하다.
  - `서식 문자열`은 특수 문자를 출력하는 이스케이프 시퀀스와, 값으로 대체되는 서식 지정자를 포함할 수 있다.

```c
#include <stdio.h>

int main() {
  printf("The tree has %d apples.\n", 22);
  printf("\"Hello World!\"\n");
}

// The tree has 22 apples.
// Hello World!
```

[코드 실행 확인](https://code.sololearn.com/1649/#c)

<br>

- Escape sequences begin with a `backslash \`:
  - 이스케이프 시퀀스는 `백슬래시 \`로 시작한다.

<br>

1. `\n`: new line
   - 줄 바꿈 (개행)
2. `\t`: horizontal tab
   - 수평 탭
3. `\\`: backslash
   - 백슬래시
4. `\b`: backspace
   - 백스페이스
5. `\'`: single quote
   - 작은 따옴표
6. `\"`: double quote
   - 큰 따옴표

<br>

- Format specifiers begin with a `percent sign %` and are replaced by corresponding arguments after the format string.
  - 서식 지정자는 `백분율 기호 %`로 시작하고, 서식 문자열 후 해당 인수에 의해 대체된다.
- A format specifier can include several options along with a conversion character:
  - 서식 지정자는 변환 문자와 함께 여러 옵션을 포함할 수 있다.

```c
%[-][width].[precision]conversion character
```

<br>

- The optional `-` specifies left alignment of the data in the string.
  - 선택 사항인 `-`는 문자열에서 데이터의 왼쪽 정렬을 지정한다.
- The optional `width` gives the minimum number of characters for the data.
  - 선택 사항인 `width`는 데이터의 최소 문자 수를 제공한다.
- The `period .` separates the `width` from the `precision`.
  - `마침표 .`는 `width`와 `precision`을 구분한다.
- The optional `precision` gives the number of decimal places for numeric data.
  - 선택 사항인 `precision`은 숫자 데이터의 소수 자리수를 제공한다.
- If `s` is used as the conversion character, then precision determines the number of characters to print.
  - `s`가 변환 문자로 사용되면, precision은 출력할 문자 수를 결정한다.

<br>

- The conversion character converts the argument, if necessary, to the indicated type:
  - 필요한 경우, 변환 문자는 표시된 타입으로 인수를 변환한다.
- `d`: decimal
  - 10진법
- `c`: character
  - 문자
- `s`: string
  - 문자열
- `f`: float
  - 부동 소수점
- `e`: scientific notation
  - 과학적 표기법
- `x`: hexadecimal
  - 16진법

<br>

- For example:

```c
#include <stdio.h>

int main() {
  printf("Color: %s, Number: %d, float: %5.2f \n", "red", 42, 3.14159);
  printf("Pi = %3.2f \n", 3.14159);
  printf("Pi = %8.5f \n", 3.14159);
  printf("Pi = %-8.5f \n", 3.14159);
  printf("There are %d %s in the tree. \n", 22, "apples");
}

// Color: red, Number: 42, float: 3.14
// Pi = 3.14
// Pi = 3.14159
// Pi = 3.14159
// There are 22 apples in the tree.
```

[코드 실행 확인](https://code.sololearn.com/1650/#c)

<br>

- To print the % symbol, use %% in the format string.
  - % 기호를 출력하려면, 서식 문자열에 %%를 사용한다.

------

<br>

### QUIZ

- Type in a code to read a character from the input.
  - 입력의 문자를 읽도록 작성해라.

```c
char c = getchar();
```

<br>

- Fill in the blank to output the single character.
  - 단일 문자를 출력해라.

```c
char c = 's';
putchar(c);
```

<br>

- Fill in the blanks to input two integer variables using the scanf() function:
  - scanf() 함수를 사용해서 두 개의 정수 변수를 입력해라.

```c
int num1, num2;
scanf("%d %d", &num1, &num2);
```

<br>

- Fill in the blanks to format the output and print 4.42.
  - 출력을 구성하고, 4.42를 출력해라.

```c
printf("%3.2f", 4.4289743);
```

<br>