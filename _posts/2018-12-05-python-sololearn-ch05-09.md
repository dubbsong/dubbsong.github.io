---
layout: post
title: "(More Type 09) 텍스트 분석기"
categories: dev
tags: python
---

###### [SoloLearn](https://www.sololearn.com) Python 번역

<br>

- This is an example project, showing a program that analyzes a sample file to find what percentage of the text each character occupies.
  - 이 예제 프로젝트는, 샘플 파일을 분석해서 각 글자가 차지하는 텍스트의 백분율을 찾는 프로그램을 보여준다.
- This section shows how a file could be open and read.
  - 이 섹션은 파일을 열고 읽을 수 있는 방법을 보여준다.

```python
filename = input("Enter a filename: ")

with open(filename) as f:
  text = f.read()
  
print(text)

# Enter a filename: test.txt
# Ornhgvshy vf orggre guna htyl.
# Rkcyvpvg vf orggre guna vzcyvpvg.
# Fvzcyr vf orggre guna pbzcyvpngrq.
# Syng vf orggre guna arfgrq.
# Fcenfr fv orggre guna qrafr.
# Ernqnovyvgl pbhagf.
# Fcrpvny pnfrf nera'g fcrpvny rabthu gb oernx gur ehyrf.
# Nygubhtu cenpgvpnyvgl orgnf chevgl.
# Reebef fubhyq arire cnff fvyragyl.
# Hayrff rkcyvpvgyl fvyraprq.
# Va gur snpr bs nzovthvgl, ershfr gur grzcgngvba bg thrff.
# Gurer fubhyq or bar-- naq cersrenoylbayl bar --boivbhf jnl gb qb vg.
# Nygubhtu gung jnl znl abg or boivbhf ng svefg hayrff lbh'er Qhgpu.
# Abj vf orggre guna arrire.
# Nygubhtu arire vf bsgra orggre guna *evtug* abj.
# Vs gur vzcyrzragngvba vf uneq gb rkcynva, vg'f n onq vqrn.
# Vs gur vzcyrzragngvba vf rnfl gb rkcynva, vg znl or n tbbq vqrn.
# Anzrfcnprf ner bar ubaxvat terng vqrn -- yrg'f qb zber bs gubfr!
```

<br>

> This is sample content for demonstration purposes only.
>
> 이는 데모용 샘플 내용이다.

<br>

- This part of the program shows a function that counts how many times a character occurs in a string.
  - 아래 예제는, 문자열에서 글자가 몇 번 발생하는지 계산하는 함수를 보여준다.

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
  - 위의 함수는, 파일의 텍스트와 하나의 글자를 인수로 사용해서 해당 글자가 텍스트에 나타나는 횟수를 반환한다.

<br>

- Now we can call it for our file.
  - 이제 파일을 호출할 수 있다.

```python
filename = input("Enter a filename: ")

with open(filename) as f:
  text = f.read()
  
print(count_char(text, "r"))
# Enter a filename: test.txt
# 83
```

<br>

> The character "r" appears 83 times in the file.
>
> 파일에서 글자 "r"이 83번 나타난다.

<br>

- The next part of the program finds what percentage of the text each character of the alphabet occupies.
  - 프로그램의 다음 부분은, 알파벳의 각 글자가 차지하는 백분율을 찾는다.

```python
for char in "abcdefghijklmnopqrstuvwxyz":
  perc = 100 * count_char(text, char) / len(text)
  
print("{0} - {1}%".format(char, round(perc, 2)))
```

<br>

- Let's put it all together and run the program:
  - 모두 함께 넣고 프로그램을 실행해보자.

```python
def count_char(text, char):
  count = 0
  
  for c in text:
    if c == char:
      count += 1
      
  return count

file = open("newfile.txt", "w")
file.write("""Ornhgvshy vf orggre guna htyl.
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
Anzrfcnprf ner bar ubaxvat terng vqrn -- yrg'f qb zber bs gubfr!""")
file.close()

filename = "newfile.txt"
with open(filename) as f:
  text = f.read()
  
for char in "abcdefghijklmnopqrstuvwxyz":
  perc = 100 * count_char(text, char) / len(text)
  print("{0} - {1}%".format(char, round(perc, 2)))
  
# Enter a filename: test.txt
# a - 4.68%
# b - 4.94%
# ...
```

[코드 실행 확인](https://code.sololearn.com/380/#py)

<br>

<br>

#### QUIZ

- Fill in the blanks to read the contents of a file using the "with" statement.
  - "with" 문을 사용해서 파일의 내용을 읽어라.

```python
with open(filename) as f:
  text = f.read()
```

<br>

- Why has the character\-counting code been put in a function?
  - 함수에 글자를 세는 코드가 왜 삽입되었는가?

> So it can be run multiple times
>
> 여러 번 실행할 수 있다.

<br>

- What is the purpose of the round function in the code?
  - 코드에서 round 함수의 목적은 무엇인가?

> To reduce the number of digits printed
>
> 출력된 숫자의 자릿수를 줄이기 위해

<br>

<br>