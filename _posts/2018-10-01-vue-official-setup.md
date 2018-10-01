---
layout: post
title: "VueJS 설정하기"
categories: vue
---

###### [Vue.js 공식 문서](https://kr.vuejs.org/) 참조

<br>

# Setup VueJS

###### VueJS 설정하기

<br>

#### 디렉토리 생성

1. `terminal` 열기
2. `$ cd Desktop` (바탕화면으로 이동)
3. `$ mkdir testVue` (testVue 디렉토리 생성)

<br>

#### 파일 생성

1. `$ cd testVue` (testVue로 이동)
2. `$ touch testVue.html` (testVue.html 파일 생성)
3. `$ touch testVue.css` (testVue.css 파일 생성)
4. `$ touch testVue.js` (testVue.js 파일 생성)

<br>

#### HTML 파일 설정

- css, js 연결
- VueJS script 추가
  - `<script src="https://cdn.jsdelivr.net/npm/vue"></script>`

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
      
      
      <!-- script -->
      <script src="https://cdn.jsdelivr.net/npm/vue"></script>
      <script src="./testVue.js"></script>
   </body>
</html>
```

<br>