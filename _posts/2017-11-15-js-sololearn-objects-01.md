---
layout: post
title: "01. JavaScript 객체 (Object)"
categories: javascript
tags: js
---

###### [SoloLearn](https://www.sololearn.com) JS 번역

<br>

# JavaScript Objects

###### JavaScript 객체

<br>

- JavaScript variables are containers for data values.
  - JavaScript 변수는 데이터 값의 컨테이너이다.
- `Objects` are variables too, but they can contain many values.
  - `객체`도 변수지만, 많은 값을 포함할 수 있다.
  - `object`: containers for named values (명명된 값의 컨테이너)

<br>

- Think of an object as a list of values that are written as `name:value` pairs, with the names and the values separated by colons.
  - 객체를 `name:value` 쌍으로 작성된 값의 list로 생각해보자.
  - name과 value는 콜론(:)으로 구분된다.

<br>

- Example:

```js
var person = {
   name: "John", age: 31,
   favColor: "green", height: 183
};
```

<br>

- These values are called `properties`.
  - 이러한 값을 `속성(property)`이라고 한다.

![sololearn img](/assets/img/sololearn-js-objects-01-01.png)

<br>

> JavaScript objects are containers for `named values`.
>
> JavaScript 객체는 `명명된 값`의 컨테이너이다.

------

<br>

## Object Properties

###### 객체 속성

<br>

- You can access object properties in two ways.
  - 두 가지 방법으로 객체 속성에 액세스 할 수 있다.

```js
objectName.propertyName
//or
objectName['propertyName']
```

<br>

- This example demonstrates how to access the age of our person object.
  - 이 예제는 person 객체의 나이에 액세스 하는 방법을 보여준다.

```js
var person = {
   name: "John", age: 31,
   favColor: "green", height: 183
};

var x = person.age;
var y = person['age'];

document.write(x);	// 31
document.write(y);	// 31
```

[코드 실행 확인 링크](https://code.sololearn.com/686/#js)

<br>

- JavaScript's built-in `length` property is used to count the number of characters in a property or string.
  - JavaScript의 내장된 `length` 속성은 속성이나 문자열의 문자 수를 계산하는 데 사용된다.

```js
var course = {name: "JS", lessons: 41};
document.write(course.name.length);	// Outputs 2
```

[코드 실행 확인 링크](https://code.sololearn.com/687/#js)

<br>

> Objects are one of the core concepts in JavaScript.
>
> 객체는 JavaScript의 핵심 개념 중 하나이다.

------

<br>

## Object Methods

###### 객체 메소드

<br>

- An object method is a property that contains a `function definition`.
  - 객체 메소드는 `함수 정의`를 포함하는 속성이다.
  - `method`: A function defined in an object (객체에 정의된 함수)

<br>

- Use the following syntax to access an object method.
  - 다음 구문을 사용해서 객체 메소드에 액세스 한다.

```js
objectName.methodName()
```

<br>

- As you already know, `document.write()` outputs data.
  - 이미 알고 있듯이, `document.write()`는 데이터를 출력한다.
- The `write()` function is actually a method of the `document object`.
  - `write()` 함수는 실제로 `문서 객체`의 메소드이다.

```js
document.write("This is some text");
```

[코드 실행 확인 링크](https://code.sololearn.com/688/#js)

<br>

> Methods are functions that are stored as object properties.
>
> 메소드는 객체 속성으로 저장되는 함수이다.

------

<br>

## QUIZ

- In reference to an object, color, height, weight and name are all examples of:
  - 객체를 참조할 때 color, height, weight, name은 모두 다음과 같다.

> `properties`
>
> 속성

<br>

- What built-in property is used to count the number of characters in an object's property?
  - 객체의 속성에서 문자 수를 계산하는 데 사용되는 내장된 속성은 무엇인가?

> `length`

<br>

- Access the "color" property of the "hair" object using dot syntax.
  - 점(.) 구문을 사용해서 "hair" 객체의 "color" 속성에 액세스 해라.

```js
hair.color
```

<br>