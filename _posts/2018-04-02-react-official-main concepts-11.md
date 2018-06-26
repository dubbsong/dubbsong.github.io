---
layout: post
title: "공식 리액트 문서 번역 - 11. Composition vs Inheritance (Main Concepts)"
categories: react
tags: react
---

[공식 리액트 문서 링크](https://reactjs.org/docs/composition-vs-inheritance.html)

<br>

## Composition vs Inheritance

###### composition vs 상속

<br>

- ###### React has a powerful composition model, and we recommend using composition instead of inheritance to reuse code between components.

  - ###### React는 강력한 합성 모델을 가지고 있고, 상속 대신 합성을 사용해서 컴포넌트 간에 코드를 재사용하는 것이 좋다.

<br>

- In this section, we will consider a few problems where developers new to React often reach for inheritance, and show how we can solve them with composition.
  - 이 섹션에서는, React에 익숙하지 않은 개발자가 상속을 위해 자주 도달하는 몇 가지 문제를 살펴보고, composition을 통해 문제를 해결할 수 있는 방법을 보여준다.

------

<br>

### Containment

- Some components don't know their children ahead of time.
  - 일부 컴포넌트는 자식을 미리 알지 못한다.
- This is especially common for components like `Sidebar` or `Dialog` that represent generic "boxes".
  - 이는 일반적인 "boxes"를 나타내는 `Sidebar`나 `Dialog` 같은 컴포넌트에 특히 일반적이다.

<br>

- We recommend that such components use the special `children` prop to pass children elements directly into their output:
  - 이러한 컴포넌트는 특수한 `children` prop을 사용해서 자식 element를 출력에 직접 전달하는 것이 좋다.

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
  - 이렇게 하면, 다른 컴포넌트가 JSX를 중첩해서 임의의 자식을 전달할 수 있다.

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

[CodePen에서 시도](https://codepen.io/gaearon/pen/ozqNOV?editors=0010)

<br>

- Anything inside the `<FancyBorder>` JSX tag gets passed into the `FancyBorder` component as a `children` prop.
  - `<FancyBorder` JSX 태그 안에 있는 것은 `FancyBorder` 컴포넌트에 자식 prop으로 전달된다.
- Since `FancyBorder` renders `{props.children}` inside a `<div>`, the passed elements appear in the final output.
  - `FancyBorder`는 `{props.children}`을 `<div>` 안에 렌더링 하므로, 전달된 element는 최종 출력에 나타난다.

<br>

- While this is less common, sometimes you might need multiple "holes" in a component.
  - 일반적이지는 않지만, 가끔 컴포넌트에 여러 개의 "holes"가 필요할 수 있다.
- In such cases you may come up with your own convention instead of using `children`:
  - 그러한 경우, `children`을 사용하는 대신, 자신의 convention을 제안할 수 있다.

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

[CodePen에서 시도](https://codepen.io/gaearon/pen/gwZOJp?editors=0010)

<br>

- React elements like `<Contacts />` and `<Chat />` are just objects, so you can pass them as props like any other data.
  - `<Contacts />`와 `<Chat />`과 같은 React element는 단지 객체이므로, 다른 데이터와 마찬가지로 props를 전달할 수 있다.
- This approach may remind you of "slots" in other libraries but there are no limitations on what you can pass as props in React.
  - 이 접근법은 다른 라이브러리의 "slots"를 생각나게 할 수 있지만, React에서 props로 전달할 수 있는 것에는 제한이 없다.

------

<br>

### Specialization

- Sometimes we think about components as being "special cases" of other components.
  - 때때로 컴포넌트가 다른 컴포넌트의 "특별한 경우"라고 생각한다.
- For example, we might say that a `WelcomeDialog` is a special case of `Dialog`.
  - 예를 들어, `WelcomeDialog`는 `Dialog`의 특별한 경우라고 말할 수 있다.

<br>

- In React, this is also achieved by composition, where a more "specific" component renders a more "generic" one and configures it with props:
  - React에서 이것은 composition에 의해 달성된다.
  - 더 "구체적인" 컴포넌트가 더 "일반적인" 컴포넌트를 렌더링 하고, 이를 props로 설정한다.

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

[CodePen에서 시도](https://codepen.io/gaearon/pen/kkEaOZ?editors=0010)

<br>

- Composition works equally well for components defined as classes:
  - composition은 클래스로 정의된 컴포넌트에도 똑같이 적용된다.

```react
function Dialog(props) {
   return (
   	<FancyBorder color="blue">
      	<h1 className="Dialog-title">
         	{props.title}
         </h1>
         <p className="Dialog-message">
         	{props.children}
         </p>
      </FancyBorder>
   );
}

class SignupDialog extends React.Component {
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
```

[CodePen에서 시도](https://codepen.io/gaearon/pen/gwZbYa?editors=0010)

------

<br>

### So What About Inheritance?

###### 상속은 어떨까?

<br>

- At Facebook, we use React in thousands of components, and we haven't found any use cases where we would recommend creating component inheritance hierarchies.
  - Facebook에서는, 수천 개의 컴포넌트에서 React를 사용하며, 컴포넌트 상속 계층 구조를 만드는 것이 권장되는 사용 사례는 찾지 못했다.

<br>

- Props and composition give you all the flexibility you need to customize a component's look and behavior in an explicit and safe way.
  - props와 composition은 명시적이고 안전한 방법으로 컴포넌트의 모양과 동작을 사용자 정의하는 데 필요한 모든 유연성을 제공한다.
- Remember that components may accept arbitrary props, including primitive values, React elements, or functions.
  - 컴포넌트는 초기 값, React element 또는 함수를 포함하는 임의의 props를 받을 수 있다.

<br>

- If you want to reuse non-UI functionality between components, we suggest extracting it into a separate JavaScript module.
  - 컴포넌트 간에 UI 이외의 함수를 재사용하려면, 별도의 JavaScript 모듈로 추출하는 것이 좋다.
- The components may import it and use that function, object, or a class, without extending it.
  - 컴포넌트는 이를 확장하지 않고 해당 함수 또는 클래스를 가져오거나 사용한다.

<br>