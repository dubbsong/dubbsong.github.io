---
layout: post
title: "리액트 공식 문서 번역 - 06. 이벤트 핸들링 (Main Concepts)"
categories: react
tags: React
---

###### [React 공식 문서](https://reactjs.org/docs/handling-events.html) 번역

<br>

# React: Handling Events

###### 이벤트 핸들링

<br>

- Handling events with React elements is very similar to handling events on DOM elements.
  - React element를 사용해서 이벤트를 처리하는 것은 DOM element에서 이벤트를 처리하는 것과 매우 유사하다.
- There are some syntactic differences:
  - 구문상의 차이는 다음과 같다.

<br>

> - React events are named using camelCase, rather than lowercase.
>   - React 이벤트는 소문자가 아닌 camelCase(낙타 대문자)를 사용해서 명명된다.

> - With JSX you pass a function as the event handler, rather than a string.
>   - JSX에서는 문자열이 아닌 이벤트 핸들러로 함수를 전달한다.

<br>

- For example, the HTML:
  - 예를 들어, HTML에서는 다음과 같다.

```html
<button onclick="activateLasers()">
   Activate Lasers
</button>
```

<br>

- is slightly different in React:
  - React에서는 약간 다르다.

```react
<button onClick={activateLasers}>
	Activate Lasers
</button>
```

<br>

- Another difference is that you cannot return `false` to prevent default behavior in React.
  - 또 다른 차이점은, React에서 기본 동작을 방지하기 위해 `false`를 반환할 수 없다는 것이다.
- You must call `preventDefault` explicitly.
  - `preventDefault`를 명시적으로 호출해야 한다.
- For example, with plain HTML, to prevent the default link behavior of opening a new page, you can write:
  - 예를 들어, 일반 HTML에서 새 페이지를 여는 기본 링크 동작을 방지하기 위해 다음과 같이 작성할 수 있다.

```html
<a href="#" onclick="console.log('The link was clicked.'); return false">
	Click me
</a>
```

<br>

- In React, this could instead be:
  - 대신 React에서는 다음과 같이 작성할 수 있다.

```react
function ActionLink() {
   function handleClick(e) {
      e.preventDefault();
      console.log('The link was clicked.');
   }
   
   return (
   	<a href="#" onClick={handleClick}>
      	Click me
      </a>
   );
}
```

<br>

- Here, `e` is a synthetic event.
  - 여기서 `e`는 합성 이벤트이다.
