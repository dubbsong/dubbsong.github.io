---
layout: post
title: "(공식 리액트 튜토리얼) 07. 왜 불변성이 중요한가?"
categories: dev
tags: react
---

###### [공식 리액트 튜토리얼](https://reactjs.org/tutorial/tutorial.html#why-immutability-is-important) 번역

<br>

#### Why Immutability Is Important

###### 왜 불변성이 중요한가?

<br>

- In this previous code example, we suggested that you use the `.slice()` operator to create a copy of the `squares` array to modify instead of modifying the existing array.
  - 이전 코드 예제에서, 기존 배열을 수정하는 대신, `.slice()` 연산자를 사용해 `squares` 배열의 복사본을 생성하는 것을 추천했다.
- We'll now discuss immutability and why immutability is important to learn.
  - 이제 왜 불변성이 중요한지 논할 것이다.

<br>

- There are generally two approaches to changing data.
  - 데이터를 변경하는 데에는, 일반적으로 두 가지 접근법이 있다.
- The first approach is to *mutate* the data by directly changing the data's values.
  - 첫 번째 방법은, 데이터의 값을 직접 변경해서 데이터를 변화시키는 것이다.
- The second approach is to replace the data with a new copy which has the desired changes.
  - 두 번째 방법은, 데이터를 원하는 변화를 가진 새 복사본으로 대체하는 것이다.

<br>

###### Data Change with Mutation

###### 변형으로 데이터 변경하기

```js
var player = {
  score: 1,
  name: 'Sam'
};

player.score = 2;	// {score: 2, name: 'Sam'}
```

<br>

###### Data Change without Mutation

###### 변형 없이 데이터 변경하기

```js
var player = {
  score: 1,
  name: 'Sam'
};

var newPlayer = Object.assign({}, player, {score: 2});
// player는 변하지 않는다.
// newPlayer는 {score: 2, name: 'Sam'}
```

<br>

- The end result is the same but by not mutating (or changing the underlying data) directly, we gain several benefits described below.
  - 최종 결과는 동일하지만, 직접 변형하지 않으면 여러 이점을 얻는다.

<br>

###### Complex Features Become Simple

###### 복잡한 기능이 단순해진다

- Immutability makes complex features much easier to implement.
  - 불변성은, 복잡한 기능을 훨씬 쉽게 구현할 수 있게 한다.
- Later in this tutorial, we will implement a `time travel` feature that allows us to review the tic-tac-toe game's history and `jump back` to previous moves.
  - 튜토리얼 뒷부분에서는, tic-tac-toe 게임의 이력을 확인하고, 이전 동작으로 `다시 돌아가는 time travel` 기능을 구현한다.
- This functionality isn't specific to games - an ability to undo and redo certain actions is a common requirement in applications.
  - 이 기능들은 game과 관련이 없다.
  - undo와 redo는 애플리케이션의 공통 요구 사항이다.
- Avoiding direct data mutation lets us keep previous versions of the game's history intact, and reuse them later.
  - 직접적인 데이터 변형을 피함으로써, game의 이력을 그대로 유지할 수 있고, 나중에 재사용할 수도 있다.

<br>

###### Detecting Changes

###### 변화 탐지하기

- Detecting changes in mutable objects is difficult because they are modified directly.
  - 변경 가능한 객체에서는 직접 수정하므로, 변화를 탐지하는 것은 어렵다.
- This detection requires the mutable object to be compared to previous copies of itself and the entire object tree to be traversed.
  - 탐지는, 변경 가능한 객체가 이전 복사본과 비교되거나, 전체 객체 트리가 순회되는 것이 필요하다.

<br>

- Detecting changes in immutable objects is considerably easier.
  - 변경 불가능한 객체의 변화를 탐지하는 것은 상당히 쉽다.
- If the immutable object that is being referenced is different than the previous one, then the object has changed.
  - 참조되고 있는 변경 불가능한 객체가 이전과 다르다면, 객체는 변경된 것이다.

<br>

###### Determining When to Re-Render in React

###### 다시 렌더링 할 시기 결정하기

- The main benefit of immutability is that it helps you build *pure components* in React.
  - 불변성의 주요 이점으로는, 순수 컴포넌트를 빌드하는 데 도움이 된다.
- Immutable data can easily determine if changes have been made which helps to determine when a component requires re-rendering.
  - 변경 불가능한 데이터는 변화가 있는지를 쉽게 알 수 있다.
  - 컴포넌트가 다시 렌더링이 필요한 시기를 결정하는 데 도움이 된다.

<br>

- You can learn more about `shouldComponentUpdate()` and how you can build *pure components* by reading [Optimizing Performance](https://reactjs.org/docs/optimizing-performance.html#examples).
  - [성능 최적화](https://reactjs.org/docs/optimizing-performance.html#examples)를 읽음으로써, 순수 컴포넌트 빌드와 `shouldComponentUpdate()`에 대해 더 배울 수 있다.

------

<br>
