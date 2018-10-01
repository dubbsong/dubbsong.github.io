---
layout: post
title: "VueJS Hello wolrd"
categories: vue
---

###### [Vue.js 공식 문서](https://jsfiddle.net/chrisvfritz/50wL7mdz/) 참조

<br>

# VueJS Hello world

- testVue.html

```html
<!DOCTYPE html>
<html lang="en">
   <head>
      <title>testVue</title>
      <meta charset="UTF-8">
      <meta http-equiv="X-UA-Compatible" content="ie=edge">
      <meta name="viewport" content="width=device-width, initial-scale=1.0">
      <link rel="stylesheet" href="./testVue.css">
   </head>
   
   <body>
      <!-- Vue.js -->
      <div id="app">
         <p>{{message}}</p>
      </div>
      
      <!-- script -->
      <script src="https://cdn.jsdelivr.net/npm/vue"></script>
      <script src="./testVue.js"></script>
   </body>
</html>
```

<br>

- testVue.js

```js
new Vue({
   el: '#app',
   data: {
      message: 'Hello VueJS!'
   }
});
```

<br>

- Result:

> `Hello VueJS!`

<br>