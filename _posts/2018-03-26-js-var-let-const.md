---
layout: post
title: "var let const 비교"
categories: javascript
tags: javascript
---

#### not yet, keep going

<br>

## var

- 전역 변수의 남발 (Function-level scope)
- for loop 초기화식에서 사용한 변수를 for loop 외부 또는 전역에서 참조 가능 (Function-level scope)
- var 키워드 생략 허용 (의도하지 않은 변수의 전역화)
- 의도하지 않은 변수값 변경 (중복 선언 허용)
- 변수를 선언하기 전에 참조 (변수 호이스팅)

<br>

- 대부분의 문제는 전역 변수로 인해 발생한다.
- 전역 변수는 유효범위(scope)가 넓어서 어디에서 어떻게 사용될 것인지 파악하기 힘들다.
- ES6는 이러한 `var`의 단점을 보완하기 위해 `let`과 `const` 키워드를 도입했다.
- ES6를 사용한다면 var 키워드는 사용하지 않는다.

<br>

## let

- let 키워드로 선언된 변수는 Block-level scope를 갖는다.
  - Block-level scope
    코드 블럭 내에서 선언된 변수는 코드 블럭 내에서만 유효하며 코드 블럭 외부에서는 참조할 수 없다.
- let은 **중복 선언 시 SyntaxError**가 발생한다.
- JS는 모든 선언(var, let, const, function, class)을 호이스팅(Hoisting)한다. 하지만 let 키워드로 선언된 변수를 선언문 이전에 참조하면 ReferenceError가 발생한다. let 키워드로 선언된 변수는 스코프의 시작에서 변수의 선언까지 **일시적 사각지대(Temporal Dead Zone; TDZ)**에 빠지기 때문이다.
  - 호이스팅
    선언문 등을 해당 스코프의 선두로 옮겨진 것처럼 동작하는 특성을 말한다.

<br>

## const

- const는 상수(변하지 않는 값)를 위해 사용한다.
- const는 let과 대부분 동일한 특징을 갖는다.
- const는 초기화 이후 재할당이 금지된다.
- 상수는 가독성의 향상과 유지보수의 편의를 위해 적극적으로 사용해야 한다.
- const 변수의 값이 객체인 경우, 재할당은 불가능하지만, 할당된 객체의 내용(프로퍼티)은 변경할 수 있다.
- **객체 타입 변수 선언에는 const를 사용하는 것이 좋다.**
  - 일반적으로 객체에 대한 참조는 변경될 필요가 없다.
  - 만일 새로운 객체에 대한 참조를 변수에 재할당해야 한다면 let을 사용한다.

<br>

## var vs. let vs. const

- ES6를 사용한다면 var 키워드는 사용하지 않는다.
- 재할당이 필요한 primitive형 변수에는 let을 사용한다.
- 변경이 발생하지 않는(재할당이 필요없는) primitive형 변수와 객체형 변수에는 const를 사용한다.

<br>

- let, const를 이용하여 변수를 선언했을 경우, 유효범위는 블록 단위가 된다.
- 일반적으로 기본형(String, Number, Boolean, Null, Undefined)에 대해서 let은 값의 변경이 있을 경우, const는 상수를 선언할 때 사용된다. 하지만 참조형(Array, Object, Function)을 선언하는 경우에는 const를 사용하는 것이 바람직하다. 참조형은 const로 선언해도 조작이 가능하다.
- 오해하지 말자. const 변수에 할당된 값은 **절대로** 바뀌지 않는다. 재할당을 막는 게 곧 값을 못 바꾼다는 얘기다. 이건 그냥 말장난, 혹은 동어 반복이다.

<br>