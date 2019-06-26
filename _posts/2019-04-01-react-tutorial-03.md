---
layout: post
title: "(공식 리액트 튜토리얼 03) props를 통해 데이터 전달하기"
categories: dev
tags: react
---

###### [공식 리액트 튜토리얼](https://reactjs.org/tutorial/tutorial.html#passing-data-through-props) 번역

<br>

#### Passing Data Through Props

###### props를 통해 데이터 전달하기

<br>

- To get our feet wet, let's try passing some data from our Board component to our Square component.
  - Board 컴포넌트에서 Square 컴포넌트로 일부 데이터를 전달해보자.

<br>

- We strongly recommend typing code by hand as you're working through the tutorial and not using copy/paste.
  - 복사/붙여넣기를 사용하지 않고, 코드를 직접 타이핑하는 게 좋다.
- This will help you develop muscle memory and a stronger understanding.
  - 이렇게 하면 개발 근육 기억과, 더 확실한 이해에 도움이 될 것이다.

<br>

- In Board's `renderSquare` method, change the code to pass a prop called `value` to the Square:
  - Board의 `renderSquare` 메소드에서, `value`라는 prop을 Square로 전달하도록 코드를 변경한다.

```react
class Board extends React.Component {
  renderSquare(i) {
    return <Square value={i} />;
  }
  ...
}
```

<br>

- Change Square's `render` method to show that value by replacing `{/* TODO */}` with `{this.props.value}`:
  - Square의 `render` 메소드를 변경하면, value가 표시된다.
  - `{/* TODO */}`를 `{this.props.value}`로 대체한다.

```react
class Square extends React.Component {
  render() {
    return (
      <button className="square">
        {this.props.value}
      </button>
    );
  }
}
```

[코드 실행 확인](https://codepen.io/gaearon/pen/aWWQOG?editors=0010)

<br>

- Before:

![img](/assets/img/react-tutorial-03-01.png)

<br>

- After:

![img](/assets/img/react-tutorial-03-02.png)

<br>

- You've just "passed a prop" from a parent Board component to a child Square component.
  - parent(부모, 상위) Board 컴포넌트에서 child(자식, 하위) Square 컴포넌트로 "prop을 전달했다".
- Passing props is how information flows in React apps, from parents to children.
  - React 앱에서 props 전달은, parent에서 children으로 정보가 흐르는 방법이다.

------

<br>

<br>
