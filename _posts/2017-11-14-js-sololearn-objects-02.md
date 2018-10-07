---
layout: post
title: "(Objects 02) 객체 생성하기"
categories: js
---

###### [SoloLearn](https://www.sololearn.com/) JS 번역

<br>

# JavaScript: Creating Objects

###### 객체 생성

------

<br>

<br>

## The Object Constructor

###### 객체 생성자

<br>

- In the previous lesson, we created an object using the `object literal` (or initializer) syntax.
  - 이전 레슨에서, `객체 리터럴`(또는 초기화) 구문을 사용해서 객체를 생성했다.

```js
var person = {
   name: "John",
   age: 42,
   favColor: "green"
};
```

<br>

- This allows you to create only a single object.
  - 이렇게 하면 하나의 객체를 생성할 수 있다.
- Sometimes, we need to set an "`object type"` that can be used to create a number of objects of a single type.
  - 때로는 단일 type의 여러 객체를 생성하는 데 사용할 수 있는 "`객체 type`"을 설정해야 한다.
- The standard way to create an "object type" is to use an object `constructor function`.
  - "객체 type"을 생성하는 표준 방법은 객체 `생성자 함수`를 사용하는 것이다.

```js
function person(name, age, color) {
   this.name = name;
   this.age = age;
   this.favColor = color;
}
```

<br>

- The above function (person) is an object constructor, which takes parameters and assigns them to the object properties.
  - 위 함수(person)는 매개변수를 가져와서 객체 속성에 할당하는 객체 생성자이다.

<br>

> The `this` keyword refers to the `current object`.
>
> `this` 키워드는 `현재 객체`를 나타낸다.

> Note that `this` is not a variable.
>
> `this`는 변수가 아니다.

> It is a keyword, and its value cannot be changed.
>
> 이는 키워드이며, 값을 변경할 수 없다.

------

<br>

## Creating Objects

###### 객체 생성

<br>

- Once you have an object constructor, you can use the `new` keyword to create new objects of the same type.
  - 객체 생성자가 있으면, `new` 키워드를 사용해서 동일한 type의 새로운 객체를 생성할 수 있다.

```js
var p1 = new person("John", 42, "green");
var p2 = new person("Amy", 21, "red");

document.write(p1.age);	// 42
document.write(p2.name);	// "Amy"
```

[코드 실행 확인](https://code.sololearn.com/689/#js)

<br>

> *p1* and *p2* are now objects of the `person` type.
>
> *p1*과 *p2*는 이제 `person` type의 객체이다.

> Their properties are assigned to the corresponding values.
>
> 해당 속성은 해당 값에 할당된다.

<br>

- Consider the following example.
  - 다음 예제를 살펴보자.

```js
function person(name, age) {
   this.name = name;
   this.age = age;
}

var John = new person("John", 25);
var James = new person("James", 21);
```

[코드 실행 확인](https://code.sololearn.com/690/#js)

<br>

- Access the object's properties by using the `dot syntax`, as you did before.
  - 이전과 마찬가지로, `dot 구문`을 사용해서 객체의 속성에 액세스한다.

![img](/assets/img/js-sololearn-object-02-01.png)

<br>

> Understanding the creation of objects is essential.
>
> 객체의 생성에 대한 이해는 필수적이다.

------

<br>

## QUIZ

- Fill in the blanks to create a constructor function:
  - 생성자 함수를 생성해라.

```js
function movie(title, director) {
   this.title = title;
   this.director = director;
}
```

<br>

- What keyword is used for creating an instance of an object?
  - 어떤 키워드가 객체의 인스턴스를 생성하는 데 사용되는가?

> `new`

<br>

- Which two components are necessary in order to use information contained within an object?
  - 객체에 포함된 정보를 사용하려면 어떤 두 가지 컴포넌트가 필요한가?

> [ ] keyword "this"
>
> [ ] constructor function's name
>
> [ ] `property's name`
>
> [ ] `object's name`

<br>