---
layout: post
title: "리액트 공식 문서 번역 - 11. Composition vs Inheritance (Main Concepts)"
categories: react
tags: React
---

###### [React 공식 문서](https://reactjs.org/docs/composition-vs-inheritance.html) 번역

<br>

# React: Composition vs Inheritance

###### 합성 vs 상속

<br>

- React has a powerful composition model, and we recommend using composition instead of inheritance to reuse code between components.
  - React에는 강력한 합성 모델(composition model)이 있다.
  - 상속(inheritance) 대신 합성을 사용해서 컴포넌트 간 코드를 재사용하는 것이 좋다.

<br>

- In this section, we will consider a few problems where developers new to React often reach for inheritance, and show how we can solve them with composition.
  - 이 섹션에서는, React에 익숙하지 않은 개발자가 상속을 위해 종종 도달하는 몇 가지 문제를 살펴보고, 합성을 사용해서 문제를 해결할 수 있는 방법을 보여준다.

------

<br>

## Containment

###### 방지

<br>

- Some components don't know their children ahead of time.
  - 일부 컴포넌트는 children을 미리 알지 못한다.
- This is especially common for components like `Sidebar` or `Dialog` that represent generic "boxes".
  - 이는 일반적인 "상자"를 타나내는 `Sidebar`나 `Dialog`와 같은 컴포넌트에 특히 일반적이다.

<br>

- We recommend that such components use the special `children` prop to pass children elements directly into their output:
  - 이러한 컴포넌트는 특별한 `children` prop을 사용해서 children element를 출력에 직접 전달하는 것이 좋다.

```react
function FancyBorder(props) {
   return (
      <div className={'FancyBorder FancyBorder-' + props.color}>
         {props.children}
      </div>
   );
}
```

<br>

- This lets other components pass arbitrary children to them by nesting the JSX:
  - 이렇게 하면, JSX를 중첩해서 다른 컴포넌트가 임의의 children을 전달할 수 있다.

```react
function WelcomeDialog() {
   return (
      <FancyBorder color="blue">
         <h1 className="Dialog-title">
            Welcome
         </h1>
         <p className="Dialog-message">
            Thank you for visiting our spacecraft!
         </p>
      </FancyBorder>
   );
}
```

