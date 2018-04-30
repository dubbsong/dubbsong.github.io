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
2. When the button is clicked, React will call the `onClick` event handler defined in Square's `render()` method.
   - 버튼을 클릭하면, React는 Square의 `render()` 메소드에 정의된 `onClick` 이벤트 핸들러를 호출한다.
3. This event handler calls `this.props.onClick()`. Square's props were specified by the Board.
   - 이 이벤트 핸들러는 `this.props.onClick()`을 호출한다. Square의 props는 Board에 의해 명시되었다.
4. Board passed `onClick={() => this.handleClick(i)}` to Square, so, when called, it runs `this.handleClick(i)` on the Board.
   - Board는 `onClick={() => this.handleClick(i)}`를 Square에 전달했으므로, 호출될 때, Board에서 `this.handleClick(i)`을 실행한다.
5. We have not defined the `handleClick()` method on the Board yet, so the code crashes.
   - 아직 Board에서 `handleClick()` 메소드를 정의하지 않았으므로, 코드가 깨진다.


<br>

- Note that DOM `<button>` element's `onClick` attribute has a special meaning to React,
  - DOM `<button>` 요소의 `onClick` 속성은 React에 특별한 의미를 가진다.
- but we could have named Square's `onClick` prop or Board's `handleClick` method differently.
  - 하지만 Square의 `onClick` prop 또는 Board의 `handleClick` 메소드의 이름을 다르게 지정할 수 있다.
- It is, however, conventional in React apps to use `on*` names for the attributes and `handle*` for the handler methods.
  - 그러나 React 애플리케이션에서 속성에 `on*` 이름을 사용하고, 핸들러 메소드에 `handle*`을 사용하는 것이 일반적이다.

<br>

- Try clicking a square - you should get an error because we haven't defined `handleClick` yet.
  - 사각형을 클릭해보자. 아직 `handleClick`을 정의하지 않았기 때문에 오류가 발생할 것이다.
- Add it to the Board class.
  - Board 클래스에 `handleClick`을 추가해라.

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

