---
layout: post
title: "러닝 리액트(Learning React) - 재귀"
categories: react
tags: react
---

###### \<Learning React>, Alex Banks, Eve Porcello 저 | 오현석 역

<br>

## CHAPTER 03 함수형 프로그래밍

<br>

### 재귀 (recursion)

- 재귀는 자기 자신을 호출하는 함수를 만드는 기법이다.
- 루프를 모두 재귀로 바꿀 수 있고, 일부 루프는 재귀로 표현하는 쪽이 더 쉽다.

<br>

- 10부터 0까지 거꾸로 세는 경우를 생각해보자.

```javascript
const countdown = (value, fn) => {
   fn(value)
   return (value > 0) ? countdown(value - 1, fn) : value
}

countdown(10, value => console.log(value));

// 10
// 9
// 8
// 7
// 6
// 5
// 4
// 3
// 2
// 1
// 0
```

<br>

- countdown은 수와 함수를 인자로 받는다.
- 이 예제에서는 10과 콜백 함수로 인자를 넘겼다.
- countdown이 호출되면 현재 값을 로그에 남기는 콜백이 호출된다.
- 그 후 countdown은 현재 값이 0보다 큰지 검사한다.
- 현재 값이 0보다 크면 countdown이 자기 자신을 호출하되 값을 1 감소시켜서 호출한다.
- 언젠가는 값이 0 이하가 되고, countdown이 그 값을 돌려주면 호출 스택을 거슬러 올라가면서 값이 전달된다.

<br>

- 재귀는 비동기 프로세스에서도 잘 작동하는 또 다른 함수형 기법이다.
- 함수는 필요할 때 자기 자신을 다시 호출할 수 있다.
- 데이터 구조를 검색할 때도 재귀가 유용하다.
- 어떤 폴더의 모든 하위 폴더를 뒤져가면서 파일 이름을 모두 추려내고 싶다면 재귀를 사용할 수 있다.
- 재귀 호출은 값을 반환할 때까지 반복된다.
- 재귀는 강력한 함수형 기법이며, 구현할 때도 재미있다.
- 가능하면 루프보다는 재귀를 사용하라.

<br>

