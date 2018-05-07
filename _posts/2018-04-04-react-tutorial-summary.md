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

#### create-react-app 설치

- `$ npm install -g create-react-app`

<br>

#### create-react-app 프로젝트 생성

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
import React from 'react';
import ReactDOM from 'react-dom';
import './index.css';

class Square extends React.Component {
  render() {
    return (
      <button className="square">
        {this.props.value}
      </button>
    )
  }
}

class Board extends React.Component {
  renderSquare(i) {
    return <Square value={i} />;
  }
   
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
import React from 'react';
import ReactDOM from 'react-dom';
import './index.css';

class Square extends React.Component {  
  render() {
    return (
      <button className="square" onClick={() => alert('click')}>
        {this.props.value}
      </button>
    )
  }
}

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
- subclass의 생성자를 정의할 때는 명시적으로 `super();`를 호출해야 한다.
- 사각형이 클릭되었을 때 변경해보자.
- 클래스에 생성자를 추가해서 state를 초기화한다.
- **index.js**

```react
import React from 'react';
import ReactDOM from 'react-dom';
import './index.css';

class Square extends React.Component {
  constructor(props) {
    super(props);
    this.state = {
      value: null,
    };
  }
  
  render() {
    return (
      <button className="square" onClick={() => alert('click')}>
        {this.props.value}
      </button>
    )
  }
}

...
```

<br>

#### 클릭 시 전환

- **index.js**

```react
import React from 'react';
import ReactDOM from 'react-dom';
import './index.css';

class Square extends React.Component {
  constructor(props) {
    super(props);
    this.state = {
      value: null,
    };
  }
  
  render() {
    return (
      <button className="square" onClick={() => this.setState({value: 'X'})}>
        {this.state.value}
      </button>
    )
  }
}
```

<br>

- `this.setState`가 호출될 때마다, 컴포넌트에 대한 업데이트가 예정되어 있으므로, 전달된 state 업데이트에서 React가 병합되고, 컴포넌트가 하위 컴포넌트와 함께 다시 렌더링된다.
- 컴포넌트가 다시 렌더링되면, `this.state.value`는 `'X'`가 되어 격자에 X가 표시된다.
- 사각형을 클릭하면, 그 안에 X가 나타난다.

<br>

#### state 끌어올리기

- 여러 자식 컴포넌트로부터 데이터를 모으거나 두 자식 컴포넌트가 서로 커뮤니케이션하기를 원한다면, state를 부모 컴포넌트로 이동시켜라.
- 부모 컴포넌트는 props를 통해 자식 컴포넌트로 state를 전달할 수 있으므로, 자식 컴포넌트는 항상 자식 컴포넌트나 부모 컴포넌트와 동기화할 수 있다.
- state를 위로 끌어올리는 것은 React 컴포넌트를 리팩토링 할 때 일반적으로 사용하는 방법이다.
- Borad에 생성자를 추가하고, 9개의 사각형과 일치하는 9개의 null을 가진 배열을 포함하도록 state를 초기화해라.
- **index.js**

```react
class Board extends React.Component {
  constructor(props) {
    super(props);
    this.state = {
      squares: Array(9).fill(null),
    };
  }

  renderSquare(i) {
    return <Square value={this.state.squares[i]} />;
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

#### 클릭 시 호출되는 함수를 Board에서 Square로 전달

- **index.js**

```react
class Board extends React.Component {
  constructor(props) {
    super(props);
    this.state = {
      squares: Array(9).fill(null),
    };
  }

  renderSquare(i) {
    return (
      <Square
        value={this.state.squares[i]}
        onClick={() => this.handleClick(i)}
      />
    );
  }
```

<br>

- 가독성을 위해 반환된 element를 여러 줄로 나누었다.

<br>

#### Board에서 Square로 두 개의 props 전달

- **index.js**

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

- 더 이상 state가 없으므로 Square에서 정의한 `constructor`를 삭제했다.
- 이제 사각형이 클릭될 때, Board에서 전달된 `onClick` 함수가 호출된다.

<br>

1. 내장된 DOM `<button>` 컴포넌트의 `onClick` prop은 React에게 클릭 이벤트 리스너를 설정하도록 지시한다.
2. 버튼을 클릭하면, React는 Square의 `render()` 메소드에 정의된 `onClick` 이벤트 핸들러를 호출한다.
3. 이 이벤트 핸들러는 `this.props.onClick()`을 호출한다. Square의 props는 Board에 의해 명시되었다.
4. Board는 `onClick={() => this.handleClick(i)}`을 Square에 전달했으므로, 호출될 때, Board에서 `this.handleClick(i)`을 실행한다.
5. 아직 Board에서 `handleClick()` 메소드를 정의하지 않았으므로, 코드가 깨진다.

<br>

#### handleClick 추가

- **index.js**

```react
class Board extends React.Component {
  constructor(props) {
    super(props);
    this.state = {
      squares: Array(9).fill(null),
    };
  }

