---
layout: post
title: "SoloLearn - 06. while Loops (Control Structures)"
categories: dev
tags: python
---

## while Loops (while 루프)

- An if statement is run once if its condition evaluates to **True**, and never if it evaluates to **False**.
  - if 문은 조건이 **True**로 평가되면 실행하고, **False**로 평가되면 실행되지 않는다.
- A **while** statement is similar, except that it can be run more than once.
  - **while** 문은 몇 번이고 실행될 수 있다는 점을 제외하면 유사하다.
- The statements inside it are repeatedly executed, as long as the condition holds.
  - while 문 내부의 명령문은 조건이 성립하는 한 반복적으로 실행된다.
- Once it evaluates to **False**, the next section of code is executed.
  - **False**로 평가되면, 코드의 다음 섹션이 실행된다.

<br>

- Below is a **while** loop containing a variable that counts up from 1 to 5, at which point the loop terminates.
  - 아래는 1부터 5까지 카운트하는 변수를 포함하는 **while** 루프이다. 어느 지점에서 반복이 종료된다.

```python
i = 1
while i <= 5:
   print(i)
   i = i + 1
   
print("Finished!")
```

<br>

- Result:

```python
>>>
1
2
3
4
5
Finished!
>>>
```

<br>

> The code in the body of a **while** loop is executed repeatedly.
>
> **while** 루프의 body에 있는 코드는 반복적으로 실행된다.

> This is called **iteration**.
>
> 이를 **iteration**이라고 한다.

------

<br>

## while Loops 02

- The **infinite loop** is a special kind of while loop; it never stops running.
  - **무한 루프**는 특별한 종류의 while 루프이다. 절대 작동을 멈추지 않는다.
- Its condition always remains **True**.
  - 조건이 항상 **True**로 유지된다.

<br>

- An example of an infinite loop:
  - 무한 루프의 예:

```python
while 1 == 1:
   print("In the loop")
```

<br>

- This program would indefinitely print "In the loop".
  - 이 프로그램은 무한히 "In the loop"를 출력한다.

> You can stop the program's execution by using the Ctrl-C shortcut or by closing the program.
>
> Ctrl-C 단축키를 사용하거나 프로그램을 닫아 프로그램 실행을 멈출 수 있다.

------

<br>

## break

- To end a **while** loop prematurely, the break statement can be used.
  - **while** 루프를 조기에 종료하려면, break 문을 사용할 수 있다.
- When encountered inside a loop, the break statement causes the loop to finish immediately.
  - 루프 내에서 break 문이 발생하면, 루프가 즉시 끝난다.

```python
i = 0
while 1 == 1:
   print(i)
   i = i + 1
   if i >= 5:
      print("Breaking")
      break
      
print("Finished")
```

<br>

- Result:

```python
>>>
0
1
2
3
4
Breaking
Finished
>>>
```

<br>

> Using the **break** statement outside of a loop causes an error.
>
> 루프 밖에서 **break** 문을 사용하면 에러가 발생한다.

------

<br>

## continue

- Another statement that can be used within loops is **continue**.
  - 루프 내에서 사용할 수 있는 또 다른 명령문은 **continue**이다.
- Unlike break, **continue** jumps back to the top of the loop, rather than stopping it.
  - break와는 달리, **continue**는 루프를 멈추기보다는 루프의 맨 위로 돌아간다.

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
```

<br>

- Result:

```python
>>>
1
Skipping 2
3
4
Breaking
Finished
>>>
```

<br>

- Basically, the **continue** statement stops the current iteration and continues with the next one.
  - 기본적으로, **continue** 문은 현재의 반복을 멈추고 다음 반복을 계속한다.

> Using the **continue** statement outside of a loop causes an error.
>
> 루프 밖에서 **continue** 문을 사용하면 에러가 발생한다.

------

<br>

## QUIZ

- How many numbers does this code print?

```python
i = 3
while i >= 0:
   print(i)
   i = i - 1
   
4
```

<br>

- Fill the blanks to create a loop that increments the value of x by 2 and prints the even values.

```python
x = 0
while x <= 20:
   print(x)
   x += 2
```

<br>

- How many numbers does this code print?

```python
i = 5
while True:
   print(i)
   i = i - 1
   if i <= 2:
      break
      
3
```

<br>

- Which statement ends the current iteration and continues with the next one?
  - continue

<br>