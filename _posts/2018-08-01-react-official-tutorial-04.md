---
layout: post
title: "04. 대화형 컴포넌트 생성 (Tutorial)"
categories: react
---

###### [React 공식 문서](https://reactjs.org/tutorial/tutorial.html#making-an-interactive-component) 번역

<br>

# React: Making an Interactive Component

###### 대화형 컴포넌트 생성

<br>

- Let's fill the Square component with an "X" when we click it.
  - Square 컴포넌트를 클릭했을 때 "X"를 채워보자.
- First, change the button tag that is returned from the Square component's `render()` function to this:
  - 먼저, Square 컴포넌트의 `render` 함수에서 반환된 button 태그를 다음과 같이 변경해라.

```react
class Square extends React.Component {
   render() {
      return (
         <button className="square" onClick={function() { alert('click'); }}>
            {this.props.value}
         </button>
      );
   }
}
```

<br>

- If we click on a Square now, we should get an alert in our browser.
  - 이제 Square를 클릭하면, 브라우저에서 alert를 받아야 한다.

<br>

> Note
>
> To save typing and avoid the [confusing behavior of this](https://yehudakatz.com/2011/08/11/understanding-javascript-function-invocation-and-this/), we will use the [arrow function syntax](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/Arrow_functions) for event handlers here and further below:
>
> 타이핑을 줄이고, [this의 동작 혼동](https://yehudakatz.com/2011/08/11/understanding-javascript-function-invocation-and-this/)을 피하기 위해, 이벤트 핸들러에 [화살표 함수 구문](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/Arrow_functions)을 사용한다.

```react
class Square extends React.Component {
   render() {
      return (
         <button className="square" onClick={() => alert('click')}>
            {this.props.value}
         </button>
      );
   }
}
```

> Notice how with `onClick={() => alert('click')}`, we're passing *a function* as the `onClick` prop.
>
> `onClick={() => alert('click')}`에서 `onClick` prop으로 *함수*를 어떻게 전달하는지에 주의해라.
>
> It only fires after a click.
>
> 클릭 후 한 번만 발생한다.
>
> Forgetting `() =>` and writing `onClick={alert('click')}` is a common mistake, and would fire the alert every time the component re-renders.
>
> `() =>`을 잊어버리고 `onClick={alert('click')}`을 작성하는 것은 흔한 실수이며, 컴포넌트가 다시 렌더링 될 때마다 alert를 발생시킨다.

<br>

- As a next step, we want the Square component to "remember" that it got clicked, and fill it with an "X" mark.
  - 다음 단계로, Square 컴포넌트가 클릭한 것을 "기억"하고, "X" 기호로 채워보자.
- To "remember" things, components use `state`.
  - 이를 "기억"하기 위해 컴포넌트는 `state`를 사용한다.

<br>

- React components can have state by setting `this.state` in their constructors.
  - React 컴포넌트는 생성자에서 `this.state`를 설정하여 state를 가질 수 있다.
- `this.state` should be considered as private to a React component that it's defined in.
  - `this.state`는 정의된 React 컴포넌트에 대해 private으로 간주되어야 한다.
- Let's store the current value of the Square in `this.state`, and change it when the Square is clicked.
  - `this.state`에 Square의 현재 값을 저장하고, Square를 클릭했을 때 이를 변경해보자.

<br>

- First, we'll add a constructor to the class to initialize the state:
  - 먼저, class에 생성자를 추가해서 state를 초기화한다.

```react
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
      );
   }
}
```

<br>

> Note
>
> In [JavaScript classes](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Classes), you need to always call `super` when defining the constructor of a subclass.
>
> [JavaScript class](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Classes)에서는, subclass의 생성자를 정의할 때 항상 `super`를 호출해야 한다.

> All React component classes that have a `constructor` should start it with a `super(props)` call.
>
> `생성자`가 있는 모든 React 컴포넌트 class는 `super(props)` 호출로 시작해야 한다.

<br>

- Now we'll change the Square's `render` method to display the current state's value when clicked:
  - 이제 Square의 `render` 메소드를 변경해서, 클릭할 때 현재 state의 값을 보여준다.

<br>

1. Replace `this.props.value` with `this.state.value` inside the `<button>` tag.
   - `<button>` 태그 내의 `this.props.value`를 `this.state.value`로 대체한다.
2. Replace the `() => alert()` event handler with `() => this.setState({value: 'X'})`.
   - `() => alert()` 이벤트 핸들러를 `() => this.setState({value: 'X'})`로 대체한다.
3. Put the `className` and `onClick` props on separate lines for better readability.
   - 가독성을 높이기 위해 `className`과 `onClick` props를 별도의 줄에 놓는다.

<br>

- After these changes, the `<button>` tag that is returned by the Square's `render` method looks like this:
  - 이러한 변경 후, Square의 `render` 메소드에서 반환한 `<button>` 태그는 다음과 같다.

```react
class Square extends React.Component {
   constructor(props) {
      super(props);
      this.state = {
         value: null,
      };
   }
   
   render() {
      return (
         <button
            className="square"
            onClick={() => this.setState({value: 'X'})}
         >
            {this.state.value}
         </button>
      );
   }
}
```

<br>

- By calling `this.setState` from an `onClick` handler in the Square's `render` method, we tell React to re-render that Square whenever its `<button>` is clicked.
  - Square의 `render` 메소드에 있는 `onClick` 핸들러에서 `this.setState`를 호출하면, `<button>`을 클릭할 때마다 React에게 해당 Square를 다시 렌더링 하라고 지시한다.
- After the update, the Square's `this.state.value` will be `'X'`, so we'll see the `X` on the game board.
  - 업데이트 후, Square의 `this.state.value`는 `'X'`가 되므로, game board에 `X`가 표시된다.
- If you click on any Square, an `X` should show up.
  - 어느 Square를 클릭해도 `X`가 표시된다.

<br>

- When you call `setState` in a component, React automatically updates the child components inside of it too.
  - 컴포넌트에서 `setState`를 호출하면, React는 자동으로 내부의 자식 컴포넌트도 업데이트한다.

<br>

- [코드 실행 확인](https://codepen.io/gaearon/pen/VbbVLg?editors=0010)

```react
class Square extends React.Component {
   constructor(props) {
      super(props);
      this.state = {
         value: null,
      };
   }
   
   render() {
      return (
         <button
            className="square"
            onClick={() => this.setState({value: 'X'})}
         >
            {this.state.value}
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

// -----------------------------------

ReactDOM.render(
   <Game />,
   document.getElementById('root')
);
```

------

<br>