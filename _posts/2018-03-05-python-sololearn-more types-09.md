---
layout: post
title: "SoloLearn 번역 - 09. Text Analyzer (More Types)"
categories: dev
tags: python
---

## Text Analyzer (텍스트 분석기)

- This is an example project, showing a program that analyzes a sample file to find what percentage of the text each character occupies.
  - 이 예제 프로젝트는, 샘플 파일을 분석해서 각 문자가 차지하는 비율을 찾는 프로그램을 보여준다.
- This section shows how a file could be open and read.
  - 이 섹션에서는 파일을 열고 읽는 방법을 보여준다.

```python
filename = input("Enter a filename: ")

with open(filename) as f:
   text = f.read()
   
print(text)
```

<br>

- Result:

```python
>>>
Enter a filename: test.txt
Ornhgvshy vf orggre guna htyl.
Rkcyvpvg vf orggre guna vzcyvpvg.
Fvzcyr vf orggre guna pbzcyvpngrq.
Syng vf orggre guna arfgrq.
Fcenfr fv orggre guna qrafr.
Ernqnovyvgl pbhagf.
Fcrpvny pnfrf nera'g fcrpvny rabthu gb oernx gur ehyrf.
Nygubhtu cenpgvpnyvgl orgnf chevgl.
Reebef fubhyq arire cnff fvyragyl.
Hayrff rkcyvpvgyl fvyraprq.
Va gur snpr bs nzovthvgl, ershfr gur grzcgngvba bg thrff.
Gurer fubhyq or bar-- naq cersrenoylbayl bar --boivbhf jnl gb qb vg.
Nygubhtu gung jnl znl abg or boivbhf ng svefg hayrff lbh'er Qhgpu.
Abj vf orggre guna arrire.
Nygubhtu arire vf bsgra orggre guna *evtug* abj.
Vs gur vzcyrzragngvba vf uneq gb rkcynva, vg'f n onq vqrn.
Vs gur vzcyrzragngvba vf rnfl gb rkcynva, vg znl or n tbbq vqrn.
Anzrfcnprf ner bar ubaxvat terng vqrn -- yrg'f qb zber bs gubfr!

# 이게 맞는 건지 아직 잘 모르겠다. -오많배
```

<br>

> This is sample content for demonstration purposes only.
>
> 이는 데모용으로만 제공되는 샘플 컨텐츠이다.

------

<br>

## Text Analyzer 02

- This part of the program shows a function that counts how many times a character occurs in a string.
  - 프로그램의 이 부분은 문자열에서 문자가 몇 번 발생했는지 계산하는 함수를 보여준다.

```python
def count_char(text, char):
   count = 0
   for c in text:
      if c == char:
         count += 1
	return count
```

<br>

- This function takes as its arguments the text of the file and one character, returning the number of times that character appears in the text.
  - 이 함수는 파일의 텍스트와 문자 하나를 인수로 취해서, 텍스트에 문자가 나타나는 횟수를 반환한다.
- Now we can call it for our file.
  - 이제 파일로 호출할 수 있다.

```python
filename = input("Enter a filename: ")
with open(filename) as f:
   text = f.read()
   
print(count_char(text, "r"))
```

<br>

- Result:

```python
>>>
Enter a filename: test.txt
83
>>>
```

<br>

> The character "r" appears 83 times in the file.
>
> 문자 "r"은 파일에 83번 나타난다.

------

<br>

## Text Analyzer 03

- The next part of the program finds what percentage of the text each character of the alphabet occupies.
  - 프로그램의 다음 부분은 알파벳의 각 문자가 차지하는 텍스트의 비율을 찾는다.

```python
for char in "abcdefghijklmnopqrstuvwxyz":
   perc = 100 * count_char(text, char) / len(text)
   print("{0} - {1}%".format(char, round(perc, 2)))
```

<br>

- Let's put it all together and run the program:
  - 프로그램을 모두 같이 놓고 실행해보자.

```python
def count_char(text, char):
   count = 0
   for c in text:
      if c == char:
         count += 1
	return count

filename = input("Enter a filename: ")
with open(filename) as f:
   text = f.read()
   
for char in "abcdefghijklmnopqrstuvwxyz":
   perc = 100 * count_char(text, char) / len(text)
   print("{0} - {1}%".format(char, round(perc, 2)))
```

<br>

- Result:

```python
Enter a filename: test.txt
a - 4.68%
b - 4.94%
c - 2.28%
...
```

------

<br>

## QUIZ

- Fill in the blanks to read the contents of a file using the "with" statement.

```python
with open(filename) as f:
   text = f.read()
```

<br>

- Why has the character-counting code been put in a function?
  - **So it can be run multiple times**
  - So it can read files
  - So it is faster

<br>

- What is the purpose of the round function in the code?
  - To make it more precise
  - **To reduce the number of digits printed**
  - To save memory

<br>