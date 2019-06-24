---
layout: post
title: "(공식 리액트 튜토리얼) 02. 시작 코드 살펴보기"
categories: dev
tags: react
---

###### [공식 리액트 튜토리얼](https://reactjs.org/tutorial/tutorial.html#inspecting-the-starter-code) 번역

<br>

#### Inspecting the Starter Code

###### 시작 코드 살펴보기

<br>

- If you're going to work on the tutorial `in your browser`, open this code in a new tab: [Starter Code](https://codepen.io/gaearon/pen/oWWQNa?editors=0010).
  - `브라우저에서` 튜토리얼을 작업하려면, 새 탭에서 [시작 코드](https://codepen.io/gaearon/pen/oWWQNa?editors=0010)를 열어라.
- If you're going to work on the tutorial `locally`, instead open `src/index.js` in your project folder.
  - `로컬에서` 튜토리얼을 작업하려면, 프로젝트 폴더의 `src/index.js`를 열어라.

<br>

- 시작 코드

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

ReactDOM.render(
  <Game />,
  document.getElementById('root')
);
```

<br>

- This Starter Code is the base of what we're building.
  - 이 시작 코드는, 빌드할 것에 대한 base이다.
- We've provided the CSS styling so that you only need to focus on learning React and programming the tic-tac-toe game.
  - CSS style을 제공했으므로, React 학습과 tic-tac-toe 게임 프로그래밍에만 집중해야 한다.

<br>

- By inspecting the code, you'll notice that we have three React components:
  - 코드를 살펴보면, 세 가지 React 컴포넌트가 있음을 알 수 있다.

<br>

1. `Square`
2. `Board`
3. `Game`

<br>

- The Square component renders a single `<button>` and the Board renders 9 squares.
  - Square 컴포넌트는 `<button>`을 렌더링 한다.
  - Board 컴포넌트는 9개의 사각형을 렌더링 한다.
- The Game component renders a board with placeholder values which we'll modify later.
  - Game 컴포넌트는 Board와 placeholder 값을 렌더링 한다.
  - 이는 나중에 수정할 것이다.

------

<br>