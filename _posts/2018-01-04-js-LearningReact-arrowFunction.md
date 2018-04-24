---
layout: post
title: "러닝 리액트 - ES6 화살표 함수"
categories: javascript
tags: javascript react
---

###### \<Learning React>, Alex Banks, Eve Porcello 저 | 오현석 역

<br>

## 화살표 함수

- 화살표 함수(arrow function)를 사용하면 `function` 키워드 없이도 함수를 만들 수 있다.
- 화살표 함수를 사용하면 `return`을 사용하지 않아도 식을 계산한 값이 자동으로 반환된다.

<br>

#### 전통적인 방식의 함수 구문

```javascript
var lordify = function(firstname) {
   return `Dubbo의 ${firstname}`
}


console.log(lordify('오많배'))	// Dubbo의 오많배
```

<br>

#### 화살표 함수 구문

```javascript
var lordify = firstname => `Dubbo의 ${firstname}`


console.log(lordify('오많배'))	// Dubbo의 오많배
```

<br>

- 화살표 함수(`=>`)를 사용하면 모든 함수 정의를 한 줄로 끝낼 수 있다.
- 함수가 파라미터를 하나만 받는 경우, 파라미터 주변의 괄호를 생략해도 된다.
- 파라미터가 2개 이상이라면 괄호가 필요하다.
- 결과를 계산하기 위해 여러 줄을 사용해야 한다면 함수 본문 전체를 중괄호로 둘러싸야 한다.

<br>

- 화살표 함수는 `this`를 새로 바인딩하지 않는다.
- 다음 코드에서 this는 gangwon 객체가 아니다.
- 오류는 this.resorts의 join 메소드를 호출하려고 시도했기 때문에 발생한다.
- 이 경우 this가 **window 객체**이기 때문에 resorts가 **undefined**다.

```javascript
var gangwon = {
   resorts: ['평창', '강촌', '강릉', '홍천'],
   print: function(delay=1000) {
      setTimeout(function() {
         console.log(this.resorts.join(','))
      }, delay)
   }
}


gangwon.print()	// Uncaught TypeError: Cannot read property 'join' of undefined
```

<br>

- 화살표 함수를 사용하면 this 영역이 제대로 유지된다.
- join을 사용해 리조트 이름을 콤마(,)로 연결할 수 있다.
- 하지만 화살표 함수는 새로운 this 영역을 만들어내지 않는다.

```javascript
var gangwon = {
   resorts: ['평창', '강촌', '강릉', '홍천'],
   print: function(delay=1000) {
      setTimeout(() => {
         console.log(this.resorts.join(','))
      }, delay)
   }
}


gangwon.print()	// 평창, 강촌, 강릉, 홍천
```

<br>