[현재 코드 확인 링크](https://codepen.io/gaearon/pen/ybbQJX?editors=0010)

<br>

- We call `.slice()` to copy the `squares` array instead of mutating the existing array.
  - 기존 배열을 변경하는 대신 `.slice()`를 호출해서 `squares` 배열을 복사한다.
- Jump ahead a [section](https://reactjs.org/tutorial/tutorial.html#why-immutability-is-important) to learn why immutability is important.
  - 왜 불변성이 중요한지 배우기 위해 [section](https://reactjs.org/tutorial/tutorial.html#why-immutability-is-important)으로 이동해라.

<br>

- Now you should be able to click in squares to fill them again,
  - 이제 사각형을 클릭해서 다시 채울 수 있어야 하지만,
- but the state is stored in the Board component instead of in each Square,
  - state는 각 Square가 아닌 Board 컴포넌트에 저장되므로,
- which lets us continue building the game.
  - 게임을 계속 만들 수 있다.
- Note how whenever Board's state changes,
  - Board의 state가 바뀔 때마다,
- the Square components rerender automatically.
  - Square 컴포넌트는 자동으로 다시 렌더링된다.

<br>

- Square no longer keeps its own state;
  - Square는 더 이상 자체 state를 유지하지 않는다;
- it receives its value from its parent Board and informs its parent when it's clicked.
  - 그것은 부모 Board로부터 그 값을 받고, 그것을 클릭했을 때 그 부모에게 알린다.
- We call components like this **controlled components**.
  - 이러한 **제어된 컴포넌트**와 같은 컴포넌트를 호출한다.

<br>

### Why Immutability Is Important (왜 불변성이 중요한가)

- In the previous code example,
  - 이전 예제 코드에서,
- We suggest using the `.slice()` operator to copy the `squares` array prior to making changes and to prevent mutating the existing array.
  - 기존 배열을 수정하지 않고 변경하기 전에 `.slice()` 연산자를 사용해서 `squares` 배열을 복사하는 것이 좋다.



- Let's talk about what this means and why it is an important concept to learn.

  - 이것이 의미하는 게 무엇인지, 왜 중요한 개념인지 이야기해보자.


<br>

- There are generally two ways for changing data.
  - 데이터를 변경하는 데에는 일반적으로 두 가지 방법이 있다.
- The first method is to *mutate* the data by directly changing the values of a variable.
  - 첫 번째 방법으로는 변수의 값을 직접 변경해서 데이터를 *변경*하는 것이다.
- The second method is to replace the data with a new copy of the object that also includes desired changes.
  - 두 번째 방법은 원하는 변경 내용이 포함된 객체의 새 복사본으로 데이터를 대체하는 것이다.

<br>

###### Data change with mutation

###### mutation을 사용한 데이터 변경

```react
var player = {score: 1, name: 'Jeff'};
player.score = 2;
// Now player is {score: 2, name: 'Jeff'}
```

<br>

###### Data change without mutation

###### mutation을 사용하지 않은 데이터 변경

```react
var player = {score: 1, name: 'Jeff'};

var newPlayer = Object.assign({}, player, {score: 2});
// Now player is unchanged, but newPlayer is {score: 2, name: 'Jeff'}

//Or if you are using object spread syntax proposal, you can write:
// var newPlayer = {...player, score: 2};
```

<br>

- The end result is the same but by not mutating (or changing the underlying data) directly we now have an added benefit
  - 직접 변경하지 않아도 (또는 기본 데이터를 변경해도) 결과는 동일하다.
- that can help us increase component and overall application performance.
  - 하지만 컴포넌트와 전반적인 애플리케이션의 성능을 향상시키는 데 도움이 되는 추가 이점이 있다.

<br>

###### Easier Undo/Redo and Time Travel

###### 쉬운 실행 취소/다시 실행과 시간 이동

- Immutability also makes some complex features much easier to implement.
  - 또한 불변성은 복잡한 기능을 좀 더 쉽게 구현할 수 있게 한다.
- For example, further in this tutorial we will implement time travel between different stages of the game.
  - 예를 들어, 이 튜토리얼에서는 게임의 다른 단계들 간의 시간 이동을 구현할 것이다.
- Avoiding data mutations lets us keep a reference to older versions of the data,
  - 데이터 변경을 피하면 데이터의 이전 버전에 대한 참조를 유지할 수 있다.
- and switch between them if we need to.
  - 그리고 필요하다면 데이터 사이를 전환할 수 있다.

<br>

###### Tracking Changes

###### 변경 사항 추적

- Determining if a mutated object has changed is complex because changes are made directly to the object.
  - 변형되는 객체가 변경되었는지 확인하는 것은 변경 사항이 직접 객체에 적용되기 때문에 복잡하다.
- This then requires comparing the current object to a previous copy,
  - 그런 다음 현재 객체를 이전 사본과 비교하는 것이 요구되며,
- traversing the entire object tree, and comparing each variable and value.
  - 전체 객체 트리를 가로지르고, 각 변수와 값의 비교가 필요하다.
- This process can become increasingly complex.
  - 이 과정은 더 복잡해질 수 있다.

<br>

- Determining how an immutable object has changed is considerably easier.
  - 불변 객체가 어떻게 변경되었는지 확인하는 것은 상당히 쉽다.
- If the object being referenced is different from before, then the object has changed.
  - 만약 참조되는 객체가 이전과 다르면, 객체는 변경된 것이다.
- That's it.
  - That's it.

<br>

###### Determining When to Re-render in React

###### React에서 언제 다시 렌더링할지 결정하기

- The biggest benefit of immutability in React comes when you build simple *pure* components.
  - React에서 불변성의 가장 큰 장점은 간단한 순수 컴포넌트를 빌드할 때이다.
- Since immutable data can more easily determine if changes have been made,
  - 변경 불가능한 데이터는 변경이 이루어졌는지를 보다 쉽게 판별할 수 있기 때문에,
- it also helps to determine when a component requires being re-rendered.
  - 컴포넌트를 다시 렌더링해야 할 때를 결정하는 데에 도움이 된다.

<br>

- To learn more about `shouldComponentUpdate()` and how you can build *pure components* take a look at [Optimizing Performance](https://reactjs.org/docs/optimizing-performance.html#examples).
  - `shouldComponentUpdate()`와 *순수 컴포넌트*를 어떻게 빌드하는지에 대한 자세한 내용은 [성능 최적화](https://reactjs.org/docs/optimizing-performance.html#examples)를 참조해라.

<br>

### Functional Components (함수 컴포넌트)

- We've removed the constructor,
  - 우리는 생성자를 제거했다.
- and in fact, React supports a simpler syntax called **functional components** for component types like Square that only consist of a `render` method.
  - 사실 React는 `render` 메소드로만 구성되는 Square와 같은 컴포넌트 타입을 위해 **함수 컴포넌트**라는 더 간단한 문법을 지원한다.
- Rather than define a class extending `React.Component`,
  - `React.Component`를 확장하는 클래스를 정의하는 대신,
- simply write a function that takes props and returns what should be rendered.
  - 간단하게 props를 가져오고 렌더링해야 할 것을 반환하는 함수를 작성하는 것이 좋다.

<br>

- Replace the whole Square class with this function:
  - Square 클래스를 전체를 이 함수로 대체해라.

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

- You'll need to change `this.props` to `props` both times it appears.
  - 그것이 나타날 때마다 `this.props`를 둘 다 `props`로 변경해야 할 것이다.
- Many components in your apps will be able to be written as functional components:
  - 애플리케이션에 있는 여러 컴포넌트가 함수 컴포넌트로 작성될 수 있다:
- these components tend to be easier to write and React will optimize them more in the future.
  - 이러한 컴포넌트는 더 쉽게 작성될 수 있고, React는 앞으로 더 최적화 될 것이다.

<br>

- While we're cleaning up the code, we also changed `onClick={() => props.onClick()}` to just `onClick={props.onClick}`,
  - 코드를 정리하는 동안, `onClick={() => props.onClick()} `을 `onClick={props.onClick}`로 변경했다.
- as passing the function down is enough for our example.
  - 함수를 전달하는 것은 우리 예제에서 충분하다.
- Note that `onClick={props.onClick()}` would not work because it would call `props.onClick` immediately instead of passing it down.
  - `onClick={props.onClick()}`은 전달하는 대신, `props.onClick`을 즉시 호출하기 때문에 작동하지 않는다.

<br>

[현재 코드 확인 링크](https://codepen.io/gaearon/pen/QvvJOv?editors=0010)

<br>

### Taking Turns (변화 가져오기)

- An obvious defect in our game is that only X can play.
  - 우리 게임의 명백한 결함은 오직 X만 플레이 할 수 있다는 것이다.
- Let's fix that.
  - 수정해보자.

<br>

- Let's default the first move to be by 'X'.
  - 첫 번째 이동이 'X'가 되도록 설정해보자.
- Modify our starting state in our Board constructor:
  - Board 생성자에서 초기 state를 수정해라.

```react
class Board extends React.Component {
   constructor(props) {
      super(props);
      this.state = {
         squares: Array(9).fill(null),
         xIsNext: true,
      };
   }
```

<br>

- Each time we move we shall toggle `xIsNext` by flipping the boolean value and saving the state.
  - 이동할 때마다 불린 값을 뒤집고 state를 저장해서 `xIsNext`를 토글한다.
- Now update Board's `handleClick` function to flip the value of `xIsNext`:
  - 이제 Board의 `handleClick` 함수를 `xIsNext` 값이 바뀔 수 있도록 업데이트한다.

```react
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

- Now X and O take turns.
  - 이제 X와 O가 교대로 나타난다.
- Next, change the "status" text in Board's `render` so that it also displays who is next:
  - 다음으로, Board의 `render`에서 누가 다음인지 표시하기 위해 "status"를 변경한다.

```react
render() {
   const status = 'Next player: ' + (this.state.xIsNext ? 'X' : 'O');
   
   return (
   	// the rest has not changed
```

<br>

- After these changes you should have this Board component:
  - 이러한 변경 후에 Board 컴포넌트는 다음과 같다.

```react
class Board extends React.Component {
   constructor(props) {
      super(props);
      this.state = {
         squares: Array(9).fill(null),
         xIsNext: true,
      };
   }
   
   handleClici(i) {
      const squares = this.state.squares.slice();
      squares[i] = this.state.xIsNext ? 'X' : 'O';
      this.setState({
         squares: squares,
         xIsNext: !this.state.xIsNext,
      });
   }
   
   renderSquare(i) {
      return (
      	<Square
				value={this.state.squares[i]}
            onClick={() => this.handleClick(i)}
			/>
      );
   }
   
   render() {
      const status = 'Next plater: ' + (this.state.xIsNext ? 'X' : 'O');
      
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

[현재 코드 확인 링크](https://codepen.io/gaearon/pen/KmmrBy?editors=0010)

<br>

### Declaring a Winner (승자 선언)

- Let's show when a game is won.
  - 게임에 이겼을 때를 확인해보자.
- Add this helper function to the end of the file:
  - 다음과 같은 헬퍼 함수를 파일의 끝에 추가해라.

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
```

<br>

- You can call it in Board's `render` function to check if anyone has won the game
  - Board의 `render` 함수에서 게임에서 누가 이겼는지 확인할 수 있도록 호출할 수 있다.
- and make the status text show "Winner: [X/O]" when someone wins.
  - 그리고 누가 이겼다면 "Winner: [X/O]"를 status 텍스트에 표시할 수 있다.

<br>

- Replace the `status` declaration in Board's `render` with this code:
  - Board의 `render`에서 `status` 선언을 다음 코드로 대체해라.

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

- You can now change `handleClick` in Board to return early
  - 이제 Board에서 `handleClick`을 일찍 반환해서 변경할 수 있다.
- and ignore the click if someone has already won the game or if a square is already filled:
  - 그리고 누군가가 게임에서 이미 이겼거나 사각형이 이미 채워져 있는 경우 클릭을 무시할 수 있다.

```react
handleClick(i) {
   const square = this.state.squares.slice();
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

- Congratulations! You now have a working tic-tac-toe game.
  - 축하한다. 이제 작동하는 틱택토 게임을 완성했다.
- And now you know the basics of React.
  - 그리고 이제 React의 기초를 알게 되었다.
- So *you're* probably the real winner here.
  - 여기에서 진짜 승자는 아마도 *당신*이다.

<br>

[현재 코드 확인 링크](https://codepen.io/gaearon/pen/LyyXgK?editors=0010)

<br>

