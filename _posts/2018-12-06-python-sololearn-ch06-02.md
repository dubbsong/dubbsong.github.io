---
layout: post
title: "(Functional Programming 02) 람다"
categories: dev
tags: python
---

###### [SoloLearn](https://www.sololearn.com) Python 번역

<br>

- Creating a function normally (using `def`) assigns it to a variable automatically.
  - 함수를 정상적으로 생성(`def` 사용)하면, 변수에 자동으로 할당된다.
- This is different from the creation of other objects \- such as strings and integers \- which can be created on the fly, without assigning them to a variable.
  - 이는 문자열 및 정수와 같은 다른 객체의 생성과 다르다.
  - 변수에 할당하지 않고 즉시 생성될 수 있다.
- The same is possible with functions, provided that they are created using `lambda` syntax.
  - 함수가 `람다(lambda)` 구문을 사용해서 생성된 경우에도 마찬가지이다.
- Functions created this way are known as `anonymous`.
  - 이렇게 생성된 함수를 `익명(anonymous) 함수`라고 한다.
- This approach is most commonly used when passing a simple function as an argument to another function.
  - 이 접근법은, 단순한 함수를 다른 함수의 인수로 전달할 때 가장 일반적으로 사용된다.
- The syntax is shown in the next example and consists of the `lambda` keyword followed by a list of arguments, a colon, and the expression to evaluate and return.
  - 구문은 다음 예제에서 보여준다.
  - `lambda` 키워드, 인수의 나열, 콜론, 평가 및 반환할 표현식으로 구성된다.

```python
def my_func(f, arg):
  return f(arg)

my_func(lambda x: 2*x*x, 5)
```

<br>

> **Lambda (람다):**
>
> a shorthand to create anonymous functions
>
> 익명 함수를 생성하기 위한 단축이다.

<br>

> Lambda functions get their name from `lambda calculus`, which is a model of computation invented by Alonzo Church.
>
> 람다 함수는, Alonzo Church가 발명한 계산 모델인 `lambda 미적분학`에서 이름을 얻었다.

<br>

- Lambda functions aren't as powerful as named functions.
  - 람다 함수는 명명된 함수만큼 강력하지 않다.
- They can only do things that require a single expression \- usually equivalent to a single line of code.
  - 하나의 표현식이 필요한 작업만 수행할 수 있다.
  - 일반적으로 하나의 코드 라인과 동일하다.

```python
# named function
def polynomial(x):
  return x**2 + 5*x + 4
print(polynomial(-4))
# 0

# lambda
print((lambda x: x**2 + 5*x + 4)(-4))
# 0
```

<br>

> In the code above, we created an anonymous function on the fly and called it with an argument.
>
> 위의 코드에서는 익명 함수를 즉시 생성하고, 인수와 함께 호출했다.

<br>

- Lambda functions can be assigned to variables, and used like normal functions.
  - 람다 함수는 변수에 할당할 수 있다.
  - 그리고 일반 함수처럼 사용할 수 있다.

```python
double = lambda x: x * 2

print(double(7))
# 14
```

[코드 실행 확인](https://code.sololearn.com/384/#py)

<br>

> However, there is rarely a good reason to do this \- it is usually better to define a function with `def` instead.
>
> 하지만 이를 수행할 이유는 거의 없다.
>
> 대신 `def`를 사용해서 함수를 정의하는 것이 더 좋다.

<br>

<br>

#### QUIZ

- What are anonymous functions called?
  - 익명 함수를 뭐라고 부르는가?

> `Lambdas`

<br>

- Fill in the blanks to create a lambda function that returns the square of its argument, and call it for the number 8.
  - 인수의 제곱을 반환하는 람다 함수를 생성한다.
  - 숫자 8을 호출한다.

```python
a = (lambda x: x*x)(8)
```

<br>

- What is the result of this code?
  - 이 코드의 결과는 무엇인가?

```python
triple = lambda x: x * 3
add = lambda x, y: x + y

print(add(triple(3), 4))
```

> `13`

<br>

<br>