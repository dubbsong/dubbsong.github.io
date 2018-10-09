---
layout: post
title: "(Objects 03) 객체 초기화"
categories: js
---

###### [SoloLearn](https://www.sololearn.com/) JS 번역

<br>

# JavaScript Object Initialization

###### 객체 초기화

<br>

- Use the `object literal` or `initializer` syntax to create single objects.
  - 하나의 객체를 생성하려면 `객체 리터럴` 또는 `초기화` 구문을 사용해라.

```js
var John = {
   name: "John",
   age: 25
};

var James = {
   name: "James",
   age: 21
};
```

<br>

> Objects consist of properties, which are used to describe an object.
>
> 객체는 객체를 설명하는 데 사용되는 속성으로 구성된다.

> Values of object properties can either contain primitive data types or other objects.
>
> 객체 속성의 값은 원시 데이터 type 또는 다른 객체를 포함할 수 있다.

------

<br>

## Using Object Initializers

###### 객체 초기화 사용하기

<br>

- Spaces and line breaks are not important.
  - 공백과 줄 바꿈은 중요하지 않다.
- An object definition can span multiple lines.
  - 객체 정의는 여러 줄에 걸칠 수 있다.

```js
var John = {
   name: "John",
   age: 25
};

var James = {
   name: "James",
   age: 21
};
```

<br>

- No matter how the object is created, the syntax for accessing the properties and methods does not change.
  - 객체가 어떻게 생성되는지 관계없이, 속성과 메소드에 액세스하는 구문은 변경되지 않는다.

```js
document.write(John.age);	// Outputs 25
```

[코드 실행 확인](https://code.sololearn.com/691/#js)

<br>

> Don't forget about the second accessing syntax: `John['age']`.
>
> 두 번째 access 구문을 잊지 마라: `John['age']`.

------

<br>

## QUIZ

- Complete the following expression to display the "simba" object's "category" property on the screen:
  - "simba" 객체의 "category" 속성을 화면에 표시해라.

> `document.write(simba.category);`

<br>
