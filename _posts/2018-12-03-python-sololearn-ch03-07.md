---
layout: post
title: "(Functions & Modules 07) 모듈(Module)"
categories: dev
tags: python
---

###### [SoloLearn](https://www.sololearn.com) Python 번역

<br>

- `Modules` are pieces of code that other people have written to fulfill common tasks, such as generating random numbers, performing mathematical operations, etc.
  - `모듈`은 다른 사람들이 일반적인 작업을 수행하기 위해 작성한 코드 조각이다.
  - 난수 생성, 수학 연산 등이 있다.
- The basic way to use a module is to add `import module_name` at the top of your code, and then using `module_name.var` to access functions and values with the name `var` in the module.
  - 모듈을 사용하는 가장 기본적인 방법은, 코드 상단에 `import module_name`을 추가한 다음, `module_name.var`를 사용해 모듈에서 이름이 `var`인 함수 및 값에 액세스하는 것이다.
- For example, the following example uses the `random` module to generate random numbers:
  - 예를 들어 다음 예제에서는, 난수를 생성하기 위해 `random` 모듈을 사용한다.

```python
import random

for i in range(5):
  value = random.randint(1, 6)
  print(value)
  
# 4
# 1
# 1
# 4
# 4
# 랜덤으로 5개의 수가 출력된다.
```

[코드 실행 확인](https://code.sololearn.com/340/#py)

<br>

> The code uses the `randint` function defined in the `random` module to print 5 random numbers in the range 1 to 6.
>
> 위의 코드는 `random` 모듈에 정의된 `randint` 함수를 사용해서 1과 6 사이 5개의 난수를 출력한다.

<br>

- There is another kind of `import` that can be used if you only need certain functions from a module.
  - 모듈에서 특정 함수만 필요한 경우, 다른 종류의 `import`를 사용할 수 있다.
- These take the form `from module_name import var`, and then `var` can be used as if it were defined normally in your code.
  - 이는 `from module_name import var`의 형식을 사용한다.
  - `var`가 코드에서 정상적으로 정의된 것처럼 사용할 수 있다.
- For example, to import only the `pi` constant from the `math` module:
  - 예를 들어, `math` 모듈에서 `pi` 상수만 import 해보자.

```python
from math import pi

print(pi)

# 3.141592653589793
```

[코드 실행 확인](https://code.sololearn.com/341/#py)

<br>

- Use a comma separated list to import multiple objects.
  - 쉼표로 구분해서 여러 객체를 import 할 수도 있다.

```python
from math import pi, sqrt
```

<br>

> \* imports all objects from a module.
>
> \*는 모듈의 모든 객체를 import 한다. (예: `from math import *`)
>
> This is generally discouraged, as it confuses variables in your code with variables in the external module.
>
> 일반적으로 이를 권장하지 않는다.
>
> 변수를 외부 모듈의 변수와 혼동할 수 있다.

<br>

- Trying to import a module that isn't available causes an ImportError.
  - 사용할 수 없는 모듈을 가져오려고 하면, ImportError가 발생한다.

```python
import some_module

# ImportError: No module named 'some_module'
```

<br>

- You can import a module or object under a different name using the `as` keyword.
  - `as` 키워드를 사용해서 다른 이름으로 모듈이나 객체를 import 할 수 있다.
- This is mainly used when a module or object has a long or confusing name.
  - 이는 모듈이나 객체의 이름이 길거나 혼동될 때 주로 사용된다.

```python
from math import sqrt as square_root
print(square_root(100))

# 10.0
```

[코드 실행 확인](https://code.sololearn.com/342/#py)

<br>

<br>

#### QUIZ

- Which module is being used in this code?
  - 아래 코드에서 어떤 모듈을 사용하는가?

```python
import math

num = 10
print(math.sqrt(num))
```

> `math`

<br>

- Fill in the blanks to import only the sqrt and cos functions from the math module:
  - math 모듈에서 sqrt와 cos 함수만 import 해라.

```python
from math import sqrt, cos
```

<br>

- What error is caused by importing an unknown module?
  - 알 수 없는 모듈을 import하면 어떤 에러가 발생하는가?

> `ImportError`

<br>

- What is the output of this code?
  - 이 코드의 출력은 무엇인가?

```python
import math as m
print(math.sqrt(25))
```

> An error occurs
>
> 에러가 발생한다.

<br>

<br>