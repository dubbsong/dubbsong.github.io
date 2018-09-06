---
layout: post
title: "리액트 공식 문서 번역 - 04. 컴포넌트와 props (Main Concepts)"
categories: react
tags: React
---

###### [React 공식 문서](https://reactjs.org/docs/components-and-props.html) 번역

<br>

# React: Components and Props

###### 컴포넌트와 props

<br>

- Components let you split the UI into independent, reusable pieces, and think about each piece in isolation.
  - 컴포넌트를 사용해서 UI를 독립적이고 재사용 가능한 부분으로 분리하고, 각 부분을 개별적으로 생각할 수 있다.
- You can find a [detailed component API reference here](https://reactjs.org/docs/react-component.html).
  - [자세한 컴포넌트 API 참조는 여기](https://reactjs.org/docs/react-component.html)에서 찾을 수 있다.

<br>

- Conceptually, components are like JavaScript functions.
  - 개념상으로 컴포넌트는 JavaScript 함수와 같다.
- They accept arbitrary inputs (called "props") and return React elements describing what should appear on the screen.
  - 컴포넌트는 임의의 입력("props"라고 한다)을 받아들이고, 무엇이 화면에 나타나야 하는지를 설명하는 React element를 반환한다.

------

<br>

## Functional and Class Components

###### 함수형 컴포넌트와 class 컴포넌트

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
  - 이러한 컴포넌트는 말 그대로 JavaScript 함수이기 때문에 "함수형"이라고 한다.

<br>

- You can also use an [ES6 class](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Classes) to define a component.
  - [ES6 class](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Classes)를 사용해서 컴포넌트를 정의할 수도 있다.

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
  - class에는 [다음 섹션](https://reactjs.org/docs/state-and-lifecycle.html)에서 논의할 몇 가지 추가 기능이 있다.
- Until then, we will use functional components for their conciseness.
  - 그때까지 간결함을 위해 함수형 컴포넌트를 사용할 것이다.

------

<br>

## Rendering a Component

###### 컴포넌트 렌더링 하기

<br>

- Previously, we only encountered React elements that represent DOM tags:
  - 이전에는 DOM 태그를 나타내는 React element만 있었다.

```react
const element = <div />;
```

<br>

- However, elements can also represent user-defined components:
  - 하지만 element는 사용자 정의 컴포넌트를 나타낼 수도 있다.

```react
const element = <Welcome name="Sara" />;
```

<br>

- When React sees an element representing a user-defined component, it passes JSX attributes to this component as a single object.
  - React가 사용자 정의 컴포넌트를 나타내는 element를 볼 때, JSX 속성을 이 컴포넌트에 하나의 객체로 전달한다.
- We call this object "props".
  - 이 객체를 "props"라고 한다.

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

[코드 실행 확인 링크](https://reactjs.org/redirect-to-codepen/components-and-props/rendering-a-component)

<br>

- Let's recap what happens in this example:
  - 이 예제에서 일어나는 일을 요약해보자.

<br>

1. We call `ReactDOM.render()` with the `<Welcome name="Sara" />` element.
   - `ReactDOM.render()`를 `<Welcome name="Sara" />` element와 함께 호출한다.
2. React calls the `Welcome` component with `{name: 'Sara'}` as the props.
   - React는 `{name: 'Sara'}`가 있는  `Welcome` 컴포넌트를 props로 호출한다.
3. Our `Welcome` component returns a `<h1>Hello, Sara</h1>` element as the result.
   - `Welcome` 컴포넌트는 `<h1>Hello, Sara</h1>` element를 결과로 반환한다.
4. ReactDOM efficiently updates the DOM to match `<h1>Hello, Sara</h1>`.
   - ReactDOM은 `<h1>Hello, Sara</h1>`과 일치하도록 DOM을 효율적으로 업데이트한다.

<br>

> Note: Always start component names with a capital letter.
>
> 항상 대문자로 컴포넌트 이름을 시작해라.

> React treats components starting with lowercase letters as DOM tags.
>
> React는 소문자로 시작하는 컴포넌트를 DOM 태그로 처리한다.

> For example, `<div />` represents an HTML div tag, but `<Welcome>` represents a component and requires `Welcome` to be in scope.
>
> 예를 들어, `<div />`는 HTML div 태그를 나타내지만, `<Welcome>`은 컴포넌트를 나타내며, `Welcome`이 범위에 있어야 한다.

> You can read more about the reasoning behind this convention [here](https://reactjs.org/docs/jsx-in-depth.html#user-defined-components-must-be-capitalized).
>
> 이 [규칙](https://reactjs.org/docs/jsx-in-depth.html#user-defined-components-must-be-capitalized)에 대한 자세한 내용은 여기를 참조해라.

------

<br>

## Composing Components

###### 컴포넌트 구성하기

<br>

- Components can refer to other components in their output.
  - 컴포넌트는 출력에서 다른 컴포넌트를 참조할 수 있다.
- This lets us use the same component abstraction for any level of detail.
  - 이를 통해 모든 세부 수준에서 동일한 컴포넌트 추상화를 사용할 수 있다.
- A button, a form, a dialog, a screen: in React apps, all those are commonly expressed as components.
  - React 앱에서 모든 것(버튼, form, dialog, 화면)은 일반적으로 컴포넌트로 표현된다.

<br>

- For example, we can create an `App` component that renders `Welcome` many times:
  - 예를 들어, `Welcome`을 여러 번 렌더링 하는 `App` 컴포넌트를 만들 수 있다.

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

[코드 실행 확인 링크](https://reactjs.org/redirect-to-codepen/components-and-props/composing-components)

<br>

- Typically, new React apps have a single `App` component at the very top.
  - 일반적으로, 새로운 React 앱에는 맨 위에 하나의 `App` 컴포넌트가 있다.
- However, if you integrate React into an existing app, you might start bottom-up with a small component like `Button` and gradually work your way to the top of the view hierarchy.
  - 하지만 React를 기존 앱에 통합하는 경우, `Button`과 같은 작은 컴포넌트를 사용해서 상향식으로 시작하고, 점차적으로 view 계층의 맨 위로 이동할 수 있다.

------

<br>

## Extracting Components

###### 컴포넌트 추출하기

<br>

- Don't be afraid to split components into smaller components.
  - 컴포넌트를 더 작은 컴포넌트로 분할하는 것을 두려워하지 마라.

<br>

- For example, consider this `Comment` component:
  - 예를 들어, 이 `Comment` 컴포넌트를 고려해보자.

```react
function Comment(props) {
   return (
      <div className="Comment">
         <div className="UserInfo">
            <img className="Avatar"
               src={props.author.avaterUrl}
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

[코드 실행 확인 링크](https://reactjs.org/redirect-to-codepen/components-and-props/extracting-components)

<br>

- It accepts `author` (an object), `text` (a string), and `date` (a date) as props, and describes a comment on a social media website.
  - `author`(객체), `text`(문자열), `date`(날짜)를 props로 받아들이고, 소셜 미디어 웹사이트에 대한 comment를 설명한다.

<br>

- This component can be tricky to change because of all the nesting, and it is also hard to reuse individual parts of it.
  - 이 컴포넌트는 모든 중첩으로 인해 변경하기가 까다로울 수 있으며, 각 부분을 재사용하기도 어렵다.
- Let's extract a few components from it.
  - 여기에서 몇 가지 컴포넌트를 추출해보자.

<br>

- First, we will extract `Avatar`:
  - 먼저, `Avatar`를 추출한다.

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
  - `Avatar`는 `Comment` 안에 렌더링 되고 있다는 것을 알 필요가 없다.
- This is why we have given its prop a more generic name: `user` rather than `author`.
  - 이것이 prop에 더 일반적인 이름을 부여한 이유이다.
  - (`author`가 아닌 `user`)

<br>

- We recommend naming props from the component's own point of view rather than the context in which it is being used.
  - 컴포넌트가 사용되는 상황이 아니라, 컴포넌트 자체의 관점에서 props의 이름을 지정하는 게 좋다.

<br>

- We can now simplify `Comment` a tiny bit:
  - 이제 `Comment`를 조금 단순화할 수 있다.

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
  - 다음으로, 사용자 이름 옆에 `Avatar`를 렌더링 하는 `UserInfo` 컴포넌트를 추출한다.

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
  - 이를 통해 `Comment`를 더욱 단순화할 수 있다.

```react
function formatDate(date) {
   return date.toLocaleDateString();
}

function Avatar(props) {
   return (
      <img className="Avatar"
         src={props.user.avatarUrl}
         alt={props.user.name}
      />
   );
}

function UserInfo(props) {
   return (
      <div className="UserInfo">
         <Avatar user={props.user} />
         <div className="UserInfo-name">{props.user.name}</div>
      </div>
   );
}

function Comment(props) {
   return (
      <div className="Comment">
         <UserInfo user={props.author} />
         <div className="Comment-text">{props.text}</div>
         <div className="Comment-date">
            {formatDate(props.date)}
         </div>
      </div>
   );
}

const comment = {
   date: new Date(),
   text: 'I hope you enjoy learning React!',
   author: {
      name: 'Hello Kitty',
      avatarUrl: 'http://placekitten.com/g/64/64',
   },
};

ReactDOM.render(
   <Comment
      date={comment.date}
      text={comment.text}
      author={comment.author}
   />,
   document.getElementById('root')
);
```

[코드 실행 확인 링크](https://reactjs.org/redirect-to-codepen/components-and-props/extracting-components-continued)

<br>

- Extracting components might seem like grunt work at first, but having a palette of reusable components pays off in larger apps.
  - 컴포넌트를 추출하는 것은 처음에는 쓸 데 없는 일처럼 보일 수 있지만, 재사용 가능한 컴포넌트 팔레트를 사용하면 대규모 앱에서 유용하다.
- A good rule of thumb is that if a part of your UI is used several times (`Button`, `Panel`, `Avatar`), or is complex enough on its own (`App`, `FeedStory`, `Comment`), it is a good candidate to be a reusable component.
  - 경험적으로 좋은 법칙은, UI의 일부가 여러 번(`Button`, `Panel`, `Avatar`) 사용되거나, 자체적으로(`App`, `FeedStory`, `Comment`) 충분히 복잡하다면, 재사용 가능한 컴포넌트가 될 수 있는 좋은 후보라는 것이다.

------

<br>

## Props are Read-Only

###### props는 읽기 전용이다

<br>

- Whether you declare a component [as a function or a class](https://reactjs.org/docs/components-and-props.html#functional-and-class-components), it must never modify its own props.
  - 컴포넌트를 함수로 선언하든, class로 선언하든, 자체 props를 절대 수정하면 안 된다.
- Consider this `sum` function:
  - `sum` 함수를 고려해보자.

```react
function sum(a, b) {
   return a + b;
}
```

<br>

- Such functions are called ["pure"](https://en.wikipedia.org/wiki/Pure_function) because they do not attempt to change their inputs, and always return the same result for the same inputs.
  - 이러한 함수를 ["순수"](https://en.wikipedia.org/wiki/Pure_function) 함수라고 한다.
  - 입력을 변경하려고 시도하지 않고, 항상 동일한 입력에 대해 동일한 결과를 반환하기 때문이다.

<br>

- In contrast, this function is impure because it changes its own input:
  - 대조적으로, 함수는 자체 입력을 변경하기 때문에 순수하지 않다.

```react
function withdraw(account, amount) {
   account.total -= amount;
}
```

<br>

- React is pretty flexible but it has a single strict rule:
  - React는 꽤 유연하지만, 하나의 엄격한 규칙이 있다.

<br>

> `All React components must act like pure functions with respect to their props.`
>
> `모든 React 컴포넌트는 props와 관련해서 순수 함수로 작동해야 한다.`

<br>

- Of course, application UIs are dynamic and change over time.
  - 물론 앱 UI는 동적이며, 시간이 지남에 따라 변경된다.
- State allows React components to change their output over time in response to user actions, network responses, and anything else, without violating this rule.
  - state는 React 컴포넌트가 규칙을 위반하지 않고 시간이 지남에 따라 출력을 변경할 수 있게 한다.
  - (사용자 활동, 네트워크 응답 등등)

------

<br>