---
layout: post
title: "(Core Objects 01) 배열"
categories: js
---

###### [SoloLearn](https://www.sololearn.com/) JS 번역

<br>

## JavaScript Arrays

###### JS 배열

<br>

- `Arrays` store multiple values in a single variable.
  - `배열`은 하나의 변수에 여러 값을 저장한다.

<br>

- To store three course names, you need three variables.
  - 세 가지 course 이름을 저장하려면, 세 가지 변수가 필요하다.

```js
var course1 = 'HTML';
var course2 = 'CSS';
var course3 = 'JS';
```

<br>

- But what if you had 500 courses?
  - 하지만 500개의 course가 있다면?
- The solution is an `array`.
  - 해답은 `배열`이다.

```js
var courses = new Array('HTML', 'CSS', 'JS');
```

<br>

> This syntax declares an array named `courses`, which stores three values, or element.
>
> 이 구문은 `courses`라는 배열을 정의한다.
>
> 여기에는 세 개의 값 또는 element가 저장된다.

------

<br>

## Accessing an Array

###### 배열에 접근하기

<br>

- You refer to an array elemeny by referring to the `index number` written in `square brackets`.
  - `index(색인) 번호`를 참조해서 `대괄호`로 묶인 배열 element를 조회한다.
- This statement accesses the value of the first element in `courses` and changes the value of the second element.
  - 아래 문(statement)은 `courses`의 첫 번째 element 값에 액세스하고, 두 번째 element 값을 변경한다.

```js
var courses = new Array('HTML', 'CSS', 'JS');
var course = courses[0];	// HTML
courses[1] = 'C++';	// 두 번째 element를 변경한다
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
> 배열 index는 `0`으로 시작한다.

<br>

<br>

- Attempting to access an index outside of the array, returns the value `undefined`.
  - 배열 외부의 index에 액세스하려고 하면, `undefined` 값을 반환한다.

```js
var courses = new Array('HTML', 'CSS', 'JS');
document.write(courses[10]);	// undefined
```

[코드 실행 확인](https://code.sololearn.com/694/#js)

<br>

> Our `courses` array has just 3 elements, so the 10th index, which is the 11th element, does not exist (is undefined).
>
> `courses` 배열에는 3개의 element가 있으므로, 11번째 element인 10번째 index는 존재하지 않는다.
>
> (undefined)

------

<br>

## QUIZ

- What two keywords do we need to create an array?
  - 배열을 생성하는 데 필요한 두 가지 키워드는 무엇인가?
- Select all that apply.
  - 해당되는 것을 모두 선택해라.

> [ ] object
>
> [ ] `new`
>
> [ ] `Array`
>
> [ ] function

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
  - 존재하지 않는 배열 member를 참조하려고 시도한 결과는 무엇인가?

> `undefined`

<br>
