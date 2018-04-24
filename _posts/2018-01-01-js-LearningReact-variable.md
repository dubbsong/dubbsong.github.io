---
layout: post
title: "러닝 리액트 - ES6 const, let"
categories: javascript
tags: javascript react
---

###### \<Learning React>, Alex Banks, Eve Porcello 저 | 오현석 역

<br>

### ES6에서 변수 선언하기

- ES6 이전에는 `var` 키워드가 변수를 선언하는 유일한 방법이었다.

<br>

## const

- `상수(constant)`는 값을 변경할 수 없는 변수다.
- 상수가 없던 시절에는 모든 값을 변수에 넣어 사용했다. 변수는 값을 변경할 수 있다.

```javascript
var pizza = true
pizza = false


console.log(pizza);	// false
```

<br>

- **상수에 값을 재설정하는 것은 불가능**하다. 값을 변경하려 하면 콘솔 오류가 발생한다.

```javascript
const pizza = true
pizza = false


// Uncaught TypeError: Assignment to constant variable.
```

<br>

## let

- JS도 이제는 **구문적인 변수 영역 규칙(lexical variable scoping)**을 지원한다.
- JS에서는 중괄호 {}를 사용해 코드 블럭을 만든다.

<br>

- **함수의 경우 코드 블럭이 별도의 변수 영역을 이룬다. 하지만 if/else 문 같은 경우는 다르다.**
- if/else 블럭 안에서 변수를 새로 만들면 그 변수의 영역이 그 블럭 안으로만 한정되지 않는다.
- if 블럭 안의 topic 변수의 값을 변경하면, if 블럭 밖의 topic 변수의 값도 변경된다.

```javascript
var topic = '자바스크립트'

if (topic) {
   var topic = '리액트'
   console.log('블럭', topic)	// 블럭 리액트
}

console.log('글로벌', topic)	// 글로벌 리액트
```

<br>

- `let` 키워드를 사용하면 변수 영역을 코드 블럭 안으로 한정시킬 수 있다.
- 글로벌 변수의 값을 보호할 수 있다.

```javascript
var topic = '자바스크립트'

if (topic) {
   let topic = '리액트'
   console.log('블럭', topic)	// 블럭 리액트
}

console.log('글로벌', topic)	// 글로벌 자바스크립트
```

<br>

- 중괄호가 새로운 영역을 만들어내지 못하는 다른 부분으로는 `for loop`가 있다.

```javascript
var div, container = document.getElementById('container')

for (var i = 0; i < 5; i++) {
   div = document.createElement('div')
   div.onclick = function() {
      alert('이것은 박스 #' + i + '입니다.')
   }
   container.appendChild(div)
}
```

- 이 루프에서는 컨테이너 안에 5개의 div를 만든다. 각 div에는 그 div의 인덱스를 경고창에 표시해주는 onClick 핸들러가 할당된다. for 루프 안에서 i를 선언해도 글로벌 영역에 i가 생기며 i가 5가 될 때까지 for 루프를 돈다. 그러므로 5개의 div 박스 중 어느 것을 클릭하건 i의 값은 글로벌 변수 i에 있는 5이기 때문에 표시되는 인덱스는 모두 같다.

![var](/assets/img/var.png)

<br>

- var 대신 let을 사용해 선언하면 i의 영역이 블럭으로 제한된다.

```javascript
var div, container = document.getElementById('container')

for (let i = 0; i < 5; i++) {
   div = document.createElement('div')
   div.onclick = function() {
      alert('이것은 박스 #: ' + i + '입니다.')
   }
   container.appendChild(div)
}
```

![let](/assets/img/let.png)

<br>