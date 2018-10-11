---
layout: post
title: "(Core Objects 04) 결합 배열"
categories: js
---

###### [SoloLearn](https://www.sololearn.com/) JS 번역

<br>

# JavaScript Associative Arrays

###### 결합 배열

<br>

- While many programming languages support arrays with named indexes (text instead of numbers), called `associative arrays`, JavaScript `does not`.
  - 많은 프로그래밍 언어가 `결합 배열`이라고 명명된 index(숫자 대신 텍스트)를 사용해서 배열을 지원하지만, JavaScript는 `지원하지 않는다`.
- However, you still can use the named array syntax, which produce an object.
  - 하지만 명명된 배열 구문을 사용해서 객체를 생성할 수 있다.

<br>

- For example:

```js
var person = [];	// empty array
person["name"] = "John";
person["age"] = 46;
document.write(person["age"]);	// Output 46
```

[코드 실행 확인](https://code.sololearn.com/700/#js)

<br>

- Now, person is treated as an object, instead of being an array.
  - 이제 person은 배열이 아닌 객체로 취급된다.
- The named indexes "name" and "age" become properties of the person object.
  - 명명된 index "name"과 "age"는 person 객체의 속성이 된다.

<br>

> As the person array is treated as an object, the standard array methods and properties will produce incorrect results.
>
> person 배열이 객체로 취급되기 때문에, 표준 배열 메소드와 속성은 잘못된 결과를 생성한다.

> For example, `person.length` will return 0.
>
> 예를 들어, `person.length`는 0을 반환한다.

<br>

<br>

- Remember that JavaScript `does not` support arrays with named indexes.
  - JavaScript는 명명된 index가 있는 배열을 `지원하지 않는다`.
- In JavaScript, arrays always use numbered indexes.
  - JavaScript에서 배열은 항상 번호가 매겨진 index를 사용한다.
- It is better to use an object when you want the index to be a string (text).
  - index를 문자열(텍스트)로 만들려면, 객체를 사용하는 것이 좋다.
- Use an `array` when you want the index to be a `number`.
  - index를 `숫자`로 사용하려면, `배열`을 사용해라.

<br>

> If you use a named index, JavaScript will redefine the array to a standard object.
>
> 명명된 index를 사용하면, JavaScript는 배열을 표준 객체로 다시 정의한다.

------

<br>

## QUIZ

- In associative arrays, index numbers are replaced with:
  - 결합 배열에서 index 숫자는 다음으로 대체된다.

> `strings`

<br>

- In order to use associative arrays, the "associated" name is put in:
  - 결합 배열을 사용하기 위해, "결합된" 이름이 ...에 입력된다.

> `brackets[]`

<br>