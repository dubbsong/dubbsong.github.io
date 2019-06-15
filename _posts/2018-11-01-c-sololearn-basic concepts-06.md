---
layout: post
title: "(Basic Concepts 06) 산술 연산자"
categories: dev
tags: c
---

###### [SoloLearn](https://www.sololearn.com/) C 번역

<br>

### Arithmetic Operators

###### 산술 연산자

<br>

- C supports arithmetic `operators` addtion (\+), subtraction (\-), multiplication (\*), division (/), and modulus division (%).
  - C는 `산술 연산자`를 지원한다.
  - 더하기(\+), 빼기(\-), 곱하기(\*), 나누기(/), 모듈러스 나누기(%)
- Operators are often used to form a `numeric expression` such as 10 + 5, which in this case contains two `operands` and the addition `operator`.
  - 연산자는 10 + 5와 같은 `숫자 표현식`을 구성하는 데 자주 사용된다.
  - 10 + 5의 경우, 두 개의 `피연산자`와 더하기 `연산자`가 포함된다.
- Numeric expressions are often used in assignment statements.
  - 숫자 표현식은 보통 할당 문에서 사용된다.

```c
#include <stdio.h>

int main() {
  int length = 10;
  int width = 5;
  int area;
  
  area = length * width;
  printf("%d \n", area);
  
  return 0;
}

// 50
```

