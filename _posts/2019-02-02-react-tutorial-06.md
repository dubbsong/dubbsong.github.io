---
layout: post
title: "(공식 리액트 튜토리얼) 06. state 끌어올리기"
categories: dev
tags: react
---

###### [공식 리액트 튜토리얼](https://reactjs.org/tutorial/tutorial.html#lifting-state-up) 번역

<br>

#### Lifting State Up

###### state 끌어올리기

<br>

- Currently, each Square component maintains the game's state.
  - 현재 각 Square 컴포넌트는 game의 state를 유지한다.
- To check for a winner, we'll maintain the value of each of the 9 squares in one location.
  - 승자를 확인하기 위해, 한 위치에서 사각형 9개 각각의 값을 유지할 것이다.

<br>

- We may think that Board should just ask each Square for the Square's state.
  - Board가 Square의 state를 각 Square에게 물어봐야한다고 생각할 수도 있다.
- Although this approach is possible in React, we discourage it because the code becomes difficult to understand, susceptible to bugs, and hard to refactor.
  - 이 접근 방법은 React에서 가능하지만, 사용하지 않는 것이 좋다.
  - 코드를 이해하기 어렵고, 버그에 취약하고, 리팩토링이 어려워진다.
- Instead, the best approach is to store the game's state in the parent Board component instead of in each Square.
  - 가장 좋은 방법은, parent(부모, 상위) Board 컴포넌트에서 game의 state를 저장하는 것이다.
