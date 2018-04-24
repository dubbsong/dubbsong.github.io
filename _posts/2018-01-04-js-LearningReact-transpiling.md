---
layout: post
title: "러닝 리액트 - ES6 트랜스파일링"
categories: javascript
tags: javascript react
---

###### \<Learning React>, Alex Banks, Eve Porcello 저 | 오현석 역

<br>

## ES6 트랜스파일링

- 브라우저에서 ES6 코드를 실행하기 전에 ES5로 컴파일하는 변환을 `트랜스파일링(transpiling)`이라고 한다.
- 가장 유명한 트랜스파일링 도구는 `바벨(Babel)`이다.
- **트랜스파일링은 코드를 바이너리로 변환하는 것이 아니라는 점에서 컴파일과 다르다.**
- 트랜스파일링은 단지 한 버전의 JS 코드를 더 많은 브라우저가 이해할 수 있는 다른 버전의 JS 구문으로 변환하는 것이다.

<br>

#### 바벨 트랜스파일링 이전의 ES6 코드

```javascript
const add = (x=5, y=10) => console.log(x+y)
```

<br>

#### 위 코드를 트랜스파일러로 변환 후 출력

```javascript
"use strict";

var add = function add() {
   var x = arguments.length <= 0 || arguments[0] === undefined
   	? 5
   	: arguments[0];
   var y = arguments.length <= 1 || arguments[1] === undefined
   	? 10
   	: arguments[1];
   return console.log(x + y);
};
```

- 트랜스파일러는 `use strict` 선언을 맨 위에 추가해서 코드가 엄격한 모드에서 실행되도록 만든다.
- x와 y 파라미터의 디폴트 값은 arguments 배열로 처리된다.
- 이렇게 만들어진 JS는 다양한 브라우저에서 사용 가능하다.

<br>