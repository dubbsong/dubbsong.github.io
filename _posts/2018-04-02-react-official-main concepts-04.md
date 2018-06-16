---
layout: post
title: "공식 리액트 문서 번역 - 04. Components and Props (Main Concepts)"
categories: react
tags: react
---

[공식 리액트 문서 링크](https://reactjs.org/docs/components-and-props.html)

<br>

## Components and Props

###### component와 props

<br>

- ###### Components let you split the UI into independent, reusable pieces, and think about each piece in isolation.

  - ###### 컴포넌트를 사용하면 UI를 독립적이고 재사용 가능한 부분으로 분리하고, 각 부분을 별개로 생각할 수 있다.

- ###### This page provides an introduction to the idea of components.

  - ###### 이 페이지는 컴포넌트에 대한 소개를 제공한다.

- ###### You can find a [detailed component API reference here](https://reactjs.org/docs/react-component.html).

  - ###### [자세한 컴포넌트 API 참조는 여기](https://reactjs.org/docs/react-component.html)서 확인할 수 있다.

<br>

- Conceptually, components are like JavaScript functions.
  - 개념상, 컴포넌트는 JavaScript 함수와 같다.
- They accept arbitrary inputs (called "props") and return React elements describing what should appear on the screen.
  - 컴포넌트는 임의의 입력("props"라 불리는)을 받아들이고, 무엇이 화면에 나타나야 하는지를 설명하는 React element를 반환한다.

------

<br>

### Functional and Class Components

###### 함수형 컴포넌트와 Class 컴포넌트

<br>

- The simplest way to define a component is to write a JavaScript function:
  - 컴포넌트를 정의하는 가장 간단한 방법은 JavaScript 함수를 작성하는 것이다.

```react
function Welcome(props) {
   return <h1>Hello, {props.name}</h1>;
}
```

<br>

- This function is a valid React component because it accepts a single "props" (which stands for properties) object argument with data and returns a React element.
  - 이 함수는 하나의 "props" 객체 인수를 데이터와 함께 받아들이고, React element를 반환하기 때문에 유효한 React 컴포넌트이다.
- We call such components "functional" because they are literally JavaScript functions.
  - 말 그대로 JavaScript 함수이기 때문에, 이러한 컴포넌트를 "함수형" 컴포넌트라고 부른다.

<br>

- You can also use an ES6 class to define a component:
  - ES6 클래스를 사용해서 컴포넌트를 정의할 수도 있다.

```react
class Welcome extends React.Component {
   render() {
      return <h1>Hello, {this.props.name}</h1>;
   }
}
```

<br>

- The above two components are equivalent from React's point of view.
  - 위의 두 컴포넌트는 React의 관점에서 동일하다.

<br>

- Classes have some additional features that we will discuss in the [next sections](https://reactjs.org/docs/state-and-lifecycle.html).
  - 클래스에는 [다음 섹션](https://reactjs.org/docs/state-and-lifecycle.html)에서 논의할 몇 가지 추가 기능이 있다.
- Until then, we will use functional components for their conciseness.
  - 그때까지, 간결함을 위해 함수형 컴포넌트를 사용할 것이다.

------

### Rendering Component

###### 컴포넌트 렌더링

<br>

- Previously, we only encountered React elements that represent DOM tags:
  - 이전에는 DOM 태그를 나타내는 React element만 있었다.

```react
const element = <div />;
```

<br>

- However, elements can also represent user-defined components:
  - 하지만, element는 사용자-정의 컴포넌트를 나타낼 수도 있다.

```react
const element = <Welcome name="Sara" />;
```

<br>

- When React sees an element representing a user-defined component, it passes JSX attributes to this component as a single object.
  - React가 사용자-정의 컴포넌트를 나타내는 element를 바라볼 때, JSX 속성을 이 컴포넌트에 단일 객체로 전달한다.
- We call this object "props".
  - 이 객체를 "props"라고 부른다.

<br>

- For example, this code renders "Hello, Sara" on the page:
  - 예를 들어, 이 코드는 페이지에 "Hello, Sara"를 렌더링 한다.

```react
function Welcome(props) {
   return <h1>Hello, {props.name}</h1>;
}

const element = <Welcome name="Sara" />;
ReactDOM.render(
	element,
   document.getElementById('root')
);
```

[CodePen에서 시도](https://codepen.io/pen?&editors=0010)

<br>

###### Let's recap what happens in this example:

###### 이 예제에서 일어나는 일을 요약해보자.

1. We call `ReactDOM.render()` with the `<Welcome name="Sara" />` element.
   - `ReactDOM.render()`를 `<Welcome name="Sara" />` element와 함께 호출한다.
2. React calls the `Welcome` component with `{name: 'Sara'}` as the props.
   - React는 `Welcome` 컴포넌트를 `{name: 'Sara'}`와 함께 props로 호출한다.
3. Our `Welcome` component returns a `<h1>Hello, Sara</h1>` element as the result.
   - `Welcome` 컴포넌트는 `<h1>Hello, Sara</h1>` element를 결과로 반환한다.
4. React DOM efficiently updates the DOM to match `<h1>Hello, Sara</h1>`.
   - React DOM은 `<h1>Hello, Sara</h1>`와 일치하도록 DOM을 효율적으로 업데이트 한다.

<br>

> **Note: Always start component names with a capital letter.**
>
> Note: 컴포넌트 이름은 항상 대문자로 시작해라.

> React treats components starting with lowercase letters as DOM tags.
>
> React는 소문자로 시작하는 컴포넌트를 DOM 태그로 처리한다.

> For example, `<div />` represents an HTML div tag, but `<Welcome />` represents a component and requires `Welcome` to be in scope.
>
> 예를 들어, `<div />`는 HTML div 태그를 나타내지만, `<Welcome />`은 컴포넌트를 나타내고, `Welcome`이 범위에 있어야 한다.

> You can read more about the reasoning behind this convention [here](https://reactjs.org/docs/jsx-in-depth.html#user-defined-components-must-be-capitalized).
>
> 이 조약에 대한 자세한 내용은 [여기](https://reactjs.org/docs/jsx-in-depth.html#user-defined-components-must-be-capitalized)를 참조해라.

------

<br>

### Composing Components

###### 컴포넌트 구성

<br>

- Components can refer to other components in their output.
  - 컴포넌트는 출력에서 다른 컴포넌트를 참조할 수 있다.
- This lets us use the same component abstraction for any level of detail.
  - 이렇게 하면, 동일한 컴포넌트 추상화를 사용할 수 있다.
- A button, a form, a dialog, a screen: in React apps, all those are commonly expressed as components.
  - 일반적으로 React 앱에서 버튼, 폼, 대화 상자, 화면 등의 모든 것은 컴포넌트로 표현된다.

<br>

- For example, we can create an `App` component that renders `Welcome` many times:
  - 예를 들어, `Welcome`을 여러 번 렌더링 하는 `App` 컴포넌트를 생성할 수 있다.

```react
function Welcome(props) {
   return <h1>Hello, {props.name}</h1>;
}

function App() {
   return (
   	<div>
      	<Welcome name="Sara" />
         <Welcome name="Cahal" />
         <Welcome name="Edite" />
      </div>
   );
}

ReactDOM.render(
	<App />,
   document.getElementById('root')
);
```

[CodePen에서 시도](https://codepen.io/pen?&editors=0010)

<br>

- Typically, new React apps have a single `App` component at the very top.
  - 일반적으로, 새로운 React 앱에는 맨 위에 단일 `App` 컴포넌트가 있다.
- However, if you integrate React into an existing app, you might start bottom-up with a small component like `Button` and gradually work your way to the top of the view hierarchy.
  - 하지만, React를 기존 앱에 통합하는 경우, `Button`과 같은 작은 컴포넌트를 사용해서 상향식으로 시작할 수 있고, 점차적으로 보기 계층의 맨 위로 이동할 수 있다.

------

<br>

### Extracting Components

###### 컴포넌트 추출

<br>

- Don't be afraid to split components into smaller components.
  - 컴포넌트를 더 작은 컴포넌트로 분할하는 것을 두려워하지 마라.

<br>

- For example, consider this `Comment` component:
  - 예를 들어, `Comment` 컴포넌트를 보자.

```react
function Comment(props) {
   return (
   	<div className="Comment">
      	<div className="UserInfo">
         	<img className="Avatar"
               src={props.author.avatarUrl}
               alt={props.author.name}
               />
            <div className="UserInfo-name">
            	{props.author.name}
            </div>
         </div>
         <div className="Comment-text">
         	{props.text}
         </div>
         <div className="Comment-date">
         	{formatDate(props.date)}
         </div>
      </div>
   );
}
```

[CodePen에서 시도](https://codepen.io/pen?&editors=0010)

<br>

- It accepts `author` (an object), `text` (a string), and `date` (a date) as props, and describes a comment on a social media website.
  - `author` (객체), `text` (문자열), `date` (날짜)를 props로 받아들이고, 소셜 미디어 웹 사이트에 대한 comment를 설명한다.

<br>

- This component can be tricky to change because of all the nesting, and it is also hard to reuse individual parts of it.
  - 이 컴포넌트는 모든 중첩으로 인해 변경하기가 까다로울 수 있으며, 각 부분을 재사용하기도 어렵다.
- Let's extract a few components from it.
  - 몇 가지 컴포넌트를 추출해보자.

<br>

- First, we will extract `Avatar`:
  - 먼저, `Avatar`를 추출할 것이다.

```react
function Avatar(props) {
   return (
   	<img className="Avatar"
         src={props.user.avatarUrl}
         alt={props.user.name}
         />
   );
}
```

<br>

- The `Avatar` doesn't need to know that it is being rendered inside a `Comment`.
  - `Avatar`는 그것이 `Comment` 안에 렌더링 된다는 것을 알 필요가 없다.
- This is why we have given its prop a more generic name: `user` rather than `author`.
  - prop에 더 일반적인 이름을 부여한 이유이다: `author` 보다는 `user`

<br>

- We recommend naming props from the component's own point of view rather than the context in which it is being used.
  - 컴포넌트가 사용되는 context보다는, 컴포넌트 자체 관점에서 props의 네이밍을 권장한다.
  - `해석이 매끄럽지 않음`

<br>

- We can now simplify `Comment` a tiny bit:
  - 이제 `Comment`를 약간 단순화할 수 있다.

```react
function Comment(props) {
   return (
   	<div className="Comment">
      	<div className="UserInfo">
         	<Avatar user={props.author} />
            <div className="UserInfo-name">
            	{props.author.name}
            </div>
         </div>
         <div className="Comment-text">
         	{props.text}
         </div>
         <div className="Comment-date">
         	{formatDate(props.date)}
         </div>
      </div>
   );
}
```

<br>

- Next, we will extract a `UserInfo` component that renders an `Avatar` next to the user's name:
  - 다음으로, 사용자 이름 옆의 `Avatar`를 렌더링 하는 `UserInfo` 컴포넌트를 추출할 것이다.

```react
function UserInfo(props) {
   return (
   	<div className="UserInfo">
      	<Avatar user={props.user} />
         <div className="UserInfo-name">
         	{props.user.name}
         </div>
      </div>
   );
}
```

<br>

- This lets us simplify `Comment` even further:
  - 이를 통해 `Comment`를 더 단순화할 수 있다.

```react
function Comment(props) {
   return (
   	<div className="Comment">
      	<UserInfo user={props.author} />
         <div className="Comment-text">
         	{props.text}
         </div>
         <div className="Comment-date">
         	{formatDate(props.date)}
         </div>
      </div>
   );
}
```

[CodePen에서 시도](https://codepen.io/pen?&editors=0010)

<br>

- Extracting components might seem like grunt work at first, but having a palette of reusable components pays off in larger apps.
  - 컴포넌트를 추출하는 것은 처음에는 쓸데없는 일처럼 보일 수 있지만, 재사용 가능한 컴포넌트 팔레트를 가지고 있으면 큰 앱에서 성과를 올릴 수 있다.
- A good rule of thumb is that if a part of your UI is used several times (`Button`, `Panel`, `Avatar`), or is complex enough on its own (`App`, `FeedStory`, `Comment`), it is a good candidate to be a reusable component.
  - 경험에 근거한 좋은 규칙은, UI의 일부가 여러 번(`Button`, `Panel`, `Avatar`) 사용되거나, 자체적으로(`App`, `FeedStory`, `Comment`) 충분히 복잡하면, 재사용 가능한 컴포넌트가 될 수 있는 좋은 후보라는 것이다.

------

<br>

### Props are Read-Only

###### 읽기 전용 props

<br>

- Whether you declare a component [as a function or a class](https://reactjs.org/docs/components-and-props.html#functional-and-class-components), it must never modify its own props.
  - 컴포넌트를 [함수나 클래스로](https://reactjs.org/docs/components-and-props.html#functional-and-class-components) 선언하든 관계없이, 자체 props를 수정하면 안 된다.
- Consider this `sum` function:
  - `sum` 함수를 보자.

```react
function sum(a, b) {
   return a + b;
}
```

<br>

- Such functions are called "pure" because they do not attempt to change their inputs, and always return the same result for the same inputs.
  - 이러한 함수를 "순수" 함수라고 한다.
  - 입력을 변경하려고 시도하지 않고, 항상 동일한 입력에 대해 동일한 결과를 반환하기 때문이다.

<br>

- In contrast, this function is impure because it changes its own input:
  - 대조적으로, 이 함수는 자체 입력을 변경하기 때문에 순수하지 않다.

```react
function withdraw(account, amount) {
   account.total -= amount;
}
```

<br>

- React is pretty flexible but it has a single strict rule:
  - React는 꽤 유연하지만, 엄격한 규칙이 하나 있다.

<br>

###### **All React components must act like pure functions with respect to their props.**

###### **모든 React 컴포넌트는 props에 대해 순수 함수로 작동해야 한다.**

<br>

- Of course, application UIs are dynamic and change over time.
  - 물론 애플리케이션 UI는 동적이며, 시간이 지남에 따라 변경된다.
- In the next section, we will introduce a new concept of "state".
  - 다음 섹션에서는, "state"라는 개념을 소개할 것이다.
- State allows React components to change their output over time in response to user actions, network responses, and anything else, without violating this rule.
  - state는 React 컴포넌트가 이 규칙을 위반하지 않고 사용자 액션, 네트워크 응답 등등 시간이 지남에 따라 출력을 변경할 수 있게 한다.

<br>