---
layout: post
title: "러닝 리액트 - ES6 디폴트 파라미터"
categories: javascript
tags: javascript react
---

###### \<Learning React>, Alex Banks, Eve Porcello 저 | 오현석 역

<br>

## 디폴트 파라미터

- C++이나 파이썬 같은 언어에서는 함수의 인자로 디폴트 값을 선언할 수 있다.
- ES6 명세에도 디폴트 파라미터(default parameter)가 추가되었다.

<br>

- **함수를 호출하면서 값을 지정하지 않으면 디폴트 값이 사용된다.**
- logActivity 함수를 호출하면서 인자를 지정하지 않아도 디폴트 값을 사용해 함수가 정상적으로 실행된다.

```javascript
function logActivity(name='오많배', activity='코딩') {
   console.log(`${name}는 ${activity}을 좋아한다.`)
}


logActivity();	// 오많배는 코딩을 좋아한다.
```

<br>

- 문자열뿐 아니라 어떤 타입의 값도 디폴트 값으로 사용할 수 있다.

```javascript
var defaultPerson = {
   name: {
      first: '많배',
      last: '오'
   },
   favActivity: '코딩'
}


function logActivity(p=defaultPerson) {
   console.log(`${p.name.first}는 ${p.favActivity}을 좋아한다.`)
}


logActivity();	// 많배는 코딩을 좋아한다.
```

<br>