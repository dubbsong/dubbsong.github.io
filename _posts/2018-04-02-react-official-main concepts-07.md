---
layout: post
title: "리액트 공식 문서 번역 - 07. 조건부 렌더링 (Main Concepts)"
categories: react
tags: React
---

###### [React 공식 문서](https://reactjs.org/docs/conditional-rendering.html) 번역

<br>

# React: Conditional Rendering

###### 조건부 렌더링

<br>

- In React, you can create distinct components that encapsulate behavior you need.
  - React에서는 필요한 동작을 캡슐화하는 고유한 컴포넌트를 생성할 수 있다.
- Then, you can render only some of them, depending on the state of your application.
  - 그런 다음, 애플리케이션의 state에 따라 해당 컴포넌트의 일부만 렌더링 할 수 있다.

<br>

- Conditional rendering in React works the same way conditions work in JavaScript.
  - React의 조건부 렌더링은 JavaScript에서 동작하는 것과 같은 방식으로 동작한다.
- Use JavaScript operators like [if](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/if...else) or the [conditional operator](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Conditional_Operator) to create elements representing the current state, and let React update the UI to match them.
  - [if](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/if...else) 또는 [조건 연산자](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Conditional_Operator)와 같은 JavaScript 연산자를 사용해서 현재 state를 나타내는 element를 생성하고, React가 이에 따라 UI를 업데이트해서 일치하도록 한다.

<br>

- Consider these two components:
  - 다음 두 컴포넌트를 살펴보자.

```react
function UserGreeting(props) {
   return <h1>Welcome back!</h1>;
}

function GuestGreeting(props) {
   return <h1>Please sign up.</h1>;
}
```

<br>

- We'll create a `Greeting` component that displays either of these components depending on whether a user is logged in:
  - 사용자가 로그인했는지 여부에 따라, 다음 컴포넌트 중 하나를 표시하는 `Greeting` 컴포넌트를 생성한다.

```react
function UserGreeting(props) {
   return <h1>Welcome back!</h1>;
}

function GuestGreeting(props) {
   return <h1>Please sign up.</h1>;
}

function Greeting(props) {
   const isLoggedIn = props.isLoggedIn;
   if (isLoggedIn) {
      return <UserGreeting />;
   }
   return <GuestGreeting />;
}

ReactDOM.render(
   // isLoggedIn={true}로 변경해라.
   <Greeting isLoggedIn={false} />,
   document.getElementById('root')
);
```

