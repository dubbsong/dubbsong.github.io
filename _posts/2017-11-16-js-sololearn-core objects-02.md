---
layout: post
title: "02. 배열을 생성하는 다른 방법 (Core Objects)"
categories: javascript
tags: js
---

###### [SoloLearn](https://www.sololearn.com) JS 번역

<br>

# JavaScript: Other Ways to Create Arrays

###### JavaScript: 배열을 생성하는 다른 방법

------

<br>

<br>

## Creating Arrays

###### 배열 생성하기

<br>

- You can also declare an array, tell it the number of elements it will store, and add the elements later.
  - 배열을 선언하고, 저장할 element의 숫자를 알려주고, 나중에 element를 추가할 수도 있다.

```JS
var courses = new Array(3);
courses[0] = "HTML";
courses[1] = "CSS";
courses[2] = "JS";

document.write(courses[2]);	// JS
```

[코드 실행 확인 링크](https://code.sololearn.com/696/#js)

<br>

> An array is a special type of `object`.
>
> 배열은 특별한 타입의 `객체`이다.

> An array uses `numbers` to access its elements, and an object uses `names` to access its members.
>
> 배열은 `숫자`를 사용해서 element에 액세스하고, 객체는 `이름`을 사용해서 액세스한다.

<br>

<br>

- JavaScript arrays are dynamic, so you can declare an array and not pass any arguments with the Array() constructor.
  - JavaScript 배열은 동적이므로, 배열을 선언하고 Array() 생성자를 사용해서 인수를 전달할 수 없다.
- You can then add the elements dynamically.
  - 그런 다음, element를 동적으로 추가할 수 있다.

```js
var courses = new Array();
courses[0] = "HTML";
courses[1] = "CSS";
courses[2] = "JS";
courses[3] = "C++";

document.write(courses[2]);	// JS
```

<br>

> You can add as many elements as you need to.
>
> 필요한 만큼 element를 추가할 수 있다.

<br>

#### Array Literal

###### 배열 리터럴

<br>

- For greater simplicity, readability, and execution speed, you can also declare arrays using the `array literal` syntax.
  - 단순성, 가독성, 실행 속도를 높이기 위해, `배열 리터럴` 구문을 사용해서 배열을 선언할 수도 있다.

```js
var courses = ["HTML", "CSS", "JS"];

document.write(courses[2]);	// JS
```

[코드 실행 확인 링크](https://code.sololearn.com/697/#js)

<br>

- This results in the same array as the one created with the `new Array()` syntax.
  - 결과적으로 `new Array()` 구문을 사용해서 생성한 배열과 같은 배열이 된다.

<br>

> You can access and modify the elements of the array using the index number, as you did before.
>
> 이전과 마찬가지로, 인덱스 숫자를 사용해서 배열의 element를 액세스하고 수정할 수 있다.

> The `array literal` syntax is the recommended way to declare arrays.
>
> `배열 리터럴` 구문은 배열을 선언하는 데 권장되는 방법이다.

------

<br>

## QUIZ

- Please insert the missing characters to output the third member of the array:
  - 누락된 문자를 삽입해서, 배열의 세 번째를 출력해라.

```js
document.write(example[2]);
```

<br>

- By entering var example = new Array(); we create an empty array which can be filled...
  - var example = new Array();를 입력해서 … 채워질 수 있는 빈 배열을 생성한다.

> `anytime later`
>
> 나중에 언제든지

<br>