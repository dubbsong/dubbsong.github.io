---
layout: post
title: "러닝 리액트 - ES6 템플릿 문자열"
categories: javascript
tags: javascript react
---

###### \<Learning React>, Alex Banks, Eve Porcello 저 | 오현석 역

<br>

## 템플릿 문자열

- 템플릿 문자열(template string)을 문자열 연결 대신 사용할 수 있다.
- 문자열 중간에 변수를 삽입할 수도 있다.

<br>

- 전통적인 문자열 연결은 더하기 기호(`+`)로 문자열과 변수를 서로 이어붙이는 방식을 사용한다.

```javascript
console.log(lastName + ", " + firstName + " " + middleName)
```

<br>

- 템플릿에서는 `${ }`를 사용해 문자열 안에 변수를 집어넣을 수 있기 때문에 문자열을 단 하나만 사용해도 된다.

```javascript
console.log(`${lastName}, ${firstName} ${middleName}`)
```

<br>

- `${ }`에는 값을 만들어내는 JS 식이라면 어떤 것이든 들어갈 수 있다.
- 템플릿 문자열은 공백(빈 칸뿐 아니라 개행 문자 등도 포함)을 유지한다.

<br>