[코드 실행 확인 링크](https://codepen.io/gaearon/pen/ZpVxNq?editors=0011)

<br>

- This example renders a different greeting depending on the value of `isLoggedIn` prop.
  - 이 예제는 `isLoggedIn` prop의 값에 따라 다른 greeting을 렌더링 한다.

------

<br>

## Element Variables

###### element 변수

<br>

- You can use variables to store elements.
  - 변수를 사용해서 element를 저장할 수 있다.
- This can help you conditionally render a part of the component while the rest of the output doesn't change.
  - 이렇게 하면 컴포넌트의 일부를 조건부로 렌더링 하는 데 도움이 되며, 나머지 출력을 변경되지 않는다.

<br>

- Consider these two new components representing Logout and Login buttons:
  - Logout과 Login 버튼을 나타내는 다음 두 개의 새 컴포넌트를 살펴보자.

```react
function LoginButton(props) {
   return (
      <button onClick={props.onClick}>
         Login
      </button>
   );
}

function LogoutButton(props) {
   return (
      <button onClick={props.onClick}>
         Logout
      </button>
   );
}
```

<br>

- In the example below, we will create a [stateful component](https://reactjs.org/docs/state-and-lifecycle.html#adding-local-state-to-a-class) called `LoginControl`.
  - 아래 예제에서는, `LoginControl`이라는 [stateful 컴포넌트](https://reactjs.org/docs/state-and-lifecycle.html#adding-local-state-to-a-class)를 생성한다.

<br>

- It will render either `<LoginButton />` or `<LogoutButton />` depending on its current state.
  - 이 컴포넌트는 자신의 현재 state에 따라 `<LoginButton />` 또는 `<LogoutButton />` 중 하나를 렌더링 한다.
- It will also render a `<Greeting />` from the previous example:
  - 이전 예제에서 생성한 `<Greeting />`도 렌더링 한다.

```react
class LoginControl extends React.Component {
   constructor(props) {
      super(props);
      this.handleLoginClick = this.handleLoginClick.bind(this);
      this.handleLogoutClick = this.handleLogoutClick.bind(this);
      this.state = {isLoggedIn: false};
   }
   
   handleLoginClick() {
      this.setState({isLoggedIn: true});
   }
   
   handleLogoutClick() {
      this.setState({isLoggedIn: false});
   }
   
   render() {
      const isLoggedIn = this.state.isLoggedIn;
      let button;
      
      if (isLoggedIn) {
         button = <LogoutButton onClick={this.handleLogoutClick} />;
      } else {
         button = <LoginButton onClick={this.handleLoginClick} />
      }
      
      return (
         <div>
            <Greeting isLoggedIn={isLoggedIn} />
            {button}
         </div>
      );
   }
}

ReactDOM.render(
   <LoginControl />,
   document.getElementById('root')
);
```

[코드 실행 확인 링크](https://codepen.io/gaearon/pen/QKzAgB?editors=0010)

<br>

- While declaring a variable and using an `if` statement is a fine way to conditionally render a component, sometimes you might want to use a shorter syntax.
  - 변수를 선언하고 `if` 문을 사용하는 것은 컴포넌트를 조건부로 렌더링 하는 좋은 방법이지만, 더 짧은 구문을 사용하고자 할 수도 있다.
- There are a few ways to inline conditions in JSX explained below.
  - 아래에서는 JSX의 조건을 inline으로 처리하는 몇 가지 방법을 설명한다.

<br>

## Inline If with Logical && Operator

###### 논리 연산자 &&를 사용해서 if를 inline으로 처리하기

<br>

- You may [embed any expressions in JSX](https://reactjs.org/docs/introducing-jsx.html#embedding-expressions-in-jsx) by wrapping them in curly braces.
  - 중괄호로 묶어서 [JSX에 모든 표현식을 포함](https://reactjs.org/docs/introducing-jsx.html#embedding-expressions-in-jsx)시킬 수 있다.
- This includes the JavaScript logical `&&` operator.
  - 여기에는 JavaScript 논리 연산자 `&&`가 포함된다.
- It can be handy for conditionally including an element:
  - 이 연산자는 조건에 따라 element를 포함시킬 때 유용하다.

```react
function Mailbox(props) {
   const unreadMessages = props.unreadMessages;
   return (
      <div>
         <h1>Hello!</h1>
         {unreadMessages.length > 0 &&
            <h2>
               You have {unreadMessages.length} unread messages.
            </h2>
         }
      </div>
   );
}

const messages = ['React', 'Re: React', 'Re:Re: React'];

ReactDOM.render(
   <Mailbox unreadMessages={messages} />,
   document.getElementById('root')
);
```

[코드 실행 확인 링크](https://codepen.io/gaearon/pen/ozJddz?editors=0010)

<br>

- It works because in JavaScript, `true && expression` always evaluates to `expression`, and `false && expression` always evaluates to `false`.
  - JavaScript에서 `true && expression`은 항상 `expression`으로 평가되고, `false && expression`은 항상 `false`로 평가되기 때문에 동작한다.

<br>

- Therefore, if the condition is `true`, the element right after `&&` will appear in the output.
  - 따라서 조건이 `true`면, `&&` 다음에 오는 element가 출력에 표시된다.
- If it is `false`, React will ignore and skip it.
  - `false`면, React는 이를 무시하고 건너뛴다.

------

<br>

## Inline If-Else with Conditional Operator

###### 조건 연산자를 사용해서 if-else를 inline으로 처리하기

<br>

- Another method for conditionally rendering elements inline is to use the JavaScript conditional operator [condition ? true : false](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Conditional_Operator).
  - element 조건부 렌더링을 인라인 처리하는 또 다른 방법은 JavaScript 조건부 연산자를 사용하는 것이다.
  - [condition ? true : false](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Conditional_Operator)

<br>

- In the example below, we use it to conditionally render a small block of text.
  - 아래 예제에서는 조건부 연산자를 사용해서 작은 텍스트 블록을 조건에 따라 렌더링 한다.

```react
render() {
   const isLoggedIn = this.state.isLoggedIn;
   return (
      The user is <b>{isLoggedIn ? 'currently' : 'not'}</b> logged in.
   );
}
```

<br>

- It can also be used for larger expressions although it is less obvious what's going on:
  - 조건부 연산자를 더 큰 표현식에 사용할 수도 있지만, 무슨 일이 일어나는지 다소 불분명해질 수 있다.

```react
render() {
   const isLoggedIn = this.state.isLoggedIn;
   return (
      <div>
         {isLoggedIn ? (
            <LogoutButton onClick={this.handleLogoutClick} />
            ) : (
            <LoginButton onClick={this.handleLoginClick} />
         )}
      </div>
   );
}
```

<br>

- Just like in JavaScript, it is up to you to choose an appropriate style based on what you and your team consider more readable.
  - JavaScript와 마찬가지로, 적절한 스타일을 선택하는 것은 당신에게 달려 있다.
- Also remember that whenever conditions become too complex, it might be a good time to [extract a component](https://reactjs.org/docs/components-and-props.html#extracting-components).
  - 조건이 너무 복잡해진다면, [컴포넌트를 분리](https://reactjs.org/docs/components-and-props.html#extracting-components)하는 것이 좋다.

<br>

## Preventing Component from Rendering

###### 컴포넌트가 렌더링 되지 않도록 방지하기

<br>

- In rare cases you might want a component to hide itself even though it was rendered by another component.
  - 드문 경우이지만, 다른 컴포넌트에 의해 렌더링 되었더라도 해당 컴포넌트를 숨겨야 할 때가 있다.
- To do this return `null` instead of its render output.
  - 이렇게 하려면, 해당 렌더링 출력 대신 `null`을 반환한다.

<br>

- In the example below, the `<WarningBanner />` is rendered depending on the value of the prop called `warn`.
  - 아래 예제에서, `warn`이라는 prop의 값에 따라 `<WarningBanner />`가 렌더링 된다.
- If the value of the prop is `false`, then the component does not render:
  - prop의 값이 `false`라면, 컴포넌트가 다음 렌더링을 실행하지 않는다.

```react
function WarningBanner(props) {
   if (!props.warn) {
      return null;
   }
   
   return (
      <div className="warning">
         Warning!
      </div>
   );
}

class Page extends React.Component {
   constructor(props) {
      super(props);
      this.state = {showWarning: true};
      this.handleToggleClick = this.handleToggleClick.bind(this);
   }
   
   handleToggleClick() {
      this.setState(state => ({
         showWarning: !state.showWarning
      }));
   }
   
   render() {
      return (
         <div>
            <WarningBanner warn={this.state.showWarning} />
            <button onClick={this.handleToggleClick}>
               {this.state.showWarning ? 'Hide' : 'Show'}
            </button>
         </div>
      );
   }
}

ReactDOM.render(
   <Page />,
   document.getElementById('root')
);
```

[코드 실행 확인 링크](https://codepen.io/gaearon/pen/Xjoqwm?editors=0010)

<br>

- Returning `null` from a component's `render` method does not affect the firing of the component's lifecycle methods.
  - 컴포넌트의 `render` 메소드에서 `null`을 반환해도 컴포넌트의 lifecycle 메소드가 실행되는 데 영향을 주지 않는다.
- For instance `componentDidUpdate` will still be called.
  - 예를 들어 `componentDidUpdate`는 여전히 호출된다.

------

<br>
