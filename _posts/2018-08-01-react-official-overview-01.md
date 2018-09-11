---
layout: post
title: "01. React란 무엇인가? (Overview)"
categories: react
---

###### [React 공식 문서](https://reactjs.org/tutorial/tutorial.html#what-is-react) 번역

<br>

# What Is React?

###### React란 무엇인가?

<br>

- React is a declarative, efficient, and flexible JavaScript library for building user interfaces.
  - React는 사용자 인터페이스를 빌드하기 위한 JavaScript 라이브러리이다.
  - 선언적이고, 효율적이며, 유연하다.
- It lets you compose complex UIs from small and isolated pieces of code called "components".
  - React를 사용하면 "컴포넌트"라는 작고 분리된 코드 조각으로 복잡한 UI를 작성할 수 있다.

<br>

- React has a few different kinds of components, but we'll start with `React.Component` subclasses:
  - React에는 몇 가지 다른 종류의 컴포넌트가 있지만, `React.Component` subclass로 시작해보자.

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

// 사용 예: <ShoppingList name="Mark" />
```

<br>

- We'll get to the funny XML-like tags soon.
  - 곧 XML과 유사한 재미있는 태그를 사용할 것이다.
- We use components to tell React what we want to see on the screen.
  - 화면에서 보고 싶은 것은, 컴포넌트를 사용해서 React에게 알려준다.
- When our data changes, React will efficiently update and re-render our components.
  - 데이터가 변경되면, React는 효율적으로 업데이트를 하고, 컴포넌트를 다시 렌더링 한다.

<br>

- Here, ShoppingList is a `React component class`, or `React component type`.
  - 여기서 ShoppingList는 `React 컴포넌트 class` 또는 `React 컴포넌트 타입`이다.
- A component takes in parameters, called `props` (short for "properties"), and returns a hierarchy of views to display via the `render` method.
  - 컴포넌트는 `props`("properties"의 약자)라는 매개변수를 가져온다.
  - 그리고 `render` 메소드를 통해 나타낼 view의 계층 구조를 반환한다.

<br>

- The `render` method returns a *description* of what you want to see on the screen.
  - `render` 메소드는 화면에 보여줄 것에 대한 *description*을 반환한다.
- React takes the description and displays the result.
  - React는 description을 가져오고, 결과를 보여준다.
- In particular, `render` returns a `React element`, which is a lightweight description of what to render.
  - 특히, `render`는 `React element`를 반환한다.
  - 이는 렌더링 할 것에 대한 간단한 description이다.
- Most React developers use a special syntax called "JSX" which makes these structures easier to write.
  - 대부분의 React 개발자는 "JSX"라는 특별한 구문을 사용해서, 이러한 구조를 보다 쉽게 작성한다.
- The `<div />` syntax is transformed at build time to `React.createElement('div')`.
  - `<div />` 구문은 빌드 시에 `React.createElement('div')`로 변형된다.
- The example above is equivalent to:
  - 위의 예제는 다음과 같다.

```react
React.createElement(
   "div",
   { className: "shopping-list" },
   React.createElement(
      "h1",
      null,
      "Shopping List for ",
      props.name
   ),
   React.createElement(
      "ul",
      null,
      React.createElement(
         "li",
         null,
         "Instagram"
      ),
      React.createElement(
         "li",
         null,
         "WhatsApp"
      ),
      React.createElement(
         "li",
         null,
         "Oculus"
      )
   )
);
```

<br>

- If you're curious, `createElement()` is described in more detail in the [API reference](https://reactjs.org/docs/react-api.html#createelement), but we won't be using it in this tutorial.
  - `createElement()`에 대한 자세한 내용은 [API reference](https://reactjs.org/docs/react-api.html#createelement)에서 다룬다.
  - 하지만 이 튜토리얼에서는 사용하지 않을 것이다.
- Instead, we will keep using JSX.
  - 대신, JSX를 계속 사용할 것이다.

<br>

- JSX comes with the full power of JavaScript.
  - JSX는 JavaScript의 모든 기능을 제공한다.
- You can put *any* JavaScript expressions within braces inside JSX.
  - JSX 내의 중괄호 안에 JavaScript 표현식을 넣을 수 있다.
- Each React element is a JavaScript object that you can store in a variable or pass around in your program.
  - 각 React element는 변수에 저장하거나, 프로그램에서 전달할 수 있는 JavaScript 객체이다.

<br>

- The `ShoppingList` component above only renders built-in DOM components like `<div />` and `<li />`.
  - 위의 `ShoppingList` 컴포넌트는 `<div />`나 `<li />`와 같은 내장된 DOM 컴포넌트만 렌더링 한다.
- But you can compose and render custom React components too.
  - 하지만 사용자 정의 React 컴포넌트도 작성하고 렌더링 할 수 있다.
- For example, we can now refer to the whole shopping list by writing `<ShoppingList />`.
  - 예를 들어, `<ShoppingList />`를 작성해서 전체 쇼핑 리스트를 참조할 수 있다.
- Each React component is encapsulated and can operate independently; this allows you to build complex UIs from simple components.
  - 각 React 컴포넌트는 캡슐화되어 독립적으로 작동할 수 있다.
  - 이를 통해 간단한 컴포넌트로 복잡한 UI를 빌드 할 수 있다.

------

<br>