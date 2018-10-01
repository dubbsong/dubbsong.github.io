---
layout: post
title: "VueJS 인스턴스"
categories: vue
---

###### [Vue.js 공식 문서](https://kr.vuejs.org/v2/guide/instance.html) 참조

<br>

# VueJS Instance

###### VueJS 인스턴스

<br>

- 모든 Vue 앱은 `Vue` 함수로 `새로운 Vue 인스턴스`를 만드는 것부터 시작한다.

```js
var vm = new Vue({
   // 옵션
});
```

<br>

- Todo 앱의 컴포넌트 tree

```js
Root Instance
└─ TodoList
   ├─ TodoItem
   │  ├─ DeleteTodoButton
   │  └─ EditTodoButton
   └─ TodoListFooter
      ├─ ClearTodosButton
      └─ TodoListStatistics
```

<br>

#### Data & Method

###### 데이터 & 메소드

<br>

- 각 Vue 인스턴스는 `data` 객체에 있는 모든 속성을 `프록시` 처리한다.

```js
var data = { a: 1 }	// 데이터 객체

var vm = new Vue({	// Vue 인스턴스에 데이터 객체를 추가한다.
   data: data
});

vm.a === data.a	// true, 같은 객체를 참조한다.

va.a = 2	// 속성 설정은 원본 데이터에도 영향을 미친다.
data.a	// 2
```

<br>

- 데이터가 변경되면 화면이 다시 렌더링 된다.
- 하지만 `data`에 있는 속성들은 인스턴스가 생성될 때 존재한 것들만 `반응형`이다.
- `b`가 변경되어도 갱신되지 않는다.
- 어떤 속성이 나중에 필요하다는 것을 알고 있고, 빈 값이거나 존재하지 않는 상태로 시작한다면, 초기값을 지정할 필요가 있다.

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

- 유일한 예외는 `Object.freeze()`를 사용하는 경우이다.
- 이는 기존 속성이 변경되는 것을 막아 반응성 시스템이 추적할 수 없다는 것을 의미한다.

```js
var obj = {
   foo: 'bar'
};

Object.freeze(obj);	// 변경을 방지해준다.

new Vue({
   el: '#app',
   data: obj
});
```

```html
<div id="app">
   <p>{{ foo }}</p>
   <!-- obj.foo는 더 이상 변하지 않는다. -->
   <button v-on:click="foo = 'baz'">Change it</button>
</div>
```

<br>

#### Instance Lifecycle Hooks

###### 인스턴스 라이프사이클 hook

<br>

- 각 Vue 인스턴스는 데이터 관찰을 설정하고, 템플릿을 컴파일하고, 인스턴스를 DOM에 마운트하고, 데이터가 변경될 때, DOM을 업데이트 해야 할 때 일련의 초기화 단계를 거친다.
- 그 과정에서 사용자 정의 로직을 실행할 수 있는 `라이프사이클 hook`도 호출된다.
- 예를 들어, `created` hook은 인스턴스가 생성된 후에 호출된다.

```js
new Vue({
   data: {
      a: 1
   },
   created: function() {
      console.log('a is: ' + this.a)	// 'this'는 vm 인스턴스를 가리킨다.
   }
});

// a is: 1
```

<br>