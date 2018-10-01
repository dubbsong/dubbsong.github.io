---
layout: post
title: "VueJS 컴포넌트 생성"
categories: vue
---

###### [Vue.js 공식 문서](https://kr.vuejs.org/v2/guide/index.html#%EC%BB%B4%ED%8F%AC%EB%84%8C%ED%8A%B8%EB%A5%BC-%EC%82%AC%EC%9A%A9%ED%95%9C-%EC%9E%91%EC%84%B1%EB%B0%A9%EB%B2%95) 참조

<br>

# VueJS Composing with Components

###### VueJS 컴포넌트 생성

<br>

- testVue.html

```html
<body>
   <div id="app">
      <ol>
         <todo-item 
                    v-for="item in groceryList" 
                    v-bind:todo="item" 
                    v-bind:key="item.id">
         </todo-item>
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
Vue.component('todo-item', {
   props: ['todo'],
   template: '<li>{{ todo.text }}</li>'
});

var app = new Vue({
   el: '#app',
   data: {
      groceryList: [
         { id: 0, text: 'Vegetables' },
         { id: 1, text: 'Cheese' },
         { id: 2, text: 'Whatever else humans are supposed to eat' }
      ]
   }
});
```

<br>

- Result:

> 1. Vegetables
> 2. Cheese
> 3. Whatever else humans are supposed to eat

<br>