---
layout: post
title: "(Objects 04) 메소드 추가하기"
categories: js
---

###### [SoloLearn](https://www.sololearn.com/) JS 번역

<br>

# JavaScript: Adding Methods

###### 메소드 추가하기

------

<br>

<br>

## Methods

###### 메소드

<br>

- `Methods` are functions that are stored as object properties.
  - `메소드`는 객체 속성으로 저장되는 함수이다.

<br>

- Use the following syntax to create an object method:
  - 객체 메소드를 생성하기 위해 다음 구문을 사용해라.

```js
methodName: function() { code lines }
```

<br>

- Access an object method using the following syntax:
  - 다음 구문을 사용해서 객체 메소드에 액세스해라.

```js
objectName.methodName()
```

<br>

- A `method` is a function, belonging to an object.
  - `메소드`는 객체에 속하는 함수이다.
- It can be referenced using the `this` keyword.
  - `this` 키워드를 사용해서 참조할 수 있다.
- The `this` keyword is used as a reference to the current object, meaning that you can access the objects properties and methods using it.
  - `this` 키워드는 현재 객체에 대한 참조로 사용된다.
  - 즉, 이를 사용해서 객체 속성과 메소드에 액세스 할 수 있다.

<br>

- Defining methods is done inside the `constructor` function.
  - 메소드를 정의하는 것은 `생성자` 함수 내에서 수행된다.

<br>

- For example:

```js
function person(name, age) {
   this.name = name;
   this.age = age;
   this.changeName = function (name) {
      this.name = name;
   }
}

var p = new person("David", 21);
p.changeName("John");	// 이제 p.name은 "John"과 같다
```

[코드 실행 확인](https://code.sololearn.com/692/#js)

<br>

- In the example above, we have defined a method named `changeName` for our person, which is a function, that takes a parameter `name` and assigns it to the `name` property of the object.
  - 위 예제에서 person에 대한 `changeName`이라는 메소드를 정의했다.
  - 이 메소드는 매개변수 `name`을 사용해서, 객체의 `name` 속성에 할당하는 함수이다.
- `this.name` refers to the name property of the object.
  - `this.name`은 객체의 name 속성을 참조한다.

<br>

> The `changeName` method changes the object's `name` property to its argument.
>
> `changeName` 메소드는 객체의 `name` 속성을 인수로 변경한다.

<br>

<br>

- You can also define the function outside of the `constructor` function and associate it with the object.
  - `생성자` 함수 외부에서 함수를 정의하고, 이를 객체와 연결할 수도 있다.

```js
function person(name, age) {
   this.name = name;
   this.age = age;
   this.yearOfBirth = bornYear;
}

function bornYear() {
   return 2016 - this.age;
}
```

<br>

- As you can see, we have assigned the object's `yearOfBirth` property to the `bornYear` function.
  - 보다시피, 객체의 `yearOfBirth` 속성을 `bornYear` 함수에 할당했다.
- The `this` keyword is used to access the *age* property of the object, which is going to call the method.
  - `this` 키워드는, 메소드를 호출할 객체의 *age* 속성에 액세스하는 데 사용된다.

<br>

> Note that it's not necessary to write the function's parentheses when assigning it to an object.
>
> 객체에 할당할 때, 함수의 괄호를 사용할 필요가 없다.

<br>

<br>

- Call the method as usual.
  - 평상시처럼 메소드를 호출해라.

```js
function person(name, age) {
   this.name = name;
   this.age = age;
   this.yearOfBirth = bornYear;
}

function bornYear() {
   return 2016 - this.age;
}

var p = new person("A", 22);
document.write(p.yearOfBirth());	// Outputs 1994
```

[코드 실행 확인](https://code.sololearn.com/693/#js)

<br>

> Call the method by the `property name` you specified in the constructor function, rather than the function name.
>
> 함수 이름 대신 생성자 함수에서 지정한 `속성 이름`으로 메소드를 호출해라.

------

<br>

## QUIZ

- The "this" keyword in the method means:
  - 메소드의 "this" 키워드는 다음을 의미한다.

> `The current object`
>
> 현재 객체

<br>

- Please associate the "testData" constructor function below with a method called "mymethod":
  - 아래의 "testData" 생성자 함수를 "mymethod"라는 메소드와 연결해라.

```js
function testData(first, second) {
   this.first = first;
   this.second = second;
   this.checkData = mymethod;
}
```

<br>

- In order to use the object's properties within a function, use:
  - 함수 내에서 객체의 속성을 사용하기 위해 사용하는 것은 무엇인가?

> `The "this" keyword`

<br>