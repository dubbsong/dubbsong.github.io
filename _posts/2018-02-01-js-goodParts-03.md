---
layout: post
title: "JS 핵심 가이드 - 3. 객체"
categories: javascript
tags: JavaScript
---

###### \<자바스크립트 핵심 가이드>, 더글라스 크락포드 저 | 김명신 역

<br>

## CHAPTER 03 객체

- JS에서 단순한 데이터 타입은 `숫자`, `문자열`, `불리언`, `null`, `undefined`가 있다.
- 이들을 제외한 다른 값들은 모두 객체이다.
- 숫자, 문자열, 불리언은 메소드가 있기 때문에 `유사 객체`라고 할 수 있다.
- `객체`는 `변형 가능한 속성들의 집합`이라고 할 수 있다.
- 객체는 데이터를 한 곳에 모으고 구조화하는데 유용하다.
- 객체 하나는 다른 객체를 포함할 수 있기 때문에, 그래프나 트리 같은 자료구조를 쉽게 표현할 수 있다.
- 객체 하나에 있는 속성들을 다른 객체에 상속하게 해주는 `프로토타입(prototype)` 연결 특성이 있다. 이 특성을 잘 활용하면, 객체를 초기화하는 시간과 메모리 사용을 줄일 수 있다.

<br>

### 객체 리터럴

- 객체 리터럴은 아무것도 없거나, 하나 이상의 이름/값 쌍들을 둘러싸는 중괄호이다.
- 속성(property)의 이름은 어떤 문자열이라도 가능하다.
- 속성 이름에 사용한 따옴표는 속성 이름이 예약어가 아닐 경우에는 생략할 수 있다.
- 쉼표(,)는 이름/값 쌍들을 구분하는 데 사용한다.

```javascript
var empty_object = {};


var stooge = {
   "first-name": "Coco",
   "last-name": "Song"
};
```

<br>

### 속성값 읽기

- 객체에 속한 속성의 값은 속성 이름을 대괄호 []로 둘러싼 형태로 읽을 수 있다.
- 속성 이름이 예약어가 아닐 경우에는 마침표(.) 표기법을 사용할 수 있다.
- 객체에 존재하지 않는 속성을 읽으려고 하면 `undefined`를 반환한다.
- 존재하지 않는 속성, 즉 undefined의 속성을 참조하려고 할 때 `TypeError` 예외가 발생한다.
- `TypeError`를 방지하기 위해 `&&`를 사용할 수 있다.

```javascript
var flight = {
   airline: "Oceanic",
   number: 815,
   departure: {
      IATA: "SYD",
      time: "2018-02-01 06:00",
      city: "Sydney"
   },
   arrival: {
      IATA: "LAX",
      time: "2018-02-02 02:00",
      city: "Los Angeles"
   }
};


stooge["first-name"]	// "Coco"
flight.departure.IATA	// "SYD"

stooge["middle-name"]	// undefined
flight.status		// undefined

flight.equipment			// undefined
flight.equipment.model			// throw "TypeError"
flight.equipment && flight.equipment.model	// undefined
```

<br>

### 속성값의 갱신

- 객체의 값은 할당에 의해 갱신한다.
- 할당하는 표현식에서 속성 이름이 이미 객체 안에 존재한다면, 해당 속성의 값만 교체된다.

<br>

### 참조

- 객체는 참조 방식으로 전달된다. 결코 복사되지 않는다.

<br>

### 프로토타입 (Prototype)

- 모든 객체는 속성을 상속하는 프로토타입 객체에 연결되어 있다.
- 객체 리터럴로 생성되는 모든 객체는, JS의 표준 객체인 Object의 prototype(Object.prototype) 객체에 연결된다.
- 프로토타입 연결은 값의 갱신에 영향을 받지 않는다.
- 프로토타입 연결은 오로지 객체의 속성을 읽을 때만 사용한다.
- 객체에 있는 특정 속성 값을 읽으려고 하는데, 해당 속성이 객체에 없는 경우, JS는 이 속성을 프로토타입 객체에서 찾으려고 한다. 이러한 시도는 프로토타입 체인(prototype chain)의 가장 마지막에 있는 Obejct.prototype까지 계속해서 이어진다. 만약 찾으려는 속성이 프로토타입 체인 어디에도 존재하지 않는 경우 undefined를 반환한다. 이러한 일련의 내부 동작을 `위임(delegation)`이라고 한다.

<br>

### 리플렉션 (reflection)

- 객체에 어떤 속성들이 있는지는 특정 속성을 접근해서 반환하는 값을 보면 쉽게 알 수 있다.
- `typeof` 연산자는 속성의 타입을 살펴보는 데 매우 유용하다.

```javascript
typeof flight.number	// 'number'
typeof flight.status	// 'string'
typeof flight.arrival	// 'object'
typeof flight.manifest	// 'undefined'
```

<br>

- 일반적으로 리플렉션을 할 때는 데이터에 관심이 있기 때문에, 함수가 반환되는 경우를 염두에 두고 있다가 배제시키면 원하지 않는 속성을 배제할 수 있다.
- 또 다른 방법으로는, 객체에 특정 속성이 있는지를 확인하여 true/false 값을 반환하는 `hasOwnProperty` 메소드를 사용하는 것이다.
- `hasOwnProperty` 메소드는 프로토타입 체인을 바라보지 않는다.

<br>

### 열거 (Enumeration)

- `for in` 구문을 사용하면 객체에 있는 모든 속성의 이름을 열거할 수 있다.
- 하지만 속성들이 이름순으로 나온다는 보장이 없다.

<br>

### 삭제

- delete 연산자를 사용하면 객체의 속성을 삭제할 수 있다.
- 객체에서 특정 속성을 삭제했는데 같은 이름의 속성이 프로토타입 체인에 있는 경우, 프로토타입의 속성이 나타난다.

<br>

### 최소한의 전역변수 사용

- 전역변수는 프로그램의 유연성을 약화하기 때문에 가능하면 피하는 것이 좋다.
- 전역변수 사용을 최소화하는 방법은, 애플리케이션에서 전역변수 사용을 위해 다음과 같이 전역변수 하나를 만드는 것이다. 그리고 변수를 다른 전역변수를 위한 컨테이너로 사용한다.

```javascript
var MYAPP = {};


MYAPP.flight = {
   airline: "Oceanic",
   number: 815,
   departure: {
      IATA: "SYD",
      time: "2018-02-01 06:00",
      city: "Sydney"
   },
   arrival: {
      IATA: "LAX",
      time: "2018-02-02 02:00",
      city: "Los Angeles"
   }
};
```

<br>

- 이러한 방법으로 애플리케이션에 필요한 전역변수를 이름 하나로 관리하면 다른 애플리케이션이나 위젯 또는 라이브러리들과 연동할 때 발생하는 문제점을 최소화할 수 있다.

<br>

