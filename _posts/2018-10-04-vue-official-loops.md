---
layout: post
title: "VueJS 반복문"
categories: vue
---

###### [Vue.js 공식 문서](https://kr.vuejs.org/v2/guide/#%EC%A1%B0%EA%B1%B4%EB%AC%B8%EA%B3%BC-%EB%B0%98%EB%B3%B5%EB%AC%B8) 참조

<br>

# VueJS Loops

###### VueJS 반복문

<br>

- testVue.html

```html
<body>
   <div id="app">
      <ol>
         <li v-for="todo in todos">
            { { todo.text } }
         </li>
      </ol>
   </div>
   
   <!-- script -->
   <script src="https://cdn.jsdelivr.net/npm/vue"></script>
   <script src="./testVue.js"></script>
</body>
```

<br>

- testVue.js

```js
var app = new Vue({
   el: '#app',
   data: {
      todos: [
         { text: 'JS 배우기' },
         { text: 'VueJS 배우기' },
         { text: '무언가 만들기' }
      ]
   }
});
```

<br>

- Result:

> 1. JS 배우기
> 2. VueJS 배우기
> 3. 무언가 만들기

<br>

#### 추가 조작 (네 번째 list 추가)

- `cmd` + `opt` + `J` (Chrome 개발자 도구 열기)
- Console

```js
app.todos.push({ text: 'New item '});
```

<br>

- Result:

> 1. JS 배우기
> 2. VueJS 배우기
> 3. 무언가 만들기
> 4. New item

<br>