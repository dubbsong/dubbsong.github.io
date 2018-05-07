---
layout: post
title: "JS 핵심 가이드 - 2. JS의 좋은 문법들"
categories: javascript
tags: JavaScript
---

###### \<자바스크립트 핵심 가이드>, 더글라스 크락포드 저 | 김명신 역

<br>

## CHAPTER 02 JS의 좋은 문법들

<br>

### 공백 (whitespace)

- 공백은 문자를 구분하는 형태나 주석의 형태를 취할 수 있다.
- 주석 역시 공백이다.
- `/* … */` 형태의 블록 주석과 `//…` 형태의 한 줄 주석을 사용할 수 있다.
- 주석은 가독성을 높이기 위해 충분히 사용되는 것이 좋다.
- 가능하면 `/* */`를 사용하는 대신 `//`를 사용할 것을 권한다.

<br>

### 이름 (Names)

- 이름은 문장, 변수, 매개변수, 속성명, 연산자, 라벨 등에 사용한다.
- 다음에 나오는 예약어들은 이름이 될 수 없다.

> abstract
>
> boolean break byte
>
> case catch char class const continue
>
> debugger default delete do double
>
> else enum export extends
>
> false final finally float for function
>
> goto
>
> if implements import in instanceof int interface
>
> long
>
> native new null
>
> package private protected public
>
> return
>
> short static super switch synchronized
>
> this throw throws transient true try typeof
>
> var volatile void
>
> while with
>
> \* 예약어에 꼭 포함될 것 같은 undefined, NaN, Infinity 등은 이 목록에 없다.

<br>

### 숫자 (Numbers)

- JS는 숫자형이 하나만 있다.
- 내부적으로 숫자는 `64비트 부동 소수점 형식`을 지닌다. 이는 자바의 double 형과 같다.
- 대부분의 다른 언어와는 달리 JS에는 정수와 실수의 구분이 없다. 즉 1과 1.0은 같은 값이다.
- 숫자형 때문에 발생하는 오류 대부분을 피할 수 있다.
- `NaN`은 수치 연산을 해서 `정상적인 값을 얻지 못할 때의 값`이다.
- NaN은 그 자신을 포함해서 어떤 값하고도 같지 않다.
- NaN인지 확인하려면 비교 구문이 아니라 `isNaN()`이라는 함수를 사용해야 한다.

<br>

### 문자열 (Strings)

- 문자열은 작은 따옴표나 큰 따옴표로 묶어서 나타낸다.
- \\(백 슬래시)는 이스케이프 문자이다.
- JS 내의 모든 문자는 `16비트 유니코드`이다.
- \\u로 시작하는 표기법은 유니코드 숫자값으로 문자를 나타낼 수 있다.
  - "A" === "\u0041"
- 문자열은 length라는 속성이 있다.
- 문자열은 변하지 않는다(`immutable`).

<br>

### 문장 (Statements)

- var 문은 함수 내부에서 사용될 때 함수의 private 변수를 정의한다.
- 문장들은 대개 위에서 아래로 실행한다.
- 실행 순서는 조건문(if, switch)이나 반복문(while, for, do) 또는 벗어나는 문장(break, return, throw)이나 함수 호출로 변경할 수 있다.
- 블록은 중괄호로 쌓인 문장들의 집합이다.
- 다른 언어들과 달리 JS에서 블록은 새로운 유효범위(scope)를 생성하지 않는다. 이러한 이유로 변수는 블록 안에서가 아니라 함수의 첫 부분에서 정의해야 한다.
- 거짓에 해당하는 값
  - false
  - null
  - undefined
  - ' '
  - 0
  - NaN
  - 이 외의 모든 값은 참
- switch 문은 다중 분기를 수행한다. 이 문장은 표현식과 모든 case 문의 표현식이 같은지를 비교한다. 일치하는 표현식을 찾으면 해당 case 절에 있는 문장들을 실행한다. 일치하는 표현식을 찾지 못하는 경우에는 default 절의 문장들을 실행한다.
- while 문은 단순한 반복 수행 문장이다. 표현식이 거짓이면 반복 수행은 끝난다.
- for 문은 좀 더 복잡한 반복문이다. 일반적인 형식은 초기화, 조건, 증가라는 세 가지 절로 제어하는 구조이다.
- do 문은 표현식이 블록을 실행하기 전이 아니라 실행한 후에 검사된다는 점만 빼면 while 문과 같다.
- try 문은 블록을 실행하면서 블록 내에서 발생하는 예외 상황을 포착한다. catch 절은 예외 객체를 받는 새로운 변수를 정의한다.
- throw 문은 예외를 발생한다.
- return 문은 함수에서 호출한 곳으로 되돌아가는 역할을 한다. 표현식이 지정되지 않으면 undefined를 반환한다.
- 할당 연산자(=)를 동등 연산자(===)와 혼동해서는 안 된다.

<br>

### 표현식 (Expressions)

- 가장 간단한 표현식은 리터럴 값(문자열이나 숫자), 변수, 내장값들(true, false, null, undefined, NaN, Infinity 등), new 키워드에 의한 호출 표현식, delete 키워드 다음에 나오는 세부지정 표현식, 괄호로 쌓인 표현식, 전치 연산자 다음에 이어지는 표현식 등이다.
- 삼항 연산자는 3개의 피연산자를 취한다. 첫 번째 피연산자가 참이면 두 번재 피연산자가 값이 되지만, 첫 번째 피연산자가 거짓인 경우에는 세 번째 피연산자가 값이 된다.
- typeof 연산자의 결과값에는 number, string, boolean, undefined, function, object 등이 있다.
- 피연산자가 배열이나 null이면 결과는 모두 object인데 이는 약간 문제가 있다.
- ! 연산자의 피연산자 값이 참이면 결과값은 거짓이다.
- && 연산자는 첫 번째 피연산자가 거짓일 경우 첫 번째 피연산자의 값을 취하고, 그렇지 않은 경우에는 두 번째 피연산자 값을 결과값으로 취한다.
- || 연산자는 &&와 반대로 첫 번째 피연산자가 참이면 이 값을 취하고, 그렇지 않으면 두 번째 피연산자를 결과값으로 취한다.
- 호출은 함수를 실행한다. 호출 연산자는 함수 이름 뒤에 이어지는 한 쌍의 괄호이다. 괄호 내에는 함수에 전달하는 인수를 포함할 수 있다.

<br>

### 리터럴 (Literals)

- 객체 리터럴은 새로운 객체를 생성할 때 편리한 표기법이다.

<br>

### 함수 (Functions)

- 함수 리터럴은 함수값을 정의한다.
- 함수 리터럴은 이름을 가질 수 있는데, 이 이름은 자신을 재귀적으로 호출할 때 사용할 수 있다.

<br>