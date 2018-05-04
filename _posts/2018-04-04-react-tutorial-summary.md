---
layout: post
title: "리액트 공식 문서 요약"
categories: react
tags: React Tutorial
---

## React Tutorial

<br>

#### 무엇을 만들 것인가?

- React로 틱택토 게임 구현
- 최종 결과물 확인: [링크](https://codepen.io/gaearon/pen/gWWZgR?editors=0010)

<br>

#### 틱택토란?

- 오목과 아주 유사한 형태인 추상전략 보드게임이다. (삼목)
- 보드는 3 x 3의 정사각형이며, 2인 전용 게임이다.
- 가로 세로 대각선으로 3개가 이어지면 이긴다.
- 구글 틱택토 게임: [플레이](https://www.google.co.kr/search?q=%ED%8B%B1%ED%83%9D%ED%86%A0+%EA%B2%8C%EC%9E%84&oq=%ED%8B%B1%ED%83%9D%ED%86%A0+%EA%B2%8C%EC%9E%84&aqs=chrome..69i57j0l5.1829j0j1&sourceid=chrome&ie=UTF-8)

<br>

#### 3가지 컴포넌트 구현

> Square: \<button>을 렌더링한다.
>
> Board: 9개의 사각형을 렌더링한다.
>
> Game: 나중에 채워야 할 placeholder가 있는 보드를 렌더링한다.

<br>

#### React란?

- React는 유저 인터페이스 빌드를 위한 선언적이고, 효율적이며, 유연한 JavaScript 라이브러리이다.
- 작성한 컴포넌트는 렌더링하고 싶은 것을 React에게 알려준다.
- React는 데이터가 변경될 때 컴포넌트를 효율적으로 업데이트하고 렌더링한다.
- 컴포넌트는 `props`라 불리는 매개변수를 가져오고, `render` 메소드를 통해 나타낼 계층 구조를 반환하고, React가 그 계층 구조를 화면에 렌더링한다.
- 대부분의 React 개발자들은 `JSX`라는 문법을 사용해서 이러한 구조를 더 쉽게 작성한다.
- JavaScript 표현식을 JSX 내부 중괄호 안에 넣을 수 있다.
- 각 컴포넌트는 독립적으로 작동할 수 있도록 캡슐화되어 있다.
- 이러한 간단한 컴포넌트들로 복잡한 UI를 빌드할 수 있다.

<br>

#### create-react-app

1. open **terminal**
2. `$ cd Desktop`
3. `$ create-react-app tic_tac_toe`
4. `$ cd tic_tac_toe`
5. `$ yarn start` (`localhost:3000`에서 정상 작동 확인)
6. `$ code .` (VS Code 실행)

<br>

#### 쓸모없는 파일 및 내용 삭제

- `/tic_tac_toe $ rm -f src/*` (`src` 내부에 있는 파일 모두 삭제)

<br>

#### 파일 생성

- `$ cd src`
- `$ touch index.css` (`src`에서 **index.css** 파일 생성)
- `$ touch index.js` (`src`에서 **index.js** 파일 생성)

<br>

#### 코드 작성

- **index.css**

```css
body {
  font: 14px "Century Gothic", Futura, sans-serif;
  margin: 20px;
}

ol, ul {
  padding-left: 30px;
}

.board-row:after {
  clear: both;
  content: "";
  display: table;
}

.status {
  margin-bottom: 10px;
}

.square {
  background: #fff;
  border: 1px solid #999;
  float: left;
  font-size: 24px;
  font-weight: bold;
  line-height: 34px;
  height: 34px;
  margin-right: -1px;
  margin-top: -1px;
  padding: 0;
  text-align: center;
  width: 34px;
}

.square:focus {
  outline: none;
}

.kbd-navigation .square:focus {
  background: #ddd;
}

.game {
  display: flex;
  flex-direction: row;
}

.game-info {
  margin-left: 20px;
}
```

<br>

- **index.js**

```react
import React from 'react';
import ReactDOM from 'react-dom';
import './index.css';

class Square extends React.Component {
  render() {
    return <button className="square">{/* TODO */}</button>;
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

// ========================================

ReactDOM.render(<Game />, document.getElementById('root'));
```

<br>

- 9개의 사각형 보드가 나타난다.

![Board](/assets/img/Before.png)

<br>

#### props를 통한 데이터 전달

- Board 컴포넌트에서 Square 컴포넌트로 `value` prop을 전달한다.
- **index.js**

```react
// import React from 'react';
// import ReactDOM from 'react-dom';
// import './index.css';

// class Square extends React.Component {
//   render() {
//     return (
	<button className="square">
		{this.props.value}
	</button>
//     )
//   }
// }

// class Board extends React.Component {
//   renderSquare(i) {
	return <Square value={i} />;
//   }

...
```

<br>

- 각 사각형 안에 숫자가 출력된다.

![Board](/assets/img/After.png)

<br>

#### 대화형 컴포넌트

- 클릭 시 **X**로 채워지는 Square 컴포넌트를 만들자.
- **index.js**

```react
// import React from 'react';
// import ReactDOM from 'react-dom';
// import './index.css';

// class Square extends React.Component {
//   render() {
//     return (
			<button className="square" onClick={() => alert('click')}>
				{this.props.value}
			</button>
//     )
//   }
// }

...
```

> `onClick`: 함수를 전달한다.
>
> `onClick={alert('click')}`: 버튼을 클릭하면 즉시 알림이 표시된다.

<br>

- 이제 사각형을 클릭하면, 브라우저에 알림이 표시된다.

![Alert](/assets/img/Alert.png)

<br>

#### state 초기화

- React 컴포넌트는 생성자에서 `this.state`를 설정함으로써 state를 가질 수 있다.
- 사각형이 클릭되었을 때 변경해보자.
- 클래스에 생성자를 추가해서 state를 초기화한다.
- **index.js**

```react
// import React from 'react';
// import ReactDOM from 'react-dom';
// import './index.css';

// class Square extends React.Component {
		constructor(props) {
   		super(props);
   		this.state = {
				value: null,
			};
		}

//   render() {
//     return (
//       <button className="square" onClick={() => alert('click')}>
//         {this.props.value}
//       </button>
//     )
//   }
// }

...
```





