- The Board component can tell each Square what to display by passing a prop, [just like we did when we passed a number to each Square](https://reactjs.org/tutorial/tutorial.html#passing-data-through-props).
  - Board 컴포넌트가 각 Square로 prop을 전달해서, 표시할 것을 알려줄 수 있다.

<br>

> To collect data from multiple children, or to have two child components communicate with each other, you need to declare the shared state in their parent component instead.
>
> 여러 children(자식, 하위)으로부터 데이터를 모으거나, 두 child(자식, 하위) 컴포넌트가 서로 통신하도록 하려면, parent(부모, 상위) 컴포넌트에서 state를 선언해야 한다.

> The parent component can pass the state back down to the children by using props; this keeps the child components in sync with each other and with the parent component.
>
> parent 컴포넌트는 props를 사용해서 children에게 state를 전달할 수 있다.
>
> 이는 parent 컴포넌트와 child 컴포넌트, 또는 child 컴포넌트가 서로 동기화되도록 유지한다.

<br>

- Lifting state into a parent component is common when React components are refactored.
  - React 컴포넌트를 리팩토링 할 때, state를 parent 컴포넌트로 끌어올리는 것이 일반적이다.

<br>

- Add a constructor to the Board and set the Board's initial state to contain an array of 9 nulls corresponding to the 9 squares:
  - Board에 constructor를 추가한다.
  - Board의 초기 state는 9개의 null 배열을 포함하도록 설정한다.

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
  
  ...
}
```

<br>

- When we fill the board in later, the `this.state.squares` array will look something like this:
  - 나중에 board를 채우면, `this.state.squares` 배열은 다음과 같이 보이게 된다.

```js
[
  'O', null, 'X',
  'X', 'X', 'O',
  'O', null, null,
]
```

<br>

- The Board's `renderSquare` method currently looks like this:
  - Board의 `renderSquare` 메소드는 현재 다음과 같다.

```react
renderSquare(i) {
  return <Square value={i} />;
}
```

<br>

- In the beginning, we [passed the value prop down](https://reactjs.org/tutorial/tutorial.html#passing-data-through-props) from the Board to show numbers from 0 to 8 in every Square.
  - 처음에는, 0부터 8까지의 숫자를 보여주기 위해 Board에서 모든 Square로 [prop 값을 전달했다](https://reactjs.org/tutorial/tutorial.html#passing-data-through-props).
- In a different previous step, we replaced the numbers with an `X` mark [determined by Square's own state](https://reactjs.org/tutorial/tutorial.html#making-an-interactive-component).
  - 다른 이전 단계에서는, [Square의 자체 state로 결정된](https://reactjs.org/tutorial/tutorial.html#making-an-interactive-component) `X`로 숫자를 대체했다.
- This is why Square currently ignores the `value` prop passed to it by the Board.
  - 이것이 Square가 Board에 의해 전달된 `value` prop을 무시하는 이유이다.

<br>

- We will now use the prop passing mechanism again.
  - 이제 prop 전달 메커니즘을 다시 사용할 것이다.
- We will modify the Board to instruct each individual Square about its current value (`'X'`, `'O'`, or `null`).
  - Board가 현재 값(`'X'`, `'O'`, or `null`)을 각 Square에게 알려주도록 수정한다.
- We have already defined the `squares` array in the Board's constructor, and we will modify the Board's `renderSquare` method to read from it:
  - 이미 Board의 constructor에서 `squares` 배열을 정의했다.
  - 이제 Board의 `renderSquare` 메소드를 수정한다.

```react
renderSquare(i) {
  return <Square value={this.state.squares[i]} />;
}
```

[코드 실행 확인](https://codepen.io/gaearon/pen/gWWQPY?editors=0010)

<br>

- Each Square will now receive a `value` prop that will either be `'X'`, `'O'`, or `null` for empty squares.
  - 이제 각 Square는 `value` prop (`'X'`, `'O'`, `null`)을 수신한다.

<br>

- Next, we need to change what happens when a Square is clicked.
  - 다음으로, Square를 클릭했을 때 일어나는 일을 변경해야 한다.
- The Board component now maintains which squares are filled.
  - 이제 Board 컴포넌트는, 어떤 사각형이 채워지는지를 관리한다.
- We need to create a way for the Square to update the Board's state.
  - Square가 Board의 state를 업데이트할 수 있는 방법을 작성해야 한다.
- Since state is considered to be private to a component that defines it, we cannot update the Board's state directly from Square.
  - state는 private으로 간주되므로, Board의 state를 Square에서 직접 업데이트할 수 없다.

<br>

- Instead, we'll pass down a function from the Board to the Square, and we'll have Square call that function when a square is clicked.
  - 대신 Board에서 Square로 함수를 전달하고, Square가 클릭될 때 Square 함수를 호출한다.
- We'll change the `renderSquare` method in Board to:
  - Board의 `renderSquare` 메소드를 다음과 같이 변경한다.

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

<br>

> **Note**
>
> We split the returned element into multiple lines for readability, and added parentheses so that JavaScript doesn't insert a semicolon after `return` and break our code.
>
> 가독성을 위해, 괄호를 추가하고 element를 여러 줄로 나누었다.

<br>

- Now we're passing down two props from Board to Square: `value` and `onClick`.
  - 이제 `value`와 `onClick` 두 props를, Board에서 Square로 전달한다.
- The `onClick` prop is a function that Square can call when clicked.
  - `onClick` prop은 Square가 클릭될 때 호출할 수 있는 함수이다.

<br>

- We'll make the following changes to Square:
  - Square를 다음과 같이 변경한다.

<br>

1. Replace `this.state.value` with `this.props.value` in Square's `render` method.
   - Square의 `render` 메소드에서, `this.state.value`를 `this.props.value`로 대체한다.
2. Replace `this.setState()` with `this.props.onClick()` in Square's `render` method.
   - Square의 `render` 메소드에서, `this.setState()`를 `this.props.onClick()`으로 대체한다.
3. Delete the `constructor` from Square because Square no longer keeps track of the game's state.
   - Square의 `constructor`를 제거한다.
   - Square는 더 이상 game의 state를 파악하지 않는다.

<br>

- After these changes, the Square component looks like this:
  - 이러한 변경 후, Square 컴포넌트는 다음과 같다.

```react
class Square extends React.Component {
  render() {
    return (
      <button
        className="square"
        onClick={() => this.props.onClick()}
      >
        {this.props.value}
      </button>
    );
  }
}
```

<br>

- When a Square is clicked, the `onClick` function provided by the Board is called.
  - Square를 클릭하면, Board에서 제공되는 `onClick` 함수가 호출된다.
- Here's a review of how this is achieved:
  - 이것이 어떻게 이루어지는지에 대한 것은 다음과 같다.

<br>

1. The `onClick` prop on the built-in DOM `<button>` component tells React to set up a click event listener.
   - `<button>` 컴포넌트의 `onClick` prop은, 클릭 이벤트 리스너를 설정하도록 React에게 알려준다.
2. When the button is clicked, React will call the `onClick` event handler that is defined in Square's `render()` method.
   - 버튼을 클릭하면, React는 Square의 `render()` 메소드에 정의된 `onClick` 이벤트 핸들러를 호출한다.
3. This event handler calls `this.props.onClick()`. The Square's `onClick` prop was specified by the Board.
   - 이 이벤트 핸들러는 `this.props.onClick()`을 호출한다.
   - Square의 `onClick` prop은 Board에 의해 지정되었다.
4. Since the Board passed `onClick={() => this.handleClick(i)}` to Square, the Square calls `this.handleClick(i)` when clicked.
   - Board가 `onClick={() => this.handleClick(i)}`을 Square로 전달했으므로, 클릭될 때 Square는 `this.handleClick(i)`를 호출한다.
5. We have not defined the `handleClick()` method yet, so our code crashes. If you click a square now, you should see a red error screen saying something like "this.handleClick is not a function".
   - 아직 `handleClick()` 메소드를 정의하지 않았으므로, 코드가 작동하지 않는다.
   - "this.handleClick is not a function"과 같은 빨간 에러가 화면에 표시된다.

<br>

> **Note**
>
> The DOM `<button>` element's `onClick` attribute has a special meaning to React because it is a built-in component.
>
> DOM `<button>` element의 `onClick` 속성은 내장 컴포넌트이므로, React에게 특별한 의미가 있다.

> For custom components like Square, the naming is up to you.
>
> Square와 같은 사용자 정의 컴포넌트의 네이밍은 사용자에게 달려 있다.

> We could give any name to the Square's `onClick` prop or Board's `handleClick` method, and the code would work the same.
>
> Square의 `onClick` prop 또는 Board의 `handleClick` 메소드에 아무 이름을 지정할 수 있다.
>
> 코드도 동일하게 작동한다.

> In React, it's conventional to use `on[Event]` names for props which represent events and `handle[Event]` for the methods which handle the events.
>
> React에서는, 이벤트를 나타내는 props에 `on[Event]`를 사용하는 것이 일반적이다.
>
> 이벤트를 처리하는 메소드에는 `handle[Event]`를 사용한다.

<br>

- When we try to click a Square, we should get an error because we haven't defined `handleClick` yet.
  - Square를 클릭하면 에러가 발생한다.
  - 아직 `handleClick`을 정의하지 않았기 때문이다.
- We'll now add `handleClick` to the Board class:
  - 이제 Board class에 `handleClick`을 추가한다.

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
    this.setState({ squares: squares });
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

[코드 실행 확인](https://codepen.io/gaearon/pen/ybbQJX?editors=0010)

<br>

- After these changes, we're again able to click on the Squares to fill them, the same as we had before.
  - 이러한 변경 후 다시 사각형을 클릭하면, 이전처럼 사각형이 채워진다.
- However, now the state is stored in the Board component instead of the individual Square components.
  - 하지만 이제 state는, 각 Square 컴포넌트 대신 Board 컴포넌트에 저장된다.
- When the Board's state changes, the Square components re-render automatically.
  - Board의 state가 변경되면, Square 컴포넌트가 자동으로 다시 렌더링 된다.
- Keeping the state of all squares in the Board component will allow it to determine the winner in the future.
  - Board 컴포넌트에서 모든 사각형의 state를 유지하면, 나중에 승자를 결정할 수 있게 된다.

<br>

- Since the Square components no longer maintain state, the Square components receive values from the Board component and inform the Board component when they're clicked.
  - Square 컴포넌트는 더 이상 state를 유지하지 않으므로, Square 컴포넌트는 Board 컴포넌트에서 값을 수신하고, 클릭했을 때 Board 컴포넌트에 알려준다.
- In React terms, the Square components are now `controlled components`.
  - 이제 React 입장에서 Square 컴포넌트는, `controlled 컴포넌트`이다.
- The Board has full control over them.
  - Board가 모든 것을 통제한다.

<br>

- Note how in `handleClick`, we call `.slice()` to create a copy of the `squares` array to modify instead of modifying the existing array.
  - `handleClick`에서 어떻게 작동하는지 주의한다.
  - 기존 배열을 수정하는 대신, `slice()`를 호출해서 `squares` 배열의 복사본을 생성한다.
- We will explain why we create a copy of the `squares` array in the next section.
  - 왜 `squares` 배열의 복사본을 생성하는지, 다음 섹션에서 설명할 것이다.

------

<br>