- React defines these synthetic events according to the [W3C spec](https://www.w3.org/TR/DOM-Level-3-Events/), so you don't need to worry about cross-browser compatibility.
  - React는 [W3C spec](https://www.w3.org/TR/DOM-Level-3-Events/)에 따라 이러한 합성 이벤트를 정의하므로, 브라우저 간 호환성에 대해 걱정할 필요가 없다.
- See the [SyntheticEvent](https://reactjs.org/docs/events.html) reference guide to learn more.
  - 자세한 내용은 [SyntheticEvent](https://reactjs.org/docs/events.html)를 참조해라.

<br>

- When using React you should generally not need to call `addEventListener` to add listeners to a DOM element after it is created.
  - React를 사용할 때 일반적으로 DOM element가 생성된 후, 해당 DOM element에 리스너를 추가하기 위해 `addEventListener`를 호출할 필요가 없다.
- Instead, just provide a listener when the element is initially rendered.
  - 대신, element가 처음 렌더링 될 때 리스너를 제공해라.

<br>

- When you define a component using an [ES6 class](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Classes), a common pattern is for an event handler to be a method on the class.
  - [ES6 class](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/ Classes)를 사용해서 컴포넌트를 정의할 때, 이벤트 핸들러에 대한 일반적인 패턴은 class의 메소드가 되도록 하는 것이다.
- For example, this `Toggle` component renders a button that lets the user toggle between "ON" and "OFF" states:
  - 예를 들어, `Toggle` 컴포넌트는 사용자가 "ON"과 "OFF" state를 전환할 수 있게 하는 버튼을 렌더링 한다.

```react
class Toggle extends React.Component {
   constructor(props) {
      super(props);
      this.state = {isToggleOn: true};
      
      // This binding is necessary to make 'this' work in the callback
      this.handleClick = this.handleClick.bind(this);
   }
   
   handleClick() {
      this.setState(prevState => ({
         isToggleOn: !prevState.isToggleOn
      }));
   }
   
   render() {
      return (
      	<button onClick={this.handleClick}>
         	{this.state.isToggleOn ? 'ON' : 'OFF'}
         </button>
      );
   }
}

ReactDOM.render(
	<Toggle />,
   document.getElementById('root')
);
```

[코드 실행 확인 링크](https://codepen.io/gaearon/pen/xEmzGg?editors=0010)

<br>

- You have to be careful about the meaning of `this` in JSX callbacks.
  - JSX 콜백에서 `this`의 의미에 주의해야 한다.
- In JavaScript, class methods are not [bound](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_objects/Function/bind) by default.
  - JavaScript에서 class 메소드는 기본적으로 [바인딩](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_objects/Function/bind)되어 있지 않다.
- If you forget to bind `this.handleClick` and pass it to `onClick`, `this` will be `undefined` when the function is actually called.
  - `this.handleClick`을 바인딩 하는 것과 `onClick`에 전달하는 것을 잊어버린다면, 함수가 실제로 호출될 때 `this`는 `undefined` 된다.

<br>

- This is not React-specific behavior; it is a part of [how functions work in JavaScript](https://www.smashingmagazine.com/2014/01/understanding-javascript-function-prototype-bind/).
  - 이는 React만의 특별한 동작이 아니다.
  - [JavaScript에서 함수가 동작하는 방식](https://www.smashingmagazine.com/2014/01/understanding-javascript-function-prototype-bind/)의 일부이다.
- Generally, if you refer to a method without `()` after it, such as `onClick={this.handleClick}`, you should bind that method.
  - 일반적으로 `onClick={this.handleClick}`처럼 뒤에 `()`를 사용하지 않는 메소드를 참조하는 경우, 해당 메소드를 바인딩 해야 된다.

<br>

- If calling `bind` annoys you, there are two ways you can get around this.
  - `bind`를 호출하는 것이 번거롭다면, 이를 해결할 수 있는 두 가지 방법이 있다.
- If you are using the experimental [public class fields syntax](https://babeljs.io/docs/en/babel-plugin-transform-class-properties/), you can use class fields to correctly bind callbacks:
  - 실험적 [공용 class field 구문](https://babeljs.io/docs/en/babel-plugin-transform-clas s-properties/)을 사용한다면, class field를 사용해서 콜백을 올바르게 바인딩 할 수 있다.

```react
class LoggingButton extends React.Component {
   // This syntax ensures 'this' is bound within handleClick.
   // Warning: this is *experimental* syntax.
   handleClick = () => {
      console.log('this is:', this);
   }
   
   render() {
      return (
      	<button onClick={this.handleClick}>
         	Click me
         </button>
      );
   }
}
```

<br>

- This syntax is enabled by default in [Create React App](https://github.com/facebook/create-react-app).
  - 이 구문은 [Create React App](https://github.com/facebook/create-react-app)에서 기본적으로 작동한다.

<br>

- If you aren't using class fields syntax, you can use an [arrow function](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/Arrow_functions) in the callback:
  - class field 구문을 사용하지 않는다면, 콜백에서 [화살표 함수](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/Arrow_functions)를 사용할 수 있다.

```react
class LoggingButton extends React.Component {
   handleClick() {
      console.log('this is:', this);
   }
   
   render() {
      // This syntax ensures 'this' is bound within handleClick
      return (
      	<button onClick={(e) => this.handleClick(e)}>
         	Click me
         </button>
      );
   }
}
```

<br>

- The problem with this syntax is that a different callback is created each time the `LoggingButton` renders.
  - 이 구문의 문제점은 `LoggingButton`이 렌더링 될 때마다 다른 콜백이 생성된다는 것이다.
- In most cases, this is fine.
  - 대부분의 경우, 이는 괜찮다.
- However, if this callback is passed as a prop to lower components, those components might do an extra re-rendering.
  - 하지만 이 콜백이 하위 컴포넌트에 prop으로 전달된다면, 이러한 컴포넌트는 추가적으로 다시 렌더링 할 수도 있다.
- We generally recommend binding in the constructor or using the class fields syntax, to avoid this sort of performance problem.
  - 이런 종류의 성능 문제를 피하려면, 일반적으로 생성자에서 바인딩 하거나, class field 구문을 사용하는 것이 좋다.

------

<br>

## Passing Arguments to Event Handlers

###### 이벤트 핸들러에 인수 전달하기

<br>

- Inside a loop it is common to want to pass an extra parameter to an event handler.
  - 루프 내부에서 이벤트 핸들러에 추가 매개변수를 전달하려는 것이 일반적이다.
- For example, if `id` is the row ID, either of the following would work:
  - 예를 들어, `id`가 row ID라면, 다음 중 하나가 작동한다.

```react
<button onClick={(e) => this.deleteRow(id, e)}>Delete Row</button>
<button onClick={this.deleteRow.bind(this, id)}>Delete Row</button>
```

<br>

- The above two lines are equivalent, and use [arrow functions](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/Arrow_functions) and [Function.prototype.bind](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_objects/Function/bind) respectively.
  - 위의 두 라인은 동등하며, [화살표 함수](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/Arrow_functions)와 [Function.prototype.bind](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_objects/Function/bind)를 각각 사용한다.

<br>

- In both cases, the `e` argument representing the React event will be passed as a second argument after the ID.
  - 두 경우 모두, React 이벤트를 나타내는 `e` 인수가 ID 뒤에 두 번째 인수로 전달된다.
- With an arrow function, we have to pass it explicitly, but with `bind` any further arguments are automatically forwarded.
  - 화살표 함수를 사용할 경우에는 인수를 명시적으로 전달해야 하지만, `bind`를 사용할 경우에는 이후 인수가 자동으로 전달된다.

------

<br>
