---
layout: post
title: "(Control Structures 06) while Loops"
categories: dev
tags: python
---

###### [SoloLearn](https://www.sololearn.com) Python 번역

<br>

- An `if` statement is run once if its condition evaluates to `True`, and never if it evaluates to `False`.
  - `if` 문은 조건이 `True`로 평가되면, 한 번 실행된다.
- A `while` statement is similar, except that it can be run more than once.
  - `while` 문은 두 번 이상 실행될 수 있다는 점을 제외하고는, `if` 문과 비슷하다.
- The statements inside it are repeatedly executed, as long as the condition holds.
  - 조건이 유지되는 한, 그 안의 명령문은 반복적으로 실행된다.
- Once it evaluates to `False`, the next section of code is executed.
  - `False`로 평가되면, 다음 코드 섹션이 실행된다.
- Below is a `while` loop containing a variable that counts up from 1 to 5, at which point the loop terminates.
  - 아래 코드는 1에서 5까지 카운트되는 변수를 포함한 `while` loop이다.
  - 5까지 카운트하고 loop가 종료된다.

```python
i = 1

while i <= 5:
  print(i)
  i = i + 1
  
print("Finished!")

# 1
# 2
# 3
# 4
# 5
# Finished!
```

<br>

> The code in the body of a `while` loop is executed repeatedly.
>
> `while` loop body의 코드는 반복적으로 실행된다.
>
> This is called `iteration`.
>
> 이를 `반복`이라고 한다.

<br>

- The `infinite loop` is a special kind of while loop; it never stops running.
  - `무한 loop`는 특별한 종류의 while loop이다.
  - 절대 실행이 멈추지 않는다.
- Its condition always remains `True`.
  - 무한 loop의 조건은 항상 `True`이다.
- An example of an infinite loop:
  - 무한 loop의 예는 다음과 같다.

```python
while 1 == 1:
  print("In the loop")
```

[코드 실행 확인](https://code.sololearn.com/308/#py)

<br>

- This program would indefinitely print "In the loop".
  - 위의 프로그램은 "In the loop"를 무한히 출력한다.

<br>

> You can stop the program's execution by using the Ctrl\-C shortcut or by closing the program.
>
> Ctrl\-C 단축키를 사용하거나 프로그램을 닫아서, 프로그램 실행을 멈출 수 있다.

<br>

## break

###### break 문

<br>

- To end a `while` loop prematurely, the `break` statement can be used.
  - `while` loop를 조기에 끝내기 위해, `break` 문을 사용할 수 있다.
- When encountered inside a loop, the `break` statement causes the loop to finish immediately.
  - `break` 문이 loop 내부에서 발견되면, loop가 즉시 종료된다.

```python
i = 0

while 1 == 1:
  print(i)
  i = i + 1
  
  if i >= 5:
    print("Breaking")
    break
    
print("Finished")

# 0
# 1
# 2
# 3
# 4
# Breaking
# Finished
```

[코드 실행 확인](https://code.sololearn.com/309/#py)

<br>

> Using the `break` statement outside of a loop causes an error.
>
> loop 외부에서 `break` 문을 사용하면 에러가 발생한다.

<br>

## continue

###### continue 문

<br>

- Another statement that can be used within loops is `continue`.
  - loop 내에서 사용할 수 있는 또 다른 명령문은 `continue`이다.
- Unlike `break`, `continue` jumps back to the top of the loop, rather than stopping it.
  - `break`와 달리, `continue`는 loop를 멈추지 않고, loop의 맨 위로 이동한다.

```python
i = 0

while True:
  i = i + 1
  
  if i == 2:
    print("Skipping 2")
    continue
    
  if i == 5:
    print("Breaking")
    break
    
  print(i)
  
print("Finished")

# 1
# Skipping 2
# 3
# 4
# Breaking
# Finished
```

[코드 실행 확인](https://code.sololearn.com/310/#py)

<br>

- Basically, the `continue` statement stops the current iteration and continues with the next one.
  - 기본적으로 `continue` 문은, 현재의 반복을 멈추고 다음 반복을 계속한다.

<br>

> Using the `continue` statement outside of a loop causes an error.
>
> loop 외부에서 ` continue` 문을 사용하면 에러가 발생한다.

<br>

<br>

#### QUIZ

- How many numbers does this code print?
  - 이 코드는 몇 개의 숫자를 출력하는가?

```python
i = 3

while i >= 0:
  print(i)
  i = i - 1
```

> `4`

<br>

- Fill in the blanks to create a loop that increaments the value of x by 2 and prints the even values.
  - x의 값을 2씩 증가시키고, 짝수를 출력하는 loop를 생성한다.

```python
x = 0

while x <= 20:
  print(x)
  x += 2
```

<br>

- How many numbers does this code print?
  - 이 코드는 몇 개의 숫자를 출력하는가?

```python
i = 5

while True:
  print(i)
  i = i - 1
  
  if i <= 2:
    break
```

> `3`

<br>

- Which statement ends the current iteration and continues with the next one?
  - 현재의 반복을 멈추고, 다음 반복을 계속하는 명령문은 무엇인가?

> `continue`

<br>

<br>