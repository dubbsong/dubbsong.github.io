###### [Vue.js](https://kr.vuejs.org/index.html) 참조

<br>

## computed 속성

- 복잡한 로직이라면 반드시 `computed 속성`을 사용해야 한다.

<br>

#### 기본 예제

```html
<div id="example">
  <p>원본 메시지: "{{ message }}"</p>
  <p>역순 메시지: "{{ reversedMessage }}"</p>
</div>
```

```js
var vm = new Vue({
  el: '#example',
  data: {
    message: 'How are you?'
  },
  computed: {
    reversedMessage: function() {
      // this는 vm 인스턴스를 가리킨다.
      return this.message.split('').reverse().join('')
    }
  }
})

// 원본 메시지: How are you?
// 역순 메시지: ?uoy era woH
```

<br>

#### computed 속성의 캐싱 vs. 메소드

- computed 속성은 종속 대상을 따라 저장(캐싱)된다.
- computed 속성은 해당 속성이 종속된 대상이 변경될 때에만 함수를 실행한다.

<br>

#### computed 속성 vs. 속성

- Vue 인스턴스의 데이터 변경을 관찰하고, 이에 반응하는 `watch 속성`을 제공한다.

<br>

###### 1. 명령형 프로그래밍 방식 (코드 반복)

```html
<div id="demo">
  {{ fullName }}
</div>
```

```js
var vm = new Vue({
  el: '#demo',
  data: {
    firstName: 'Foo',
    lastName: 'Bar',
    fullName: 'Foo Bar'
  },
  watch: {
    firstName: function(val) {
      this.fullName = val + ' ' + this.lastName
    },
    lastName: function(val) {
      this.fullName = this.firstName + ' ' + val
    }
  }
})
```

<br>

###### 2. 선언형 프로그래밍 방식 (computed 속성)

```js
var vm = new Vue({
  el: '#demo',
  data: {
    firstName: 'Foo',
    lastName: 'Bar'
  },
  computed: {
    fullName: function() {
      return this.firstName + ' ' + this.lastName
    }
  }
})
```

<br>

#### computed 속성의 setter 함수

- computed 속성은 기본적으로 getter 함수를 가지고 있지만, 필요한 경우 setter 함수를 만들어 사용할 수 있다.

```js
computed: {
  fullName: {
    // getter
    get: function() {
      return this.firstName + ' ' + this.lastName
    },
    set: function(newValue) {
      var names = newValue.split(' ')
      this.firstName = names[0]
      this.lastName = names[names.length - 1]
    }
  }
}
```

<br>

## watch 속성

- watch 속성은 데이터 변경에 대한 응답으로 비동기식 또는 시간이 많이 소요되는 조작을 수행하려는 경우에 가장 유용하다.

```html
<div id="watch-example">
  <p>
    yes/no 질문을 물어보세요:
    <input v-model="question">
  </p>
  <p>{{ answer }}</p>
</div>
```

```html
<html>
  <head>
    <script src="https://unpkg.com/axios@0.12.0/dist/axios.min.js"></script>
    <script src="https://unpkg.com/lodash@4.13.1/lodash.min.js"></script>
    <script>
      var watchExampleVM = new Vue({
        el: '#watch-example',
        data: {
          question: '',
          answer: '질문을 하기 전까지는 대답할 수 없습니다.'
        },
        watch: {
          // 질문이 변경될 때마다 이 기능이 실행된다.
          question: function(newQuestion) {
            this.answer = '입력을 기다리는 중...'
            this.getAnswer()
          }
        },
        methods: {
          getAnswer: _.debounce(
            function() {
              if (this.question.indexOf('?') === -1) {
                this.answer = '질문에는 일반적으로 물음표가 포함된다.'
                return
              }
              this.answer = '생각중...'
              var vm = this
              axios.get('https://yesno.wtf/api')
                .then(function(response) {
                  vm.answer = _.capitalize(response.data.answer)
                })
                .catch(function(error) {
                  vm.answer = '에러, API 요청에 오류가 있다. ' + error
                })
            },
            // 사용자가 입력을 기다리는 시간이다.
            500
          )
        }
      })
    </script>
  </head>
</html>
```

> input에 `All good?`을 입력하면, `입력을 기다리는 중...` 후에 `Yes` 또는 `No`가 표시된다.

<br>

<br>