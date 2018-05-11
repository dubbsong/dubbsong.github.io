---
layout: post
title: "SoloLearn 번역 - 07. Modules (Function & Modules)"
categories: dev
tags: python
---

## Modules (모듈)

- **Modules** are pieces of code that other people have written to fulfill common tasks, such as generating random numbers, performing mathematical operations, etc.
  - **모듈**은 다른 사람들이 난수 생성, 수학 연산 수행 등과 같은 일반적인 작업을 수행하기 위해 작성한 코드 조각이다.

<br>

- The basic way to use a module is to add **import module_name** at the top of your code,
  - 모듈을 사용하는 기본적인 방법은 **import module_name**을 코드 상단에 추가하는 것이다.
- and then using **module_name.var** to access functions and values with the name **var** in the module.
  - 그런 다음, 모듈에서 **module_name.var**를 사용해서 **var**라는 이름의 함수 및 값에 액세스한다.
- For example, the following example uses the **random** module to generate random numbers:
  - 예를 들어, 다음 예제에서 **random** 모듈을 사용해 난수를 생성한다.

```python
import random

for i in range(5):
   value = random.randint(1, 6)
   print(value)
```

<br>

- Result:

```python
>>>
2
3
6
5
4
>>>
```

<br>

> The code uses the **randint** function defined in the **random** module to print 5 random numbers in the range 1 to 6.
>
> 이 코드는 **random** 모듈에 정의된 **randint** 함수를 사용해서 1부터 6까지 범위의 5개 난수를 출력한다.

------

<br>

## Modules 02

- There is another kind of **import** that can be used if you only need certain functions from a module.
  - 모듈에서 특정 함수만 필요할 경우 사용할 수 있는 다른 종류의 **import**가 있다.
- These take the form **from module_name import var**, and then **var** can be used as if it were defined normally in your code.
  - 이것들은 **from module_name import var** 양식을 취한 다음, 코드에서 정상적으로 정의된 것처럼 **var**를 사용할 수 있다.
- For example, to import only the **pi** constant from the **math** module:
  - 예를 들어, **math** 모듈에서 **pi** 상수만 가져오려면:

```python
from math import pi

print(pi)
```

<br>

- Result:

```python
>>>
3.141592653589793
>>>
```

<br>

- Use a comma separated list to import multiple objects.
  - 여러 객체를 가져오려면 콤마로 구분된 목록을 사용해라.

```python
from math import pi, sqrt
```

<br>

> \* imports all objects from a module. For example: **from math import** \*
>
> \* 모듈에서 모든 객체를 가져오려면: **from math import** \*

> This is generally discouraged, as it confuses variables in your code with variables in the external module.
>
> 이것은 코드의 변수와 외부 모듈의 변수를 혼동시키므로, 보통 권장하지 않는다.

------

<br>

## Modules 03

- Trying to import a module that isn't available causes an ImportError.
  - 사용할 수 없는 모듈을 가져오려고 하면 ImportError가 발생한다.

```python
import some_module
```

<br>

- Result:

```python
>>>
ImportError: No module named 'some_module'
```

------

<br>

## Modules 04

- You can import a module or object under a different name using the **as** keyword.
  - **as** 키워드를 사용해서 다른 이름으로 모듈이나 객체를 가져올 수 있다.
- This is mainly used when a module or object has a long or confusing name.
  - 이것은 주로 모듈이나 객체가 길거나 혼동스러운 이름을 가진 경우에 사용된다.

<br>

- For example:

```python
from math import sqrt as square_root
print(square_root(100))
```

<br>

- Result:

```python
>>>
10.0
>>>
```

------

<br>

## QUIZ

- Which module is being used in this code?
  - sqrt
  - **math**
  - num

```python
import math
num = 10
print(math.sqrt(num))
```

<br>

- Fill in the blanks to import only the sqrt and cos functions from the math module:

```python
from math import sqrt, cos
```

<br>

- What error is caused by importing an unknown module?
  - UnknownModuleError
  - **ImportError**
  - ModuleError

<br>

- What is the output of this code?
  - **An error occurs**
  - 5
  - 25

```python
import math as m
print(math.sqrt(25))
```

<br>