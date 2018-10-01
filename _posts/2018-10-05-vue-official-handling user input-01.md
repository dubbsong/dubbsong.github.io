---
layout: post
title: "VueJS 사용자 입력 핸들링하기 (button)"
categories: vue
---

###### [Vue.js 공식 문서](https://kr.vuejs.org/v2/guide/#%EC%82%AC%EC%9A%A9%EC%9E%90-%EC%9E%85%EB%A0%A5-%ED%95%B8%EB%93%A4%EB%A7%81) 참조

<br>

# VueJS Handling User Input

###### VueJS 사용자 입력 핸들링하기

<br>

- testVue.html

```html
<body>
   <div id="app">
      <p>{{ message }}</p>
      <button v-on:click="reverseMessage">
         메시지 뒤집기
      </button>
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
      message: '안녕! VueJS!'
   },
   methods: {
      reverseMessage: function() {
         this.message = this.message.spli('').reverse().join('');
      }
   }
});
```

<br>

- Result:

> `안녕! VueJS!`
>
> [메시지 뒤집기]

> [메시지 뒤집기] 버튼을 누르면 `!SJeuV !녕안`으로 변경된다.

<br>