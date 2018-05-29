---
layout: post
title: "리액트 공식 문서 번역 - 02. Overview (tutorial)"
categories: react
tags: react tutorial
---

[React 공식 문서 링크](https://reactjs.org/tutorial/tutorial.html)

<br>

## Overview

###### 개요

<br>

### What is React? (React란?)

- React is a declarative, efficient, and flexible JavaScript library for building user interfaces.
  - React는 유저 인터페이스 빌드를 위한 선언적이고, 효율적이며, 유연한 JavaScript 라이브러리이다.

<br>

- React has a few different kinds of components,
  - React는 몇 가지 다른 종류의 컴포넌트들이 있지만,
- but we'll start with `React.Component` subclasses:
  - `React.Component` subclass로 시작할 것이다.

```react
class ShoppingList extends React.Component {
   render() {
      return (
      	<div className="shopping-list">
         	<h1>Shopping List for {this.props.name}</h1>
            <ul>
            	<li>Instagram</li>
               <li>WhatsApp</li>
               <li>Oculus</li>
            </ul>
         </div>
      );
   }
}

// Example usage: <ShoppingList name="Mark" />
```

<br>

- We'll get to the funny XML-like tags in a second.
  - XML과 유사한 재미있는 태그를 잠깐 사용할 것이다.
- Your components tell React what you want to render -
  - 작성한 컴포넌트는 렌더링하고 싶은 것을 React에게 알려준다.
- then React will efficiently update and render just the right components when your data changes.
  - 그러면 React는 데이터가 변경될 때 컴포넌트를 효율적으로 업데이트하고 렌더링한다.

<br>

- Here, ShoppingList is a **React component class**, or **React component type**.
  - 여기에서, ShoppingList는 **React 컴포넌트 클래스**이거나 **React 컴포넌트 타입**이다.
- A component takes in parameters, called `props`,
  - 컴포넌트는 `props`라 불리는 매개변수를 가져오고,
- and returns a hierarchy of views to display via the `render` method.
  - 그리고 `render` 메소드를 통해 나타낼 계층 구조를 반환한다.

<br>

- The `render` method returns a *description* of what you want to render,
  - `render` 메소드는 렌더링 할 것에 대한 *설명*을 반환하고,
- and then React takes that description and renders it to the screen.
  - 그런 다음 React가 그 설명을 가져와서 화면에 렌더링한다.
- In particular, `render` returns a **React element**, which is a lightweight description of what to render.
  - 특히, `render`는 렌더링 할 간단한 설명인 **React element**를 반환한다.
- Most React developers use a special syntax called JSX which makes it easier to write these structures.
  - 대부분의 React 개발자들은 JSX라는 특별한 문법을 사용해서 이러한 구조를 더 쉽게 작성한다.
- The `<div />` syntax is transformed at build time to `React.createElement('div')`.
  - `<div />` 문법은 빌드 시에 `React.createElement('div')`로 변환된다.
- The example above is equivalent to:
  - 위의 예는 다음과 같다.

```react
React.createElement(
	'div',
   { className: 'shopping-list'},
   React.createElement(
   	'h1',
      null,
      'Shopping List for ',
      props.name
   ),
   React.createElement(
   	'ul',
      null,
      React.createElement(
      	'li',
         null,
         'Instagram'
      ),
      React.createElement(
      	'li',
         null,
         'WhatsApp'
      ),
      React.createElement(
      	'li',
         null,
         'Oculus'
      )
   )
);
```

[전체 코드 확인](https://babeljs.io/repl/#?presets=react&code_lz=DwEwlgbgBAxgNgQwM5IHIILYFMC8AiJACwHsAHUsAOwHMBaOMJAFzwD4AoKKYQgRlYDKJclWpQAMoyZQAZsQBOUAN6l5ZJADpKmLAF9gAej4cuwAK5wTXbg1YBJSswTV5mQ7c7XgtgOqEETEgAguTuYFamtgDyMBZmSGFWhhYchuAQrADc7EA)

<br>

- If you're curious, `createElement()` is described in more detail in the [API reference](https://reactjs.org/docs/react-api.html#createelement),
  - `createElement()`에 대해 궁금한 점이 있으면, [API reference](https://reactjs.org/docs/react-api.html#createelement)를 참조하라.
- but we won't be using it directly in this tutorial.
  - 하지만 이 튜토리얼에서 직접 사용하지는 않을 것이다.
- Instead, we will keep using JSX.
  - 대신, JSX를 계속 사용할 것이다.

<br>

- You can put any JavaScript expression within braces inside JSX.
  - JavaScript 표현식을 JSX 내부 중괄호 안에 넣을 수 있다.
- Each React element is a real JavaScript object that you can store in a variable or pass around your program.
  - 각 React element는 변수에 저장하거나 프로그램에 전달할 수 있는 실제 JavaScript 객체이다.

<br>

- The `ShoppingList` component only renders built-in DOM components,
  - `ShoppingList` 컴포넌트는 오직 내장된 DOM 컴포넌트에만 렌더링한다,
- but you can compose custom React components just as easily, by writing `<ShoppingList />`.
  - 하지만 `<ShoppingList />`를 작성해서 사용자 정의 React 컴포넌트를 쉽게 작성할 수 있다.
- Each component is encapsulated so it can operate independently,
  - 각 컴포넌트는 독립적으로 작동할 수 있도록 캡슐화되어 있으므로,
- which allows you to build complex UIs out of simple components.
  - 간단한 컴포넌트들로 복잡한 UI를 빌드할 수 있다.

<br>

### Getting Started (시작하기)

- Start with this example: [Starter Code](https://codepen.io/gaearon/pen/oWWQNa?editors=0010).
  - 이 예제로 시작해라: [시작 코드](https://codepen.io/gaearon/pen/oWWQNa?editors=0010).

<br>

- It contains the shell of what we're building today.
  - 시작 코드는 우리가 빌드할 틱택토 게임의 틀을 포함한다.
- We've provided the styles so you only need to worry about the JavaScript.
  - 스타일을 제공했기 때문에 오직 JavaScript만 신경쓰면 된다.

<br>

- In particular, we have three components:
  - 특히, 세 가지 컴포넌트가 있다.

> Square (Square 컴포넌트)
>
> Board (Board 컴포넌트)
>
> Game (Game 컴포넌트)

<br>

- The Square component renders a single `<button>`,
  - Square 컴포넌트는 하나의 `<button>`을 렌더링하고,
- the Board renders 9 squares,
  - Board는 9개의 사각형을 렌더링하고,
- and the Game component renders a board with some placeholders that we'll fill in later.
  - Game 컴포넌트는 나중에 채워야 할 placeholder가 있는 보드를 렌더링한다.
- None of the components are interactive at this point.
  - 이 시점에서 어느 컴포넌트도 상호작용이 아니다.

<br>

### Passing Data Through Props (props를 통한 데이터 전달)

- Just to get our feet wet, let's try passing some data from the Board component to the Square component.
  - 막 겨우 발을 들여놓았으니, Board 컴포넌트에서 Square 컴포넌트로 데이터를 전달해보자.

<br>

- In Board's `renderSquare` method, change the code to pass a `value` prop to the Square:
  - Board의 `renderSquare` 메소드에서, `value` prop을 Square로 전달하도록 코드를 변경해라.

```react
class Board extends React.Component {
   renderSquare(i) {
      return <Square value={i} />;
   }
```

<br>

- Then change Square's `render` method to show that value by replacing `{/* TODO */}` with `{this.props.value}`:
  - 그런 다음 Square의 `render` 메소드를 변경해서 `{/* TODO */}`을 `{this.props.value}`로 바꾸면 그 값이 표시된다.

```react
class Square extends React.Component {
   render() {
      return (
      	<button className="square">
         	{this.props.value}
         </button>
      );
   }
}
```

<br>

- Before:

![Before](/assets/img/Before.png)

<br>

- After: You should see a number in each square in the rendered output.
  - After: 각 사각형 안에 출력된 숫자들을 확인할 수 있다.

![After](/assets/img/After.png)

<br>

[현재 코드 확인 링크](https://codepen.io/gaearon/pen/aWWQOG?editors=0010)

<br>

### An Interactive Component (대화형 컴포넌트)

- Let's make the Square component fill in an "X" when you click it.
  - 클릭했을 때 "X"로 채워지는 Square 컴포넌트를 만들자.
- Try changing the button tag returned in the `render()` function of the Square like this:
  - Square의 `render()` 함수에서 반환된 버튼 태그를 다음과 같이 변경해라.

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

- If you click on a square now, you should get an alert in your browser.
  - 이제 사각형을 클릭하면, 브라우저에 알림이 표시된다.

<br>

- This uses the new JavaScript [arrow function](https://developer.mozilla.org/en/docs/Web/JavaScript/Reference/Functions/Arrow_functions) syntax.
  - 새로운 JavaScript [화살표 함수](https://developer.mozilla.org/en/docs/Web/JavaScript/Reference/Functions/Arrow_functions) 문법을 사용한다.
- Note that we're passing a function as the `onClick` prop.
  - `onClick` prop으로 함수를 전달하고 있다.
- Doing `onClick={alert('click')}` would alert immediately instead of when the button is clicked.
  - `onClick={alert('click')}`을 작성하면 버튼을 클릭하는 대신 즉시 알림이 표시된다.

<br>

- React components can have state by setting `this.state` in the constructor, which should be considered private to the component.
  - React 컴포넌트는 생성자에서 `this.state`를 설정함으로써 state를 가질 수 있다.
- Let's store the current value of the square in state, and change it when the square is clicked.
  - 사각형의 현재 값을 state에 저장해보자. 그리고 사각형이 클릭되었을 때 변경해보자.

<br>

- First, add a constructor to the class to initialize the state:
  - 먼저, 클래스에 생성자를 추가해서 state를 초기화한다.

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

- In [JavaScript classes](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Classes), you need to explicitly call `super();` when defining the constructor of a subclass.
  - [JavaScript 클래스](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Classes)에서, subclass의 생성자를 정의할 때는, 명시적으로 `super();`를 호출해야 한다.

<br>

- Now change the Square `render` method to display the value from the current state, and to toggle it on click:
  - 이제 Square `render` 메소드를 변경해서 현재 state의 값을 표시하고, 클릭했을 때 전환하자.

<br>

1. Replace `this.props.value` with `this.state.value` inside the `<button>` tag.
   - `<button>` 태그 안에서 `this.props.value`를 `this.state.value`로 대체해라.
2. Replace the `() => alert()` event handler with `() => this.setState({value: 'X'})`.
   - `() => alert()` 이벤트 핸들러를 `() => this.setState({value: 'X'})`로 대체해라.

<br>

- Now the `<button>` tag looks like this:
  - 이제 `<button>` 태그는 다음과 같다.

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
         <button className="square" onClick={() => this.setState({value: 'X'})}>
         	{this.state.value}
         </button>
      );
   }
}
```

- Whenever `this.setState` is called, an update to the component is scheduled,
  - `this.setState`가 호출될 때마다, 컴포넌트에 대한 업데이트가 예정되어 있으므로,
- causing React to merge in the passed state update and rerender the component along with its descendatns.
  - 전달된 state 업데이트에서 React가 병합되고, 컴포넌트가 하위 컴포넌트와 함께 다시 렌더링된다.
- When the component rerenders, `this.state.value` will be `'X'` so you'll see an X in the grid.
  - 컴포넌트가 다시 렌더링되면, `this.state.value`는 `'X'`가 되어 격자에 X가 표시된다.

<br>

- If you click on any square, an X should show up in it.
  - 사각형을 클릭하면, 그 안에 X가 나타난다.

<br>

[현재 코드 확인 링크](https://codepen.io/gaearon/pen/VbbVLg?editors=0010)

<br>

### Developer Tools (개발자 도구)

- The React Devtools extension for [Chrome](https://chrome.google.com/webstore/detail/react-developer-tools/fmkadmapgofadopljbjfkapdkoienihi?hl=en) and [Firefox](https://addons.mozilla.org/en-US/firefox/addon/react-devtools/) lets you inspect a React component tree in your browser devtools.
  - [Chrome](https://chrome.google.com/webstore/detail/react-developer-tools/fmkadmapgofadopljbjfkapdkoienihi?hl=en)과 [Firefox의 React Devtools 확장 프로그램을 사용하면 브라우저 devtools에서 React 컴포넌트 트리를 검사할 수 있다.

![devTools](/assets/img/devTools.png)

- It lets you inspect the props and state of any of the components in your tree.
  - 이 도구를 사용하면 트리 내부 컴포넌트의 props와 state를 검사할 수 있다.

<br>

- After installing it, you can right-click any element on the page,
  - 도구를 설치하고, 페이지에서 검사하길 원하는 element를 우클릭하고,
- click "Inspect" to open the developer tools,
  - "Inspect"를 클릭하고 개발자 도구를 열면,
- and the React tab will appear as the last tab to the right.
  - 우측에 마지막 탭으로 React 탭이 나타난다.

<br>

- **However, note there are a few extra steps to get it working with CodePen:**
  - 하지만, CodePen을 사용해서 동작시키고 싶다면 몇 가지 추가적으로 필요한 단계가 있다.

<br>

1. Log in register and confirm your email (required to prevent spam).
   - 로그인이나 이메일 인증 (스팸 방지를 필요로 한다).
2. Click the "Fork" button.
   - "Fork" 버튼 클릭.
3. Click "Change View" and then choose "Debug mode".
   - "Change View"를 클릭하고난 후 "Debug mode" 선택.
4. In the new tab that opens, the devtools should now have a React tab.
   - 열리는 새 탭에서, 이제 devtools에 React 탭이 있어야 한다.

------

<br>