---
layout: post
title: "(공식 리액트 튜토리얼 04) 대화형 컴포넌트 생성하기"
categories: dev
tags: react
---

###### [공식 리액트 튜토리얼](https://reactjs.org/tutorial/tutorial.html#making-an-interactive-component) 번역

<br>

#### Making an Interactive Component

###### 대화형 컴포넌트 생성하기

<br>

- Let's fill the Square component with an "X" when we click it.
  - 클릭했을 때, Square 컴포넌트를 `"X"`로 채워보자.
- First, change the button tag that is returned from the Square component's `render()` function to this:
  - 먼저, Square 컴포넌트의 `render()` 함수에서 반환되는 button 태그를 다음과 같이 변경한다.

```react
class Square extends React.Component {
  render() {
    return (
      <button
        className="square"
        onClick={function() {
          alert('click');
        }}
      >
        {this.props.value}
      </button>
    );
  }
}
```

<br>

- If you click on a Square now, you should see an alert in your browser.
  - 이제 Square를 클릭하면, 브라우저에서 alert가 표시된다.

<br>

> **Note**
>
> To save typing and avoid the [confusing behavior of this](https://yehudakatz.com/2011/08/11/understanding-javascript-function-invocation-and-this/), we will use the [arrow function syntax](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/Arrow_functions) for event handlers here and further below:
>
> 타이핑을 줄이고, [this의 혼란스러운 동작](https://yehudakatz.com/2011/08/11/understanding-javascript-function-invocation-and-this/)을 피하기 위해, 이벤트 핸들러에 [화살표 함수 구문](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/Arrow_functions)을 사용한다.

```react
class Square extends React.Component {
  render() {
    return (
      <button
        className="square"
        onClick={() => alert('click')}
      >
        {this.props.value}
      </button>
    );
  }
}
```

> Notice how with `onClick={() => alert('click')}`, we're passing a *function* as `onClick` prop.
>
> `onClick` prop으로 함수를 전달하는 것에 주의한다.
>
> `onClick={() => alert('click')}`

<br>

- As a next step, we want the Square component to "remember" that it got clicked, and fill it with an "X" mark.
  - 다음으로, 클릭한 것을 컴포넌트가 "기억"하고, "X"로 채우기를 원한다.
- To "remember" things, components use `state`.
  - 이를 "기억"하기 위해, 컴포넌트는 `state`를 사용한다.

<br>

- React components can have state by setting `this.state` in their constructors.
  - React 컴포넌트는, constructor(생성자)에서 `this.state`를 설정해서 state를 가질 수 있다.
- `this.state` should be considered as private to a React component that it's defined in.
  - `this.state`는 정의된 React 컴포넌트에 대해 private으로 간주되어야 한다.

- Let's store the current value of the Square in `this.state`, and change it when the Square is clicked.
  - `this.state`에 Square의 현재 값을 저장하고, Square를 클릭했을 때 변경해보자.

<br>

- First, we'll add a constructor to the class to initialize the state:
  - 먼저, state를 초기화하기 위해서 class에 constructor를 추가한다.

```react
class Square extends React.Component {
  constructor(props) {
    super(props);
    this.state = {
      value: null
    };
  }
  
  render() {
    return (
      <button
        className="square"
        onClick={() => alert('click')}
      >
        {this.props.value}
      </button>
    );
  }
}
```

<br>

> **Note**
>
> In [JavaScript classes](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Classes), you need to always call `super` when defining the constructor of a subclass.
>
> [JS class](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Classes)에서 subclass의 constructor를 정의할 때, 항상 `super()`를 호출해야 한다.

> All React component classes that have a `constructor` should start it with a `super(props)` call.
>
> `constructor`가 있는 모든 React 컴포넌트 class는, `super(props)` 호출로 시작해야 한다.

<br>

- Now we'll change the Square's `render` method to display the current state's value when clicked:
  - 이제 클릭했을 때 현재 state의 값을 표시하기 위해, Square의 `render` 메소드를 변경한다.

<br>

1. Replace `this.props.value` with `this.state.value` inside the `<button>` tag.
   - `<button>` 태그 내의 `this.props.value`를 `this.state.value`로 대체한다.
2. Replace the `onClick={…}` event handler with `onClick={() => this.setState({value: 'X'})}`.
   - `onClick={…}` 이벤트 핸들러를 `onClick={() => this.setState({value: 'X'})}`로 대체한다.
3. Put the `className` and `onClick` props on separate lines for better readability.
   - 더 나은 가독성을 위해, `className`과 `onClick` props를 구분해서 놓는다.

```react
class Square extends React.Component {
  constructor(props) {
    super(props);
    this.state = {
      value: null
    };
  }
  
  render() {
    return (
      <button
        className="square"
        onClick={() => this.setState({ value: 'X' })}
      >
        {this.state.value}
      </button>
    );
  }
}
```

[코드 실행 확인](https://codepen.io/gaearon/pen/VbbVLg?editors=0010)

<br>

- By calling `this.setState` from an `onClick` handler in the Square's `render` method, we tell React to re-render that Square whenever its `<button>` is clicked.
  - `<button>`을 클릭해서 `this.setState`를 호출할 때마다, 해당 Square를 다시 렌더링하도록 React에게 알려준다.
- After the update, the Square's `this.state.value` will be `'X'`, so we'll see the `X` on the game board.
  - 업데이트 후, Square의 `this.state.value`는 `'X'`가 되므로, game board에 `X`가 표시된다.
- If you click on any Square, an `X` should show up.
  - Square를 클릭하면, `X`가 나타난다.

<br>

- When you call `setState` in a component, React automatically updates the child components inside of it too.
  - 컴포넌트에서 `setState`를 호출하면, React는 child 컴포넌트를 자동으로 업데이트한다.

------

<br>

<br>
