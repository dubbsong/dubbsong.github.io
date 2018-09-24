---
layout: post
title: "(Tutorial 03) props를 통한 데이터 전달"
categories: react
---

###### [React 공식 문서](https://reactjs.org/tutorial/tutorial.html#passing-data-through-props) 번역

<br>

# React: Passing Data Through Props

###### props를 통한 데이터 전달

<br>

- Just to get our feet wet, let's try passing some data from our Board component to our Square component.
  - Board 컴포넌트의 데이터를 Square 컴포넌트로 전달해보자.

<br>

- In Board's `renderSquare` method, change the code to pass a prop called `value` to the Square:
  - Board의 `renderSquare` 메소드에서 `value`라는 prop을 Square로 전달하도록 코드를 변경해라.

```react
class Board extends React.Component {
   renderSquare(i) {
      return <Square value={i} />;
   }
```

<br>

- Change Square's `render` method to show that value by replacing `{/* TODO */}` with `{this.props.value}`:
  - Square의 `render` 메소드를 변경해서 `{/* TODO */}`를 `{this.props.value}`로 대체하면 그 값이 보여진다.

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

![img](/assets/img/react-official-tutorial-03-01.png)

<br>

- After: You should see a number in each square in the rendered output.
  - 렌더링 된 결과의 각 사각형에 숫자가 보여진다.

![img](/assets/img/react-official-tutorial-03-02.png)

[코드 실행 확인](https://codepen.io/gaearon/pen/aWWQOG?editors=0010)

<br>

- You've just "passed a prop" from a parent Board component to a child Square component.
  - 부모 Board 컴포넌트에서 자식 Square 컴포넌트로 "prop을 전달"했다.
- Passing props is how information flows in React apps, from parents to children.
  - React app에서 props 전달은, 부모 컴포넌트로부터 자식 컴포넌트에게 정보가 흘러가는 방식이다.

------

<br>