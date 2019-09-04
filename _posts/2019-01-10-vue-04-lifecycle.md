---
layout: post
title: "(Official VueJS 04) 라이프사이클"
categories: dev
tags: vue
---

###### [Vue.js](https://kr.vuejs.org/index.html) 참조

<br>

## 인스턴스 라이프사이클 훅

- `created` 훅은 인스턴스가 생성된 후에 호출된다.

```js
new Vue({
  data: {
    a: 1
  },
  created: function() {
    // this는 vm 인스턴스를 가리킨다.
    console.log('a is: ' + this.a)
  }
})

// a is 1
```

<br>

## 라이프사이클 다이어그램

![img](/assets/img/vue_lifecycle_diagram.png)

<br>

<br>