[코드 실행 확인](https://code.sololearn.com/1626/#c)

<br>

###### Division

###### 나누기

<br>

- C has two division operators: `/` and `%`
  - C에는 `/`와 `%` 두 개의 나누기 연산자가 있다.
- The division / operator performs differently depending on the data types of the operands.
  - 나누기 / 연산자는, 피연산자의 데이터 타입에 따라 다르게 수행된다.
- When both operands are int data types, `integer division`, also called `truncated division`, removes any remainder to result in an integer.
  - 두 피연산자가 모두 int 데이터 타입인 경우, `정수 나누기` 또는 `절삭 나누기`라고 한다.
  - 정수가 되도록 나머지는 모두 제거한다.
- When one or both operands are real numbers (float or double), the result is a real number.
  - 하나 또는 두 피연산자가 실수(float 또는 double)인 경우, 결과는 실수(real number)이다.
- The % operator returns only the remainder of integer division.
  - % 연산자는 정수 나누기의 나머지만 반환한다.
- It is useful for many algorithms, including retrieving digits from a number.
  - 많은 알고리즘에 유용하다.
- `Modulus division` cannot be performed on floats or doubles.
  - `모듈러스 나누기`는 float 또는 double에서 수행될 수 없다.

<br>

- For example:

```c
#include <stdio.h>

int main() {
  int i1 = 10;
  int i2 = 3;
  int quotient, remainder;
  float f1 = 4.2;
  float f2 = 2.5;
  float result;
  
  quotient = i1 / i2;
  remainder = i1 % i2;
  result = f1 / f2;
  
  return 0;
}

// 3
// 1
// 1.680000
```

[코드 실행 확인](https://code.sololearn.com/1627/#c)

------

<br>

### Operator Precedence

###### 연산자 우선순위

<br>

- C evaluates a numeric expression based on `operator precedence`.
  - C는 `연산자 우선순위`에 따라 숫자 표현식을 평가한다.
- The \+ and \- are equal in precedence, as are \*, /, and %.
  - \+와 \-는 우선순위가 동일하다.
  - \*, /, %도 동일하다.
- The \*, /, and % are performed first in order from left to right and then \+ and \-, also in order from left to right.
  - \*, /, %는 왼쪽에서 오른쪽 순으로 먼저 수행한 다음, \+, \-를 왼쪽에서 오른쪽 순으로 수행한다.
- You can change the order of operations by using parentheses \() to indicate which operations are to be performed first.
  - 괄호 \()를 사용해서 먼저 수행할 연산자를 지정하면, 연산자의 순서를 변경할 수 있다.
- For example, the result of 5 \+ 3 \* 2 is 11, where the result of \(5 \+ 3) \* 2 is 16.
  - 예를 들어, 5 \+ 3 \* 2의 결과는 11이고, \(5 \+ 3) \* 2의 결과는 16이다.

```c
#include <stdio.h>

int main() {
  int a = 6;
  int b = 4;
  int c = 2;
  int result;
  
  result = a - b + c;	// 4
  result = a + b / c;	// 8
  result = (a + b) / c;	// 5
  
  return 0;
}
```

[코드 실행 확인](https://code.sololearn.com/1628/#c)

<br>

> C may not evaluate a numeric expression as desired when the associative property allows any order.
>
> 결합 법칙이 임의의 순서를 허용할 때, C는 숫자 표현식을 원하는 대로 평가하지 않을 수 있다.

> For example, x \* y \* z may be evaluated as \(x * y) \* z or as x \* \(y \* z).
>
> 예를 들어, x \* y \* z는 \(x \* y) \* z 또는 x \* \(y \* z)로 평가될 수 있다.

> If order is important, break the expression into separate statements.
>
> 순서가 중요한 경우, 표현식을 별도의 명령문으로 분리한다.

------

<br>

### Type Conversion

###### 타입 변환 (형 변환)

<br>

- When a numeric expression contains operands of different data types, they are automatically converted as necessary in a process called `type conversion`.
  - 숫자 표현식에 다른 데이터 타입의 피연산자가 포함되어 있는 경우, `형 변환`이라는 프로세스의 필요에 따라 자동으로 변환된다.
- For example, in an operation involving both floats and ints, the compiler will convert the int values to float values.
  - 예를 들어 float과 int를 모두 포함하는 연산에서는, 컴파일러가 int 값을 float 값으로 변환한다.
- In the following program, the `increase` variable is automatically converted to a `float`:
  - 다음 프로그램의 `increase` 변수는 `float`으로 자동 변환된다.

```c
#include <stdio.h>

int main() {
  float price = 6.50;
  int increase = 2;
  float new_price;
  
  new_price = price + increase;
  printf("New price is %4.2f", new_price);
  
  return 0;
}

// New price is 8.50
```

[코드 실행 확인](https://code.sololearn.com/1629/#c)

<br>

- Note the format specifier includes 4.2 to indicate the float is to be printed in a space at least 4 characters wide with 2 decimal places.
  - 서식 지정자에는 4.2가 포함된다.
  - float이 적어도 4자 이상의 둘째 소수 자릿수로 출력되어야 함을 나타낸다.
- When you want to force the result of an expression to a different type you can perform explicit type conversion by `type casting`, as in the statements:
  - 표현식의 결과를 다른 타입으로 강제 변환할 경우, `타입 캐스팅(type casting)`을 통해 명시적 형 변환을 수행할 수 있다.

```c
#include <stdio.h>

int main() {
  float average;
  int total = 23;
  int count = 4;
  
  average = (float) total / count;
  printf("%4.2f", average);
  
  return 0;
}

// 5.75
```

[코드 실행 확인](https://code.sololearn.com/1636/#c)

<br>

- Without the type casting, average will be assigned 5.
  - 타입 캐스팅이 없다면, average에 5가 할당된다.
- Explicit type conversion, even when the compiler may do automatic type conversion, is considered good programming style.
  - 명시적 형 변환은, 컴파일러가 자동 형 변환을 수행할 수 있는 경우에도 좋은 프로그래밍 스타일로 간주된다.

------

<br>

### Assignment Operators

###### 할당(대입) 연산자

<br>

- An `assignment statement` evaluates the expression on the right side of the equal sign first and then assigns that value to the variable on the left side of the =.
  - `할당 문`은 등호(=)의 오른쪽에 있는 표현식을 먼저 평가한 다음, 해당 값을 등호(=)의 왼쪽에 있는 변수에 할당한다.
- This makes it possible to use the same variable on both sides of an assignment statement, which is frequently done in programming.
  - 할당 문 양쪽에서 동일한 변수를 사용할 수 있다.
  - 이는 프로그래밍에서 자주 수행된다.

<br>

- For example:

```c
int x = 3;
x = x + 1;	// x is now 4
```

<br>

- To shorten this type of assignment statement, C offers the \+= `assignment operator`.
  - 이러한 타입의 할당 문을 단축하기 위해, C는 \+= `할당(대입) 연산자`를 제공한다.
- The statement above can be written as:
  - 위의 명령문을 다음과 같이 작성할 수 있다.

```c
x += 1;	// x = x + 1
```

<br>

- Many C operators have a corresponding assignment operator.
  - C의 여러 연산자에는 해당 할당 연산자가 있다.
- The program below demonstrates the arithmetic assignment operators:
  - 아래의 프로그램은 산술 할당 연산자를 보여준다.

```c
#include <stdio.h>

int main() {
  int x = 2;
  
  x += 1;	// 3
  x -= 1;	// 2
  x *= 3;	// 6
  x /= 2;	// 3
  x %= 2;	// 1
  x += 3 * 2;	// 7
  printf("%d", x);
  
  return 0;
}
```

[코드 실행 확인](https://code.sololearn.com/1630/#c)

<br>

- Look carefully at the last assignment statement.
  - 마지막 할당문에 주의한다.
- The entire expression on the right is evaluated and then added to x before being assigned to x.
  - x에 할당되기 전에, 오른쪽에 있는 전체 표현식이 평가된 다음 x에 더해진다.
- You can think of the statement as x = x \+ \(3 \* 2).
  - x = x \+ \(3 \* 2)로 생각할 수 있다.

------

<br>

### Increment & Decrement Operators

###### 증가 & 감소 연산자

<br>

- Adding 1 to a variable can be done with the `increment operator ++`.
  - `증가 연산자 ++`로 변수에 1을 더할 수 있다.
- Similarly, the `decrement operator --` is used to subtract 1 from a variable.
  - 마찬가지로, `감소 연산자 --`는 변수에서 1을 빼는 데 사용된다.

<br>

- For example:

```c
z--;	// decrement z by 1
y++;	// increment y by 1
```

<br>

- The increment and decrement operators can be used either `prefix` (before the variable name) or `postfix` (after the variable name).
  - 증가 및 감소 연산자는 `접두부(prefix)` 또는 `접미부(postfix)` 중 하나를 사용할 수 있다.
- Which way you use the operator can be important in an assignment statement, as in the following example.
  - 연산자를 사용하는 방법은, 아래 예제와 같이 할당문에서 중요할 수 있다.

```c
#include <stdio.h>

int main() {
  int x, y, z;
  
  z = 3;
  x = z--;	// assign 3 to x, then decrement z to 2
  printf("x=%d \n", x);
  
  y = 3;
  x = ++y;	// increment y to 4, then assign 4 to x
  printf("x=%d \n", x);
  printf("y=%d \n", y);
  
  return 0;
}
```

[코드 실행 확인](https://code.sololearn.com/1637/#c)

<br>

- The `prefix` form increments/decrements the variable and then uses it in the assignment statement.
  - `접두부(prefix)`  형식은 변수를 증가/감소한 다음, 할당문에서 사용한다.
- The `postfix` form uses the value of the variable first, before incrementing/decrementing it.
  - `접미부(postfix)` 형식은 변수의 값을 먼저 사용한 다음, 증가/감소시킨다.

------

<br>

### QUIZ

- What is the value of the result variable?
  - result 변수의 값은 무엇인가?

```c
int a = 12;
int b = 5;
int result = a % b;
```

> `2`

<br>

- Fill in the blanks to subtract y from x and add z to the result.
  - x에서 y를 빼고, 그 결과에 z를 더해라.

```c
int x = 6;
int y = 4;
int z = 2;

int res = x - y + z;
```

<br>

- Explicitly convert the result of the division to float:
  - 나누기의 결과를 float으로 명시적 변환해라.

```c
average = (float) total / count;
```

<br>

- Type in the missing operator to add the value of num2 to num1:
  - num2의 값을 num1에 추가해라.

```c
int num1 = 8;
int num2 = 42;

num1 += num2;
```

<br>

- What is the value of x after the following code?
  - 다음 코드 후, x의 값은 무엇인가?

```c
int x = 8;
int y = 7;
x++;
x+=y--;
```

> `16`

<br>