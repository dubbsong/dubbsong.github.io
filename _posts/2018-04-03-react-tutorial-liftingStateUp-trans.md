---
layout: post
title: "리액트 공식 문서 번역 - Lifting State Up"
categories: react
tags: react tutorial
---

[React 공식 문서 링크](https://reactjs.org/tutorial/tutorial.html)

<br>

## Lifting State Up

###### State 끌어올리기

<br>

- We now have the basic building blocks for a tic-tac-toe game.
  - 이제 틱택토 게임을 위한 기본 빌딩 블럭을 가지고 있다.
- But right now, the state is encapsulated in each Square component.
  - 하지만 지금은, 각 Square 컴포넌트에 state가 캡슐화되어 있다.
- To make a fully-working game, we now need to check if one player has won the game,
  - 제대로 작동하는 게임을 만들기 위해서는, 이제 한 플레이어가 게임에서 이겼는지 확인해야 하고,
- and alternate placing X and O in the squares.
  - 사각형들 안에 X와 O를 번갈아 놓아야 한다.
- To check if someone has won,
  - 누가 게임에서 이겼는지 확인하기 위해서는,
- we'll need to have the value of all 9 squares in one place,
  - 한 곳에서 9개 사각형의 값을 모두 가지고 있어야 한다.


- rather than split up across the Square components.
  - Square 컴포넌트를 쪼개지 않고.

<br>

- You might think that Board should just inquire what the current state of each Square is.
  - 당신은 Board가 각 Square의 현재 state가 무엇인지 확인해야 한다고 생각할 수도 있다.
- Although it is technically possible to do this in React,
  - React에서 기술적으로 가능은 하지만,
- it is discouraged because it tends to make code difficult to understand, more brittle, and harder to refactor.
  - 그것은 코드를 이해하기 어렵고, 불안정하고, 리팩토링하기 힘들게 만든다.

<br>

- Instead, the best solution here is to store this state in the Board component instead of in each Square -
  - 가장 좋은 해결책은 각 Square가 아닌 Board 컴포넌트에 이 state를 저장하는 것이다.
- and the Board component can tell each Square what to display, like how we made each square display its index earlier.
  - 그리고 Board 컴포넌트는 각 Square에 표시할 것을 알려줄 수 있다.

<br>

- When you want to aggregate data from multiple children or to have two child components communicate with each other,
  - 여러 자식 컴포넌트로부터 데이터를 모으거나 두 자식 컴포넌트가 서로 커뮤니케이션하기를 원한다면,
- move the state upwards so that it lives in the parent component.
  - state를 부모 컴포넌트로 이동시켜라.
- **The parent can then pass the state back down to the children via props,**
  - **그러면 부모 컴포넌트는 props를 통해 자식 컴포넌트로 state를 전달할 수 있으므로,**
- **so that the child components are always in sync with each other and with the parent.**
  - **자식 컴포넌트는 항상 자식 컴포넌트나 부모 컴포넌트와 동기화할 수 있다.**

<br>

- Pulling state upwards like this is common when refactoring React components,
  - state를 위로 당기는 것은 React 컴포넌트를 리팩토링 할 때 일반적으로 사용하는 방법이다.
- so let's take this opportunity to try it out.
  - 이 기회에 시도해보자.
- Add a constructor to the Board and set its initial state to contain an array with 9 nulls, corresponding to the 9 squares:
  - Board에 생성자를 추가하고, 9개 사각형과 일치하는 9개의 null을 가진 배열을 포함하도록 state를 초기화해라.

```react
class Board extends React.Component {
   constructor(props) {
      super(props);
      this.state = {
         squares: Array(9).fill(null),
      };
   }
   
   renderSquare(i) {
      return <Square value={i} />;
   }
   
   render() {
      const status = 'Next player: X';
      
      return (
         <div>
	      	<div className="status">{status}</div>
            <div className="board-row">
            	{this.renderSquare(0)}
               {this.renderSquare(1)}
               {this.renderSquare(2)}
            </div>
            <div className="board-row">
            	{this.renderSquare(3)}
               {this.renderSquare(4)}
               {this.renderSquare(5)}
            </div>
            <div className="board-row">
            	{this.renderSquare(6)}
               {this.renderSquare(7)}
               {this.renderSquare(8)}
            </div>
			</div>
      );
   }
}
```

<br>

- We'll fill in later so that a board looks something like

```react
[
   'O', null, 'X',
   'X', 'X', 'O',
   'O', null, null,
]
```

<br>

- Board's `renderSquare` method currently looks like this:
  - Board의 `renderSquare` 메소드는 현재 다음과 같다.

```react
renderSquare(i) {
   return <Square value={i} />;
}
```

<br>

- Modify it to pass a `value` prop to Square.
  - Square에 `value` prop을 전달하도록 수정해라.

```react
renderSquare(i) {
   return <Square value={this.state.squares[i]} />;
}
```

<br>

[현재 코드 확인 링크](https://codepen.io/gaearon/pen/gWWQPY?editors=0010)

<br>

- Now we need to change what happens when a square is clicked.
  - 이제 사각형을 클랙했을 때 발생할 변경이 필요하다.
- The Board component now stores which squares are filled,
  - Board 컴포넌트는 이제 어떤 사각형이 채워지는지를 저장하고 있다.
- which means we need some way for Square to update the state of Board.
  - 이는 Square가 Board의 state를 업데이트 할 수 있는 방법이 필요하다는 것을 의미한다.
- Since component state is considered private, we can't update Board's state directly from Square.
  - 컴포넌트 state는 비공개로 간주되므로, Square에서 Board의 state를 직접적으로 업데이트 할 수 없다.

<br>

- The usual pattern here is pass down a function from Board to Square that gets called when the square is clicked.
  - 일반적인 패턴은 사각형이 클릭되었을 때 호출되는 함수를 Board에서 Square로 전달하는 것이다.
- Change `renderSquare` in Board again so that it reads:
  - Board에서 `renderSquare`를 다시 변경해라.

```react
renderSquare(i) {
   return (
   	<Square
         value={this.state.squares[i]}
         onClick={() => this.handleClick(i)}
		/>
   );
}
```

- We split the returned element into multiple lines for readability,
  - 가독성을 위해 반환된 element를 여러 줄로 나누었다.
- and added parentheses around it so that JavaScript doesn't insert a semicolon after `return` and break our code.
  - 그리고 JavaScript가 `return` 후 세미콜론을 삽입하고 코드를 중단하지 않도록 괄호를 추가한다.

<br>

- Now we're passing down two props from Board to Square: `value` and `onClick`.
  - 이제 Board에서 Square로 두 개의 props를 전달할 것이다: `value`와 `onClick`을.
- The latter is a function that Square can call.
  - 후자는 Square에서 호출할 수 있는 함수이다.
- Let's make the following changes to Square:
  - Square에서 다음과 같이 변경해보자.

<br>

1. Replace `this.state.value` with `this.props.value` in Square's `render`.
   - Square의 `render`에서 `this.state.value`를 `this.props.value`로 대체해라.
2. Replace `this.setState()` with `this.props.onClick()` in Square's `render`.
   - Square의 `render`에서 `this.setState()`를 `this.props.onClick()`으로 대체해라.
3. Delete `constructor` definition from Square because it doesn't have state anymore.
   - 더 이상 state가 없으므로 Square에서 정의한 `constructor`를 삭제해라.

<br>

- After these changes, the whole Square component looks like this:
  - 이러한 변경 후에, 모든 Square 컴포넌트는 다음과 같다.

```react
class Square extends React.Component {
   render() {
      return (
      	<button className="square" onClick={() => this.props.onClick()}>
         	{this.props.value}
         </button>
      );
   }
}
```

<br>

- Now when the square is clicked, it calls the `onClick` function that was passed by Board.
  - 이제 사각형이 클릭될 때, Board에서 전달된 `onClick` 함수가 호출된다.
- Let's recap what happens here:
  - 어떤 일이 일어나는지 요약해보자.

<br>

1. The `onClick` prop on the built-in DOM `<button>` component tells React to set up a click event listener.
   - 내장된 DOM `<button>` 컴포넌트의 `onClick` prop은 React에게 클릭 이벤트 리스너를 설정하도록 지시한다.



































