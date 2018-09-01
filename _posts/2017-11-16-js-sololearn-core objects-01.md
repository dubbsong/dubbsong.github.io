---
layout: post
title: "01. 배열 (Core Objects)"
categories: javascript
tags: js
---

###### [SoloLearn](https://www.sololearn.com) JS 번역

<br>

# JavaScript Arrays

###### JavaScript 배열

<br>

- `Arrays` store multiple values in a single variable.
  - `배열`은 하나의 변수에 여러 값을 저장한다.
  - `array`: used to store multiple values in a single variable (하나의 변수에 여러 값을 저장하는 데 사용된다)

<br>

- To store three course names, you need three variables.
  - 세 개의 course 이름을 저장하려면, 세 개의 변수가 필요하다.

```js
var course1 = "HTML";
var course2 = "CSS";
var course3 = "JS";
```

<br>

- But what if you had 500 courses?
  - 하지만 500개의 course가 있다면?
- The solution is an `array`.
  - 해결책은 `배열`이다.

```js
var courses = new Array("HTML", "CSS", "JS");
```

<br>

> This syntax declares an array named `courses`, which stores three values, or elements.
>
> 이 구문은 세 개의 값 또는 element를 저장하는 `courses`라는 배열을 선언한다.

------

<br>

## Accessing an Array

###### 배열에 액세스하기

<br>

- You refer to an array element by referring to the `index number` written in `square brackets`.
  - `꺾쇠괄호 []`로 묶인 `인덱스 숫자`를 조회해서 배열 element를 참조해라.
- This statement accesses the value of the first element in `courses` and changes the value of the second element.
  - 이 명령문은 `courses`에서 첫 번째 element의 값에 액세스하고, 두 번째 element의 값을 변경한다.

```js
var courses = new Array("HTML", "CSS", "JS");
var course = courses[0];	// HTML
courses[1] = "C++";	// Changes the second element
```

<br>

> [0] is the first element in an array.
>
> [0]은 배열의 첫 번째 element이다.

> [1] is the second.
>
> [1]은 두 번째 element이다.

> Array indexes start with `0`.
>
> 배열 인덱스는 0부터 시작한다.

<br>

<br>

- Attempting to access an index outside of the array, returns the value `undefined`.
  - 배열 외부의 인덱스에 액세스하려고 시도하면, `undefined`를 반환한다.

```js
var courses = new Array("HTML", "CSS", "JS");

document.write(courses[10]);	// undefined
```

[코드 실행 확인 링크](https://code.sololearn.com/694/#js)

<br>

> Our `courses` array has just 3 elements, so the 10th index, which is the 11th element, does not exist (is undefined).
>
> `courses` 배열에는 단지 3개의 element가 있으므로, 11번째 element인 10번째 인덱스는 존재하지 않는다(undefined).

------

<br>

## QUIZ

- What two keywords do we need to create an array?
  - 배열을 만드는 데 필요한 두 가지 키워드는 무엇인가?

> `new`
>
> `Array`

<br>

- What is the output of this code?
  - 이 코드의 출력은 무엇인가?

```js
var arr = new Array(3, 6, 8);

document.write(arr[1]);
```

> `6`

<br>

- What is the result of trying to reference an array member which does not exist?
  - 존재하지 않는 배열 일부를 참조하려고 시도한 결과는 무엇인가?

> `undefined`

<br>