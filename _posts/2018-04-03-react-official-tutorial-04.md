---
layout: post
title: "리액트 공식 문서 번역 - 04. Storing a History (tutorial)"
categories: react
tags: react tutorial
---

[React 공식 문서 링크](https://reactjs.org/tutorial/tutorial.html)

<br>

## Storing a History

###### 히스토리 저장

<br>

- Let's make it possible to revisit old states of the board so we can see what it looked like after any of the previous moves.
  - 보드의 이전 state로 되돌려서 이전 이동 이후의 모습을 볼 수 있게 하자.
- We're already creating a new `squares` array each time a move is made,
  - 이동할 때마다, 이미 새로운 `squares` 배열을 만들고 있다.
- which means we can easily store the past board states simultaneously.
  - 이는 동시에 이전 보드 state를 쉽게 저장할 수 있음을 의미한다.

<br>

- Let's plan to store an object like this in state:
  - state에 다음과 같은 객체를 저장해보자.

```react
history = [
   {
      squares: [
         null, null, null,
         null, null, null,
         null, null, null,
      ]
   },
   {
      squares: [
         null, null, null,
         null, 'X', null,
         null, null, null,
      ]
   },
   // ...
]
```

<br>

- We'll want the top-level Game component to be responsible for displaying the list of moves.
  - 최상위 레벨의 Game 컴포넌트가 이동 목록을 표시하길 원한다.
- So just as we pulled the state up before from Square into Board,
  - 그래서 이전에 Square에서 Board로 state를 당긴 것처럼
- let's now pull it up again from Board into Game -
  - 이제 Board에서 Game으로 다시 당겨보자.
- so that we have all the information we need at the top level.
  - 그래서 우리가 필요한 모든 정보를 최상위 레벨에 가지고 있다.

<br>

- First, set up the initial state for Game by adding a constructor to it:
  - 우선, 생성자를 추가해서 Game의 초기 state를 설정한다.

```react
class Game extends React.Component {
   constructor(props) {
      super(props);
      this.state = {
         history: [{
            squares: Array(9).fill(null),
         }],
         xIsNext: true,
      };
   }
   
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
```

<br>

- Then change Board so that it takes `squares` via props and has its own `onClick` prop specified by Game,
  - 그런 다음, Board를 변경해서 props를 통해 `squares`를 가져오고, Game에서 지정한 자체 `onClick` prop을 갖는다.
- like the transformation we made for Square earlier.
  - 이전에 Square에서 했던 변형과 같이
- You can pass the location of each square into the click handler
  - 각 사각형의 위치를 클릭 핸들러에 전달해서
- so that we still know which square was clicked.
  - 어떤 사각형이 클릭되었는지 알 수 있다.
- Here is a list of steps you need to do:
  - 수행해야 할 단계 목록은 다음과 같다.

<br>

- Delete the `constructor` in Board.
  - Board에서 `constructor`를 삭제해라.
- Replace `this.state.squares[i]` with `this.props.square[i]` in Board's `renderSquare`.
  - Board의 `renderSquare`에서 `this.state.squares[i]`를 `this.props.square[i]`로 대체해라.
- Replace `this.handleClick(i)` with `this.props.onClick(i)` in Board's `renderSquare`.
  - Board의 `renderSquare`에서 `this.handleClick(i)`를 `this.props.onClick(i)`로 대체해라.

<br>

- Now the whole Board component looks like this:
  - 이제 전체 Board 컴포넌트는 다음과 같다.

```react
class Board extends React.Component {
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
   
   renderSquare(i) {
      return (
      	<Square
				value={this.props.squares[i]} 
            onClick={() => this.props.onClick(i)}
			/>
      );
   }
   
   render() {
      const winner = calculateWinner(this.state.squares);
      let status;
      if (winner) {
         status = 'Winner: ' + winner;
      } else {
         status = 'Next player: ' + (this.state.xIsNext ? 'X' : 'O');
      }
      
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

- Game's `render` should look at the most recent history entry and can take over calculating the game status:
  - Game의 `render`는 가장 최근의 히스토리를 보고 게임 status를 계산해서 가져올 수 있어야 한다.

```react
render() {
   const history = this.state.history;
   const current = history[history.length - 1];
   const winner = calculateWinner(current.squares);
   
   let status;
   if (winner) {
      status = 'Winner: ' + winner;
   } else {
      status = 'Next player: ' + (this.state.xIsNext ? 'X' : 'O');
   }
   
   return (
   	<div className="game">
      	<div className="game-board">
         	<Board
					squares={current.squares}
               onClick={(i) => this.handleClick(i)}
				/>
         </div>
         <div className="game-info">
         	<div>{status}</div>
            <ol>{/* TODO */}</ol>
         </div>
      </div>
   );
}
```

<br>

- Since Game is now rendering the status,
  - Game은 이제 status를 렌더링하므로,
- we can delete `<div className="status">{status}</div>` and the code calculating the status from the Board's `render` function.
  - `<div className="status">{status}</div>`와 Board의 `render` 함수에서 status를 계산하는 코드를 삭제할 수 있다.

```react
render() {
	return (
		<div>
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
```

<br>

- Next, we need to move the `handleClick` method implementation from Board to Game.
  - 다음으로, `handleClick` 메소드 구현을 Board에서 Game으로 옮겨야 한다.
- You can cut it from the Board class, and paste it into the Game class.
  - Board 클래스에서 잘라내고, Game 클래스에서 붙여넣을 수 있다.

<br>

- We also need to change it a little, since Game state is structured differently.
  - Game state가 다르게 구성되어 있으므로, 조금 변경해야 한다.
- Game's `handleClick` can push a new entry onto the stack
  - Game의 `handleClick`은 스택에 푸시할 수 있다.
- by concatenating the new history entry to make a new history array.
  - 새 히스토리 항목을 연결해서 새 히스토리 배열을 만들어서

```react
handleClick(i) {
   const history = this.state.history;
   const current = history[history.length - 1];
   const squares = current.squares.slice();
   if (calculateWinner(squares) || squares[i]) {
      return;
   }
   squares[i] = this.state.xIsNext ? 'X' : 'O';
   this.setState({
      history: history.concat([{
         squares: squares,
      }]),
      xIsNext: !this.state.xIsNext,
   });
}
```

<br>

- At this point, Board only  needs `renderSquare` and `render`;
  - 이 시점에서, Board는 오직 `renderSquare`와 `render`만 필요하다.
- the state initialization and click handler should both live in Game.
  - state 초기화와 클릭 핸들러는 둘 다 Game 안에서 동작한다.

<br>

[현재 코드 확인 링크](https://codepen.io/gaearon/pen/EmmOqJ?editors=0010)

<br>

### Showing the Moves (이동 표시)

- Let's show the previous moves made in the game so far.
  - 지금까지 게임에서 만들어진 이전 이동을 보자.
- We learned earlier that React elements are first-class JS objects
  - 앞서, React element는 일급 JS 객체라고 배웠다.
- and we can store them or pass them around.
  - 그리고 그것들을 저장하거나 전달할 수 있다.
- To render multiple items in React,
  - React에서 여러 항목을 렌더링하기 위해,
- We pass an array of React elements.
  - React element의 배열을 전달한다.
- The most common way to build that array is to map over your array of data.
  - 배열을 빌드하는 가장 일반적인 방법은 데이터 배열을 매핑하는 것이다.
- Let's do that in the `render` method of Game:
  - Game의 `render` 메소드에서 해보자.

```react
render() {
   const history = this.state.history;
   const current = history[history.length - 1];
   const winner = calculateWinner(current.squares);
   const moves = history.map((step, move) => {
      const desc = move
      	? 'Go to move #' + move
      	: 'Go to game start';
      return (
      	<li>
         	<button onClick={() => this.jumpTo(move)}>{desc}</button>
         </li>
      );
   });
   
   let status;
   if (winner) {
      status = 'Winner: ' + winner;
   } else {
      status = 'Next player: ' + (this.state.xIsNext ? 'X' : 'O');
   }
   
   return (
   	<div className="game">
      	<div className="game-board">
         	<Board
					squares={current.squares}
               onClick={(i) => this.handleClick(i)}
				/>
         </div>
         <div className="game-info">
         	<div>{status}</div>
            <ol>{moves}</ol>
         </div>
      </div>
   );
}
```

[현재 코드 확인 링크](https://codepen.io/gaearon/pen/EmmGEa?editors=0010)

<br>

- For each step in the history,
  - 히스토리에서 각 단계마다,
- we create a list item `<li>` with a button `<button>` inside it
  - 내부에 `<button>`이 있는 목록 항목 `<li>`를 만든다.
- that has a click handler which we'll implement shortly.
  - 곧 구현할 클릭 핸들러를 가지고 있는
- With this code, you should see a list of the moves that have been made in the game,
  - 이 코드에서, 게임에서 만들어진 이동 목록을 볼 수 있다.
- along with a warning that says:
  - 다음과 같은 경고와 함께

<br>

> Warning: Each child in an array or iterator should have a unique "key" prop.
>
> 경고: 배열 또는 반복자의 각 자식에서는 고유한 "key" prop을 가지고 있어야 한다.

<br>

> Check the render method of "Game".
>
> "Game"의 render 메소드를 확인해라.

<br>

- Let's talk about what that warning means.
  - 경고의 의미에 대해서 이야기해보자.

<br>

### keys

- When you render a list of items,
  - 항목 목록을 렌더링할 때,
- React always stores some info about each item in the list.
  - React는 항상 목록에서 각 항목에 대한 정보를 저장한다.
- If you render a component that has state, that state needs to be stored -
  - 만약 state를 가지고 있는 컴포넌트를 렌더링한다면, state는 저장되어야 한다.
- and regardless of how you implement your components,
  - 컴포넌트가 어떻게 구현되는지에 상관없이,
- React stores a reference to the backing native views.
  - React는 native view 뒤에 참조할 것을 저장한다.

<br>

- When you update that list, React needs to determine what has changed.
  - 목록을 업데이트 할 때, React는 변경된 것을 결정해야 한다.
- You could've added, removed, rearranged, or updated items in the list.
  - 목록의 항목을 추가, 제거, 재배치, 업데이트 할 수 있다.

<br>

- Imagine transitioning form
  - 이 코드가 아래의 코드로 변경된다고 생각해보자.

```reac
<li>Alexa: 7 tasks left</li>
<li>Ben: 5 tasks left</li>
```

to

```react
<li>Ben: 9 tasks left</li>
<li>Claudia: 8 tasks left</li>
<li>Alexa: 5 tasks left</li>
```

<br>

- To a human eye, it looks likely that Alexa and Ben swapped places and Claudia was added -
  - 사람의 눈에는, Alexa와 Ben이 바뀌었고, Claudia는 추가되어 보인다.
- but React is just a computer program and doesn't know what you intended it to do.
  - 그러나 React는 컴퓨터 프로그램이고, 당신이 의도한 바를 모른다.
- As a result, React asks you to specify a *key* property on each element in a list,
  - 결과적으로, React는 목록의 각 element에 대해 *key* 속성을 명시하도록 요청하며,
- a string to differentiate each component from its siblings.
  - 문자열은 형제로부터 각 컴포넌트를 구별한다.
- In this case, `alexa`, `ben`, `claudia` might be sensible keys;
  - 이 경우에는, `alexa`, `ben`, `claudia`는 분별 있는 key가 될 수 있다;
- if the items correspond to objects in a database,
  - 만약 항목들이 데이터베이스의 객체에 해당하는 경우,
- the database ID is usually a good choice:
  - 데이터베이스 ID는 대개 좋은 선택이다:

```react
<li key={user.id}>{user.name}: {user.taskCount} tasks left</li>
```

<br>

- `Key` is a special property that's reserved by React (along with `ref`, a more advanced feature).
  - `Key`는 React가 제공하는 특별한 속성이다 (`ref`에서 더 확장된 기능).
- When an element is created,
  - element가 만들어졌을 때,
- React pulls off the `key` property and stores the key directly on the returned element.
  - React는 `key` 속성을 가져오고, key를 반환된 element에 직접 저장한다.
- Even though it may look like it is part of props,
  - props의 일부인 것 같아 보이지만,
- it cannot be referenced with `this.props.key`.
  - `this.props.key`로 참조할 수 없다.
- React uses the key automatically while deciding which children to update;
  - React는 업데이트 할 자식을 결정하는 동안 key를 자동으로 key를 사용한다;
- there is no way for a component to inquire about its own key.
  - 컴포넌트가 자체 key에 대해 요청할 방법이 없다.

<br>

- When a list is rerendered,
  - 목록이 다시 렌더링될 때,
- React takes each element in the new version and looks for one with a matching key in the previous list.
  - React는 새로운 버전의 각 element를 가져오고, 이전 목록에서 매칭되는 key가 있는 것을 찾는다.
- When a key is added to the set, a component is created;
  - key가 세트에 추가될 때, 컴포넌트가 생성된다;
- when a key is removed, a component is destroyed.
  - key가 제거될 때, 컴포넌트는 파기된다.
- Keys tell React about the identity of each component,
  - Key는 React에게 각 컴포넌트의 신원을 알려주고,
- so that it can maintain the state across rerenders.
  - 다시 렌더링해서 state를 유지할 수 있도록 한다.
- If you change the key of a component,
  - 만약 컴포넌트의 key를 변경하면,
- it will be completely destroyed and recreated with a new state.
  - 그것은 완전히 파기되고, 새로운 state로 재생성 될 것이다.

<br>

- **It's strongly recommended that you assign proper keys whenever you build dynamic lists.**
  - **동적 목록을 작성할 때마다 적절한 key를 할당하는 것을 강력히 추천한다.**
- If you don't have an appropriate key handy,
  - 만약 적절한 key가 없다면,
- you may want to consider restructuring your data so that you do.
  - 데이터를 재구성하는 것이 좋다.

<br>

- If you don't specify any key,
  - 만약 key를 명시하지 않았다면,
- React will warn you and fall back to using the array index as a key -
  - React가 경고하고 배열 인덱스를 key로 사용한다 -
- which is not the correct choice
  - 이는 올바른 선택이 아니다.
- if you ever reorder elements in the list or add/remove items anywhere but the bottom of the list.
  - 만약 목록의 element를 재정렬하거나 목록의 맨 아래에 있는 항목을 추가/제거하는 경우
- Explicitly passing `key={i}` silences the warning
  - `key={i}`를 명시적으로 전달하면 경고가 사라지지만
- but has the same problem so isn't recommended in most cases.
  - 동일한 문제가 발생하므로 대부분의 경우 추천하지 않는다.


<br>

- Component keys don't need to be globally unique,
  - 컴포넌트 key는 전역적으로 고유할 필요는 없지만,
- only unique relative to the immediate siblings.
  - 관계있는 형제들 사이에서는 고유해야 한다.

<br>

### Implementing Time Travel (시간 이동 실행)

- For our move list, we already have a unique ID for each step:
  - 이동 목록에는 이미 각 단계마다 고유한 ID가 있다:
- the number of the move when it happened.
  - 이동이 발생했을 때의 숫자이다.
- In the Game's `render` method, add the key as `<li key={move}>` and the key warning should disappear:
  - Game의 `render` 메소드에서, key를 `<li key={move}>`로 추가하면 key 경고가 사라진다.

```react
const moves = history.map((step, move) => {
   const desc = move
   	? 'Go to move #' + move
   	: 'Go to game start';
   return (
   	<li key={move}>
      	<button onClick={() => this.jumpTo(move)}>{desc}</button>
      </li>
   );
});
```

[현재 코드 확인 링크](https://codepen.io/gaearon/pen/PmmXRE?editors=0010)

<br>

- Clicking any of the move buttons throws an error because `jumpTo` is undefined.
  - `jumpTo`가 정의되지 않았기 때문에, 이동 버튼 중 하나를 클릭하면 오류가 발생한다.
- Let's add a new key to Game's state to indicate which step we're currently viewing.
  - 현재 어떤 단계를 나타내는지 Game의 state에 새로운 key를 추가해보자.

<br>

- First, add `stepNumber: 0` to the initial state in Game's `constructor:`
  - 먼저, Game의 `constructor:`에 초기 state로 `stepNumber: 0`을 추가한다.

```react
class Game extends React.Component {
   constructor(props) {
      super(props);
      this.state = {
         history: [{
            squares: Array(9).fill(null),
         }],
         stepNumber: 0,
         xIsNext: true,
      };
   }
```

<br>

- Next, we'll define the `jumpTo` method in Game to update that state.
  - 다음으로, 해당 state를 업데이트하기 위해 Game에서 `jumpTo` 메소드를 정의할 것이다.
- We also want to update `xIsNext`.
  - 또한 `xIsNext`도 업데이트 할 것 이다.
- We set `xIsNext` to true if the index of the move number is an even number.
  - 만약 이동 숫자의 인덱스가 짝수면, `xIsNext`를 true로 설정한다.

<br>

- Add a method called `jumpTo` to the Game class:
  - Game 클래스에 `jumpTo` 메소드를 추가해라.

```react
handleClick(i) {
   // this method has not changed
}

jumpTo(step) {
   this.setState({
      stepNumber: step,
      xIsNext: (step % 2) === 0,
   });
}

render() {
   // this method has not changed
}
```

<br>

- Then update `stepNumber` when a new move is made
  - 그런 다음, 새로운 이동이 이루어질 때 `stepNumber`를 업데이트 해라.
- by adding `stepNumber: history.length` to the state update in Game's `handleClick`.
  - Game의 `handleClick`에서 state 업데이트에 `stepNumber: history.length`를 추가한다.
- We'll also update `handleClick` to be aware of `stepNumber` when reading the current board state
  - 또한 현재의 보드 state를 읽을 때, `stepNumber`를 인식하도록 `handleClick`을 업데이트 한다.
- so that you can go back in time then click in the board to create a new entry:
  - 그러면 다시 돌아와 보드에서 클릭해서 새로운 엔트리를 만들 수 있다.

```react
handleClick(i) {
   const history = this.state.history.slice(0, this.state.stepNumber + 1);
   const current = history[history.length - 1];
   const squares = current.squares.slice();
   if (calculateWinner(squares) || squares[i]) {
      return;
   }
   squares[i] = this.state.xIsNext ? 'X' : 'O';
   this.setState({
      history: history.concat([{
         squares: squares
      }]),
      stepNumber: history.length,
      xIsNext: !this.state.xIsNext,
   });
}
```

<br>

- Now you can modify Game's `render` to read from that step in the history:
  - 이제 히스토리에서 해당 단계를 읽기 위해 Game의 `render`를 수정할 수 있다.

```react
render() {
   const history = this.state.history;
   const current = history[this.state.stepNumber];
   const winner = calculateWinner(current.squares);
   
   // the rest has not changed
```

<br>

[현재 코드 확인 링크](https://codepen.io/gaearon/pen/gWWZgR?editors=0010)

<br>

- If you click any move button now,
  - 이제 아무 이동 버튼을 클릭하면,
- the board should immediately update to show what the game looked like at that time.
  - 보드는 그 시간에 게임이 어떻게 보였는지 보여주기 위해 즉시 업데이트되어야 한다.

<br>

### Wrapping up (마무리)

- Now, you've made a tic-tac-toe game that:
  - 틱택토 게임을 만들었다:

<br>

- lets you play tic-tac-toe,
  - 틱택토 게임을 플레이하게 하고,
- indicates when one player has won the game,
  - 한 플레이어가 게임에 이겼을 때 나타나고,
- stores the history of moves during the game,
  - 게임을 하는 동안 이동 히스토리를 저장하고,
- allows players to jump back in time to see older versions of the game board.
  - 게임 보드의 이전 버전을 보기 위해 플레이어는 돌아갈 수 있다.

<br>

- Nice work! We hope you now feel like you have a decent grasp on how React works.
  - 잘했다. React가 어떻게 작동하는지에 관해 잘 알았으면 좋겠다.

<br>

- Check out the final result here: [Final Result](https://codepen.io/gaearon/pen/gWWZgR?editors=0010).
  - 최종 결과물을 여기서 확인해라: [최종 결과물](https://codepen.io/gaearon/pen/gWWZgR?editors=0010).

<br>

- If you have extra time or want to practice yoru new skills,
  - 만약 여유 시간이 있거나 새로운 기술을 연습하고 싶다면,
- here are some ideas for improvements you could make,
  - 여기에 해볼 수 있는 몇 가지 아이디어가 있다.
- listed in order of increasing difficulty:
  - 점점 더 어려운 순으로 나열했다:

<br>

1. Display the location for each move in the format (col, row) in the move history list.
   - 이동 히스토리 목록에서 각 이동의 위치를 (col, row) 형식으로 표시해라.
2. Bold the currently selected item in the move list.
   - 이동 목록에서 현재 선택된 항목을 굵게 표시해라.
3. Rewrite Board to use two loops to make the squares instead of hardcoding them.
   - 하드코딩하는 대신 사각형을 두 개의 루프를 사용해서 Board를 다시 작성해라.
4. Add a toggle button that lets you sort the moves in either ascending or descending order.
   - 오름차순 또는 내림차순으로 이동을 정렬하는 토글 버튼을 추가해라.
5. When someone wins, highlight the three squares that caused the win.
   - 누군가가 이겼을 때, 승리를 가져온 세 개의 사각형을 강조 표시해라.
6. When no one wins, display a message about the result being a draw.
   - 아무도 이기지 않았을 때, 비기게 된 결과에 대한 메시지를 표시해라.

<br>

- Throughout this tutorial,
  - 튜토리얼을 진행하는 동안,
- we have touched on a number of React concepts including elements, components, props, and state.
  - element, 컴포넌트, props, state를 포함하는 수많은 React 개념을 다루어보았다.
- For a more in-depth explanation for each of these topics, check out [the rest of the documentation](https://reactjs.org/docs/hello-world.html).
  - 각 주제에 대한 더 깊은 설명을 원한다면, [나머지 문서](https://reactjs.org/docs/hello-world.html)를 확인해라.
- To learn more about defining components, check out the [React.Component API reference](https://reactjs.org/docs/react-component.html).
  - 컴포넌트 정의에 대해 더 배우려면, [React 컴포넌트 API 참조](https://reactjs.org/docs/react-component.html)를 확인해라.

<br>

