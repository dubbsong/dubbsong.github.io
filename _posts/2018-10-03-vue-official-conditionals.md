---
layout: post
title: "VueJS 조건문"
categories: vue
---

###### [Vue.js 공식 문서](https://kr.vuejs.org/v2/guide/#%EC%A1%B0%EA%B1%B4%EB%AC%B8%EA%B3%BC-%EB%B0%98%EB%B3%B5%EB%AC%B8) 참조

<br>

# VueJS Conditionals

###### VueJS 조건문

<br>

- testVue.html

```html
<body>
   <div id="app">
      <p v-if="seen">You can see me </p>
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
      seen: true
   }
});
```

<br>

- Result:

> `You can see me`

<br>

#### 추가 조작 (화면에서 제거)

- `cmd` + `opt` + `J` (Chrome 개발자 도구 열기)
- Console

```js
app.seen = false;
```

<br>

- Result:

> 화면의 `You can see me`가 제거된다.

<br>