  handleClick(i) {
    const squares = this.state.squares.slice();
    squares[i] = 'X';
    this.setState({squares: squares});
  }

  renderSquare(i) {
    return (
      <Square
        value={this.state.squares[i]}
        onClick={() => this.handleClick(i)}
      />
    );
  }
```

<br>

- 기존 배열을 변경하는 대신 `.slice()`를 호출해서 `squares` 배열을 복사한다.
- Board의 state가 바뀔 때마다, Square 컴포넌트는 자동으로 다시 렌더링된다.
- Square는 더 이상 자체 state를 유지하지 않는다.
- 그것은 부모 Board로부터 그 값을 받고, 그것을 클릭했을 때 그 부모에게 알린다.

<br>

#### 함수 컴포넌트

- React는 `render` 메소드로만 구성되는 컴포넌트 타입을 위해 **함수 컴포넌트**라는 더 간단한 문법을 지원한다.
- **index.js**

```react
function Square(props) {
  return (
    <button className="square" onClick={props.onClick}>
      {props.value}
    </button>
  );
}
```

<br>

- `this.props`를 `props`로 변경해야 한다.
- 함수 컴포넌트는 더 쉽게 작성될 수 있고, React는 더 최적화 될 것이다.

<br>

#### 첫 번째 이동이 'X'가 되도록 + 토글

- 아직까지는 오직 X만 플레이 할 수 있다. 수정해보자.
- **index.js**

```react
class Board extends React.Component {
  constructor(props) {
    super(props);
    this.state = {
      squares: Array(9).fill(null),
      xIsNext: true,
    };
  }

  handleClick(i) {
    const squares = this.state.squares.slice();
    squares[i] = this.state.xIsNext ? 'X' : 'O';
    this.setState({
      squares: squares,
      xIsNext: !this.state.xIsNext,
    });
  }
```

<br>

- 이동할 때마다 불린 값을 뒤집고 state를 저장해서 `xIsNext`를 토글한다.
- `handleClick` 함수를 `xIsNext` 값이 바뀔 수 있도록 업데이트한다.
- 이제 X와 O가 교대로 나타난다.

<br>

#### 누가 다음인지 표시

- **index.js**

```react
render() {
    const status = 'Next player: ' + (this.state.xIsNext ? 'X' : 'O');

    return (
       // the rest has not changed
```

<br>

#### 승자 선언

- 헬퍼 함수 추가
- **index.js**

```react
function calculateWinner(squares) {
  const lines = [
    [0, 1, 2],
    [3, 4, 5],
    [6, 7, 8],
    [0, 3, 6],
    [1, 4, 7],
    [2, 5, 8],
    [0, 4, 8],
    [2, 4, 6],
  ];
  for (let i = 0; i < lines.length; i++) {
    const [a, b, c] = lines[i];
    if (squares[a] && squares[a] === squares[b] && squares[a] === squares[c]) {
      return squares[a];
    }
  }
  return null;
}
// ========================================

ReactDOM.render(<Game />, document.getElementById('root'));
```

<br>

- Board의 `render` 함수에서 누가 이겼는지 확인할 수 있도록 호출

```react
render() {
    const winner = calculateWinner(this.state.squares);
    let status;
    if (winner) {
      status = 'Winner: ' + winner;
    } else {
      status = 'Next player: ' + (this.state.xIsNext ? 'X' : 'O');
    }

    return (
       // the rest has not changed
```

<br>

- 이제 승자가 누구인지 확인이 가능하다.

<br>

#### 이미 채워져 있는 경우 클릭 무시

- **index.js**

```react
  handleClick(i) {
    const squares = this.state.squares.slice();
    if (calculateWinner(squares) || squares[i]) {
      return;
    }
    squares[i] = this.state.xIsNext ? 'X' : 'O';
    this.setState({
      squares: squares,
      xIsNext: !this.state.xIsNext,
    });
  }
```

<br>

- 이제 작동하는 틱택토 게임이 완성됐다.

<br>

