---
layout: post
title: "리액트 공식 문서 번역 - 02. starter 코드 확인하기 (Overview)"
categories: react
---

###### [React 공식 문서 번역](https://reactjs.org/tutorial/tutorial.html#inspecting-the-starter-code)

<br>

# Inspecting the Starter Code

###### starter 코드 확인하기

<br>

- If you're going to work on the tutorial `in your browser`, open this code in a new tab: [Starter Code](https://codepen.io/gaearon/pen/oWWQNa?editors=0010).
  - 튜토리얼을 `브라우저에서` 작성하려면, [이 코드](https://codepen.io/gaearon/pen/oWWQNa?editors=0010)를 새 탭에서 열어라.
- If you're going to work on the tutorial `locally`, instead open `src/index.js` in your project folder (you have already touched this file during the [setup](https://reactjs.org/tutorial/tutorial.html#setup-option-2-local-development-environment)).
  - 튜토리얼을 `로컬에서` 작성하려면, 프로젝트 폴더에서 `src/index.js`를 열어라.

<br>

```react
class Square extends React.Component {
   render() {
      return (
      	<button className="square">
         	{/* TODO */}
         </button>
      );
   }
}

class Board extends React.Component {
   renderSquare(i) {
      return <Square />;
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

class Game extends React.Component {
   render() {
      return (
      	<div className="game">
         	<div className="game-board">
            	<Board />
            </div>
            <div className="game-info">
            	<div>{/* status */}</div>
               <ol>{/* TODO */}</ol>
            </div>
         </div>
      );
   }
}

// =======================================

ReactDOM.render(
	<Game />,
   document.getElementById('root')
);
```

<br>

- This Starter Code is the base of what we're building.
  - 이 starter 코드는 우리가 만들고자 하는 것의 기반이다.
- We've provided the CSS styling so that you only need focus on learning React and programming the tic-tac-toe game.
  - React를 배우고, tic-tac-toe 게임을 프로그래밍하는 데에만 집중할 수 있도록 CSS 스타일을 제공했다.

<br>

- By inspecting the code, you'll notice that we have three React components:
  - 코드를 확인해보면, 세 가지 React 컴포넌트가 있음을 알 수 있다.

<br>

> - Square
> - Board
> - Game

<br>

- The Square component renders a single `<button>` and the Board renders 9 squares.
  - Square 컴포넌트는 하나의 `<button>`을 렌더링 하고, Board는 9개의 사각형을 렌더링 한다.
- The Game component renders a board with placeholder values which we'll modify later.
  - Game 컴포넌트는 board의 placeholder 값을 렌더링 하고, 이를 나중에 수정할 것이다.
- There are currently no interactive components.
  - 현재 대화형 컴포넌트가 없다.

------

<br>