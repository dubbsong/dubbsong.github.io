---
layout: post
title: "(Official VueJS 03) 인스턴스"
categories: dev
tags: vue
---

###### [Vue.js](https://kr.vuejs.org/index.html) 참조

<br>

## Vue 인스턴스

- 모든 Vue 앱은 `Vue` 함수로 새로운 `Vue 인스턴스`를 만드는 것부터 시작한다.
- 컨벤션으로, Vue 인스턴스를 참조하기 위해 종종 변수 `vm`(ViewModel의 약자)을 사용한다.

```js
var vm = new Vue({
  // 옵션
})
```

<br>

<br>

## 속성

- 각 Vue 인스턴스는 `data` 객체에 있는 모든 속성을 `프록시` 처리한다.

```js
// 데이터 객체
var data = { a: 1 }

// Vue 인스턴스에 데이터 객체 추가한다.
var vm = new Vue({
  data: data
})

// 같은 객체를 참조한다.
vm.a === data.a  // true

// 속성 설정은 원본 데이터에도 영향을 미친다.
vm.a = 2
data.a  // 2
```

<br>

- 빈 값이거나 존재하지 않은 상태로 시작한다면, 초기값을 지정할 필요가 있다.

```js
data: {
  newTodoText: '',
  visitCount: 0,
  hideCompletedTodos: false,
  todos: [],
  error: null
}
```

<br>

###### 메소드

```js
var data = { a: 1 }
var vm = new Vue({
  el: '#example',
  data: data
})

vm.$data === data  // true
vm.$el === document.getElementById('example')  // true

// $watch는 인스턴스 메소드이다.
vm.$watch('a', function(newValue, oldValue) {
  // vm.a가 변경되면 호출된다.
})
```

<br>

<br>