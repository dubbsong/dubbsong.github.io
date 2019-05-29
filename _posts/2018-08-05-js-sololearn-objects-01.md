---
layout: post
title: "(Objects 01) 객체"
categories: js
---

###### [SoloLearn](https://www.sololearn.com/) JS 번역

<br>

## JavaScript Objects

###### JavaScript 객체

<br>

- JavaScript variables are containers for data values.
  - JavaScript 변수는 데이터 값의 컨테이너다.
- `Objects` are variables too, but they can contain many values.
  - `객체`도 변수이지만, 많은 값을 포함할 수 있다.

<br>

- Think of an object as a list of values that are written as `name:value` pairs, with the names and the values separated by colons.
  - 객체를 `이름:값` 쌍으로 작성된 값 목록으로 생각하자.
  - 이름과 값은 콜론으로 구분된다.

<br>

- For example:

```js
var person = {
   name: "John",
   age: 31,
   favColor: "green",
   height: 183
};
```

<br>

- These values are called `properties`.
  - 이러한 값들을 `속성(property)`이라고 한다.

![img](/assets/img/js-sololearn-objects-01-01.png)

<br>

> JavaScript objects are containers for `named values`.
>
> JavaScript 객체는 `명명된 값`의 컨테이너다.

------

<br>

## Object Properties

###### 객체 속성

<br>

- You can access object properties in two ways.
  - 두 가지 방법으로 객체 속성에 액세스 할 수 있다.

```js
objectName.propertyName

// or

objectName['propertyName']
```

<br>

- This example demonstrates how to access the age of our person object.
  - 아래 예제는 person 객체의 age에 어떻게 액세스하는지를 보여준다.

```js
var person = {
   name: "John",
   age: 31,
   favColor: "green",
   height: 183
};

var x = person.age;
var y = person['age'];

document.write(x);	// 31
document.write(y);	// 31
```

[코드 실행 확인](https://code.sololearn.com/686/#js)

<br>

- JavaScript's built-in `length` property is used to count the number of characters in a property or string.
  - JavaScript의 내장 `length` 속성은, 속성이나 문자열의 문자 수를 계산하는 데 사용된다.

```js
var course = {
   name: "JS",
   lessons: 41
};

document.write(course.name.length);	// 2
```

[코드 실행 확인](https://code.sololearn.com/687/#js)

<br>

> Objects are one of the core concepts in JavaScript.
>
> 객체는 JavaScript의 핵심 개념 중 하나이다.

------

<br>

## Object Methods

###### 객체 메소드

<br>

- An `object method` is a property that contains a `function definition`.
  - `객체 메소드`는 `함수 정의`를 포함하는 속성이다.

<br>

- Use the following syntax to access an object method.
  - 객체 메소드에 액세스하기 위해 다음 구문을 사용한다.

```js
objectName.methodName();
```

<br>

- As you already know, `document.write()` outputs data.
  - 이미 알다시피, `document.write()`는 데이터를 출력한다.
- The `write()` function is actually a method of the `document object`.
  - `write()` 함수는 사실 `document 객체`의 메소드이다.

```js
document.write('This is some text');
```

[코드 실행 확인](https://code.sololearn.com/688/#js)

<br>

> Methods are functions that are stored as object properties.
>
> 메소드는 객체 속성으로 저장되는 함수이다.

------

<br>

## QUIZ

- In reference to an object, color, height, weight and name are all examples of:
  - color, height, weight, name은 모두 ...의 예이다.

> `properties`
>
> 속성

<br>

- What built-in property is used to count the number of characters in an object's property?
  - 어떤 내장 속성이 객체 속성의 문자 수를 계산하는 데 사용되는가?

> `length` 속성

<br>

- Access the "color" property of the "hair" object using dot syntax.
  - dot 구문을 사용해서 "hair" 객체의 "color" 속성에 액세스해라.

```js
hair.color
```

<br>