[코드 실행 확인 링크](https://codepen.io/gaearon/pen/ozqNOV?editors=0010)

<br>

- Anything inside the `<FancyBorder>` JSX tag gets passed into the `FancyBorder` component as a `children` prop.
  - `<FancyBorder>` JSX 태그 내에 있는 것은 `FancyBorder` 컴포넌트에 `children` prop으로 전달된다.
- Since `FancyBorder` renders `{props.children}` inside a `<div>`, the passed elements appear in the final output.
  - `FancyBorder`는 `{props.children}`을 `<div>` 내에 렌더링 하므로, 전달된 element는 마지막 출력에 나타난다.

<br>

- While this is less common, sometimes you might need multiple "holes" in a component.
  - 일반적이지는 않지만, 종종 여러 개의 "구멍"이 컴포넌트에 필요할 수 있다.
- In such cases you may come up with your own convention instead of using `children`:
  - 이러한 경우, `children`을 사용하는 대신 자신의 convention을 생각할 수 있다.

```react
function SplitPane(props) {
   return (
      <div className="SplitPane">
         <div className="SplitPane-left">
            {props.left}
         </div>
         <div className="SplitPane-right">
            {props.right}
         </div>
      </div>
   );
}

function App() {
   return (
      <SplitPane
         left={
            <Contacts />
         }
         right={
            <Chat />
         } />
   );
}
```

[코드 실행 확인 링크](https://codepen.io/gaearon/pen/gwZOJp?editors=0010)

<br>

- React elements like `<Contacts />` and `<Chat />` are just objects, so you can pass them as props like any other data.
  - `<Contacts />`와 `<Chat />`과 같은 React element는 그냥 객체이므로, 다른 데이터처럼 props로 전달할 수 있다.
- This approach may remind you of "slots" in other libraries but there are no limitations on what you can pass as props in React.
  - 이 접근법은 "slot"을 생각나게 할 수 있지만, React에서 props로 전달할 수 있는 것에는 제한이 없다.

------

<br>

## Specialization

###### 특별화

<br>

- Sometimes we think about components as being "special cases" of other components.
  - 종종 어떤 컴포넌트가 다른 컴포넌트의 "특별한 경우"라고 생각한다.
- For example, we might say that a `WelcomeDialog` is a special case of `Dialog`.
  - 예를 들어, `WelcomeDialog`는 `Dialog`의 특별한 경우라고 말할 수 있다.

<br>

- In React, this is also achieved by composition, where a more "specific" component renders a more "generic" one and configures it with props:
  - React에서 이는 합성(composition)에 의해 이루어지기도 한다.
  - 더 "구체적인" 컴포넌트가 "일반적인" 컴포넌트를 렌더링 하고, props로 설정한다.

```react
function Dialog(props) {
   return (
      <FancyBorder color="blue">
         <h1 className="Dialog-title">
            {props.title}
         </h1>
         <p className="Dialog-message">
            {props.message}
         </p>
      </FancyBorder>
   );
}

function WelcomeDialog() {
   return (
      <Dialog
         title="Welcome"
         message="Thank you for visiting our spacecraft!" />
   );
}
```

[코드 실행 확인 링크](https://codepen.io/gaearon/pen/kkEaOZ?editors=0010)

<br>

- Composition works equally well for components defined as classes:
  - 합성(composition)은 클래스로 정의된 컴포넌트에도 동일하게 작동한다.

```react
function FancyBorder(props) {
   return (
      <div className={'FancyBorder FancyBorder-' + props.color}>
         {props.children}
      </div>
   );
}

function Dialog(props) {
   return (
      <FancyBorder color="blue">
         <h1 className="Dialog-title">
            {props.title}
         </h1>
         <p className="Dialog-message">
            {props.message}
         </p>
         {props.children}
      </FancyBorder>
   );
}

class SignUpDialog extends React.Component {
   constructor(props) {
      super(props);
      this.handleChange = this.handleChange.bind(this);
      this.handleSignUp = this.handleSignUp.bind(this);
      this.state = {login: ''};
   }
   
   render() {
      return (
         <Dialog title="Mars Exploration Program"
            message="How should we refer to you?">
            <input value={this.state.login}
               onChange={this.handleChange} />
            
            <button onClick={this.handleSignUp}>
               Sign Me Up!
            </button>
         </Dialog>
      );
   }
   
   handleChange(e) {
      this.setState({login: e.target.value});
   }
   
   handleSignUp() {
      alert(`Welcome aboard, ${this.state.login}!`);
   }
}

ReactDOM.render(
   <SignUpDialog />,
   document.getElementById('root')
);
```

[코드 실행 확인 링크](https://codepen.io/gaearon/pen/gwZbYa?editors=0010)

------

<br>

## So What About Inheritance?

###### 그러면 상속은?

<br>

- At Facebook, we use React in thousands of components, and we haven't found any use cases where we would recommend creating component inheritance hierarchies.
  - Facebook에서는, 수천 개의 컴포넌트에서 React를 사용한다.
  - 컴포넌트를 상속 계층 구조로 만드는 것이 권장되는 사용 사례는 찾지 못했다.

<br>

- Props and composition give you all the flexibility you need to customize a component's look and behavior in an explicit and safe way.
  - props와 합성(composition)은 명시적이고 안전한 방법으로 컴포넌트의 모양과 동작을 사용자 정의하는 데 필요한 모든 유연함을 제공한다.
- Remember that components may accept arbitrary props, including primitive values, React elements, or functions.
  - 컴포넌트는 primitive 값, React element, React 함수를 포함하는 임의의 props를 수용할 수 있다.

<br>

- If you want to reuse non-UI functionality between components, we suggest extracting it into a separate JavaScript module.
  - 컴포넌트 간 UI 이외의 기능을 재사용하려면, 별도의 JavaScript 모듈로 추출하는 것이 좋다.
- The components may import it and use that function, object, or a class, without extending it.
  - 컴포넌트는 이것을 import하지 않는다.
  - 함수, 객체, 클래스를 확장하지 않고 사용할 수 있다.

------

<br>