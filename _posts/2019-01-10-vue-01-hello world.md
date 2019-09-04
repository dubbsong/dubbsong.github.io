###### [Vue.js](https://kr.vuejs.org/index.html) 참조

<br>

## 디렉토리 생성

```bash
$ cd Desktop
$ mkdir test_vue
```

<br>

## 파일 생성

```bash
$ cd test_vue
$ touch test_vue.html
```

<br>

## 코드 작성

- test_vue.html

```html
<!DOCTYPE html>
<html>
  <head>
    <title>Hello VueJS</title>
  </head>
  <body>
    <div id="app">
      {{ message }}
    </div>
    
    <!-- Scripts -->
    <script src="https://cdn.jsdelivr.net/npm/vue"></script>
    <script>
      var app = new Vue({
        el: '#app',
        data: {
          message: 'Hello VueJS'
        }
      })
    </script>
  </body>
</html>
```

> 화면에 `Hello VueJS`가 표시된다.

<br>

<br>