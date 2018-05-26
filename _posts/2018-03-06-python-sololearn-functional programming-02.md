---
layout: post
title: "SoloLearn 번역 - 02. Lambdas (Functional Programming)"
categories: dev
tags: python
---

## Lambdas (람다)

- Creating a function normally (using def) assigns it to a variable automatically.
  - 함수를 정상적으로 (def를 사용해서) 생성하면 변수에 자동으로 할당한다.
- This is different from the creation of other objects - such as strings and integers - which can be created on the fly, without assigning them to a variable.
  - 이는 변수에 할당하지 않고 즉시 생성될 수 있는 문자열 및 정수 같은 다른 객체를 만드는 것과는 다르다.
- The same is possible with functions, provided that they are created using **lambda** syntax.
  - **람다** 문법을 사용해서 작성되었다면, 함수에서도 마찬가지이다.
  - `lambda`: a shorthand to create anonymous functions
- Functions created this way are known as **anonymous**.
  - 이 방법으로 생성된 함수는 **익명**으로 알려져 있다.
- This approach is most commonly used when passing a simple function as an argument to another function.
  - 이 접근법은 간단한 함수를 다른 함수에 인수로 전달할 때 가장 일반적으로 사용된다.
- The syntax is shown in the next example and consists of the lambda keyword followed by a list of arguments, a colon, and the expression to evaluate and return.
  - 문법은 다음 예제에 표시되고, 인수 목록, 콜론, 평가하고 반환할 표현식으로 람다 키워드가 구성된다.

```python
def my_func(f, arg):
   return f(arg)

my_func(lambda x: 2*x*x, 5)
```

<br>

> Lambda functions get their name from **lambda calculus**, which is a model of computation invented by Alonzo Church.
>
> 람다 함수는 Alonzo Church가 만든 계산 모델인 **람다 미적분**으로부터 이름을 얻었다.

------

<br>

## Lambdas 02

- Lambda functions aren't as powerful as named functions.
  - 람다 함수는 명명된 함수만큼 강력하지 않다.
- They can only do things that require a single expression - usually equivalent to a single line of code.
  - 단일 표현식을 필요로 하는 작업만 수행할 수 있다. 일반적으로 단일 코드 행과 동일하다.

<br>

- Example:

```python
# named function
def polynomial(x):
   return x**2 + 5*x + 4
print(polynomial(-4))

# lambda
print((lambda x: x**2 + 5*x + 4) (-4))
```

<br>

- Result:

```python
>>>
0
0
>>>
```

<br>

> In the code above, we created an anonymous function on the fly and called it with an argument.
>
> 위의 코드에서, 즉시 익명 함수를 생성하고 인수로 호출했다.

------

<br>

## Lambdas 03

- Lambda functions can be assigned to variables, and used like normal functions.
  - 람다 함수는 변수에 할당할 수 있고, 일반 함수처럼 사용할 수 있다.

<br>

- Example:

```python
double = lambda x: x * 2
print(double(7))
```

<br>

- Result:

```python
>>>
14
>>>
```

<br>

> However, there is rarely a good reason to do this - it is usually better to define a function with **def** instead.
>
> 하지만, 이것을 수행하는 좋은 이유는 거의 없다. 보통 **def** 대신에 함수를 정의하는 것이 좋다.

------

<br>

## QUIZ

- What are anonymous functions called?
  - **lambdas**
  - lamdas
  - lombdas

<br>

- Fill in the blanks to create a lambda function that returns the square of its argument, and call it for the number 8.

```python
a = (lambda x: x*x) (8)
```

<br>

- What is the result of this code?

```python
triple = lambda x: x * 3
add = lambda x, y: x + y
print(add(triple(3), 4))


13
```

<br>