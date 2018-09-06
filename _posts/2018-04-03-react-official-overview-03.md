---
layout: post
title: "리액트 공식 문서 번역 - 03. props를 통해 데이터 전달하기 (Overview)"
categories: react
---

###### [React 공식 문서 번역](https://reactjs.org/tutorial/tutorial.html#passing-data-through-props)

<br>

# React: Passing Data Through Props

###### props를 통해 데이터 전달하기

<br>

- Just to get our feet wet, let's try passing some data from our Board component to our Square component.
  - Board 컴포넌트의 데이터를 Square 컴포넌트로 전달해보자.

<br>

- In Board's `renderSquare` method, change the code to pass a prop called `value` to the Square:
  - Board의 `renderSquare` 메소드에서, `value`라는 prop을 `Square`로 전달하도록 변경해라.

```react
class Board extends React.Component {
   renderSquare(i) {
      return <Square value={i} />;
   }
```

<br>

- Change Square's `render` method to show that value by replacing `{/* TODO */}` with `{this.props.value}`:
  - Square의 `render` 메소드를 변경해서 `{/* TODO */}`를 `{this.props.value}`로 대체하면, 그 값이 표시된다.

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

<br>

- Before:

![react img](/assets/img/react-official-overview-03-01.png)

<br>

- After: You should see a number in each square in the rendered output.
  - 렌더링 된 출력에서 각 사각형에 숫자가 표시되어야 한다.

![react img](/assets/img/react-official-overview-03-02.png)

[코드 실행 확인 링크](https://codepen.io/gaearon/pen/aWWQOG?editors=0010)

<br>

- You've just "passed a prop" from a parent Board component to a child Square component.
  - 부모 Board 컴포넌트에서 자식 Square 컴포넌트로 "prop을 전달했다".
- Passing props is how information flows in React apps, from parents to children.
  - React 애플리케이션에서 props 전달은, 부모로부터 자식에게 정보가 흘러가는 방식이다.

------

<br>