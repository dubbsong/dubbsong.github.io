---
layout: post
title: "리액트 공식 문서 번역"
categories: react
tags: React translation
---

# Tutorial: Intro To React

[React 공식 문서](https://reactjs.org/tutorial/tutorial.html)

<br>

> - Before We Start (시작하기 전에)
> - Overview (개요)
> - Lifting State Up
> - Storing A History (히스토리 저장)

------

<br>

## Before We Start

###### 시작하기 전에

<br>

### What We're Building (무엇을 만들 것인가)

- Today, we're going to build an interactive tic-tac-toe game.
  - 우리는 틱택토 게임을 만들 것이다.
- If you like, you can check out the final result here: [Final Result](https://codepen.io/gaearon/pen/gWWZgR?editors=0010)
  - 원한다면 [여기서](https://codepen.io/gaearon/pen/gWWZgR?editors=0010) 최종 결과물을 확인할 수 있다.
- Don't worry if the code doesn't make sense to you yet, or if it uses an unfamiliar syntax.
  - 아직 코드가 이해가지 않거나 문법이 친숙하지 않아도 걱정하지 마라.
- We will be learning how to build this game step by step throughout this tutorial.
  - 우리는 이 튜토리얼을 통해서 이 게임을 어떻게 만드는지 차근차근 배울 것이다.

<br>

- Try playing the game.
  - 게임을 플레이해봐라.
- You can also click on a button in the move list to go "back in time"
  - 이동 리스트에 있는 버튼을 클릭해서 돌아갈 수 있고
- and see what the board looked like just after that move was made.
  - 돌아간 후 보드가 어떻게 보이는지 볼 수 있다.

<br>

- Once you get a little familiar with the game, feel free to close that tab,
  - 게임에 익숙해지면, 마음 편히 탭을 닫고,
- as we'll start from a simpler template in the next sections.
  - 다음 섹션에서 간단한 템플릿으로 시작할 것이다.

<br>

### Prerequisites (전제 조건)

- We'll assume some familiarity with HTML and JavaScript,
  - 니가 HTML과 JavaScript에 익숙하다고 가정하지만,
- but you should be able to follow along even if you haven't used them before.
  - 전에 사용한 적이 없다 하더라도 따라올 수 있어야 한다.

<br>

- If you need a refresher on JavaScript, we recommend reading [this guide](https://developer.mozilla.org/en-US/docs/Web/JavaScript/A_re-introduction_to_JavaScript).
  - JavaScript를 다시 배워야 한다면, [이것](https://developer.mozilla.org/en-US/docs/Web/JavaScript/A_re-introduction_to_JavaScript)을 읽어보길 추천한다.
- Note that we're also using some features from ES6, a recent version of JavaScript.
  - 약간의 ES6와 최신 JavaScript도 사용할 것을 알고 있어라.
- In this tutorial, we're using [arrow functions](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/Arrow_functions), [classes](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Classes), [let](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/let), and [const](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/const) statements.
  - 이 튜토리얼에서 우리는 [화살표 함수](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/Arrow_functions), [클래스](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Classes), [let](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/let), [const](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/const) 표현법을 사용할 것이다.
- You can use the [Babel REPL](https://babeljs.io/repl/#?presets=react&code_lz=MYewdgzgLgBApgGzgWzmWBeGAeAFgRgD4AJRBEAGhgHcQAnBAEwEJsB6AwgbgChRJY_KAEMAlmDh0YWRiGABXVOgB0AczhQAokiVQAQgE8AkowAUAcjogQUcwEpeAJTjDgUACIB5ALLK6aRklTRBQ0KCohMQk6Bx4gA) to check what ES6 code compiles to.
  - ES6 코드가 어떻게 컴파일 되는지 확인하기 위해 [Babel REPL](https://babeljs.io/repl/#?presets=react&code_lz=MYewdgzgLgBApgGzgWzmWBeGAeAFgRgD4AJRBEAGhgHcQAnBAEwEJsB6AwgbgChRJY_KAEMAlmDh0YWRiGABXVOgB0AczhQAokiVQAQgE8AkowAUAcjogQUcwEpeAJTjDgUACIB5ALLK6aRklTRBQ0KCohMQk6Bx4gA)을 사용할 수 있다.

<br>

### How to Follow Along (학습하는 방법)

- There are two ways to complete this tutorial:
  - 이 튜토리얼을 완료하기 위해서는 두 가지 방법이 있다.
- you could either write the code right in the browser,
  - 브라우저에서 코드를 작성하거나,
- or you could set up a local development environment on your machine.
  - 니 컴퓨터의 로컬 개발 환경을 설정할 수 있다.
- You can choose either option depending on what you feel comfortable with.
  - 니가 편한대로 선택할 수 있다.

<br>

### If You Prefer to Write Code in the Browser (브라우저에서 코드를 작성하기 원한다면)

- This is the quickest way to get started!
  - 이것은 가장 빠르게 시작할 수 있는 방법이다.
- First, open this [starter code](https://codepen.io/gaearon/pen/oWWQNa?editors=0010) in a new tab.
  - 우선, 새 탭에 [이것](https://codepen.io/gaearon/pen/oWWQNa?editors=0010)을 열어라.
- It should display an empty tic-tac-toe field.
  - 빈 틱택토 작업 환경이 보일 것이다.
- We will be editing that code during this tutorial.
  - 이 튜토리얼을 진행하는 동안 저 코드를 수정할 것이다.

<br>

- You can now skip the next section about setting up a local development environment and head straight to the [overview](https://reactjs.org/tutorial/tutorial.html#overview).
  - 로컬 개발 환경 세팅을 스킵할 수 있으니 바로 [개요](https://reactjs.org/tutorial/tutorial.html#overview)로 가라.

<br>

### If you Prefer to Write Code in Your Editor (에디터에서 코드를 작성하기 원한다면)

- Alternatively, you can set up a project on your computer.
  - 니 컴퓨터에서 프로젝트를 세팅할 수 있다.

<br>

- Note: **this is completely optional and not required for this tutorial!**
  - 주석: 이것은 완전히 선택 사항이지 필수 사항이 아니다.

<br>

- This is more work, but lets you work from the comfort of your editor.
  - 이 방법은 손이 더 많이 가겠지만 에디터의 편리함을 누리며 작업할 수 있다.

<br>

- If you want to do it, here are the steps to follow:
  - 이 방법을 원한다면 따라야 할 몇 가지 절차가 있다.
- 1. Make sure you have a recent version of [Node.js](https://nodejs.org/en/) installed.
     - 설치된 [Node.js](https://nodejs.org/en/)가 최신 버전인지 확인해라.
- 2. Follow the [installation instructions](https://reactjs.org/docs/add-react-to-a-new-app.html) to create a new project.
     - 새로운 프로젝트를 만들기 위해 [설치 방법](https://reactjs.org/docs/add-react-to-a-new-app.html)을 따라라.

> $ npm install -g create-react-app
>
> $ create-react-app my-app

- 3. Delete all files in the `src/` folder of the new project(don't delete the folder, just its contents).
     - `src/` 폴더에 있는 모든 파일을 삭제해라(폴더는 지우지 않고, 파일만 삭제).

> $ cd my-app
>
> $ -f src/*

- 4. Add a file named `index.css` in the `src/` folder with [this CSS code](https://codepen.io/gaearon/pen/oWWQNa?editors=0100).
     - `src/` 폴더 안에 `index.css` 파일을 생성하고 [이 CSS code](https://codepen.io/gaearon/pen/oWWQNa?editors=0100)를 작성해라.
- 5. Add a file named `index.js` in the `src/` folder with [this JS code](https://codepen.io/gaearon/pen/oWWQNa?editors=0010).
     - `src/` 폴더 안에 `index.js` 파일을 생성하고 [이 JS code](https://codepen.io/gaearon/pen/oWWQNa?editors=0010)를 작성해라.
- 6. Add these three lines to the top of `index.js` in the `src/` folder:
     - `src/` 폴더 안의 `index.js` 파일 맨 위에 아래 3줄을 추가해라.

```react
// index.js

import React from 'react';
import ReactDOM from 'react-dom';
import './index.css';
```

<br>

- Now if you run `npm start` in the project folder and open `http://localhost:3000` in the browser, you should see an empty tic-tac-toe field.
  - 프로젝트 폴더 안에서 `$ npm start`를 실행하고 `http://localhost:3000`을 브라우저에서 열면, 빈 틱택토 작업환경을 볼 수 있을 것이다.

<br>

- We recommend following [these instructions](http://babeljs.io/docs/editors) to configure syntax highlighting for your editor.
  - 에디터에서 하이라이팅 문법을 설정하려면 [이 문서](http://babeljs.io/docs/editors)를 따라하기를 추천한다.

<br>

### Help, I'm Stuck! (문제 발생 시)

- If you get stuck, check out the [community support resources](https://reactjs.org/community/support.html).
  - 문제가 생겼다면, [여기](https://reactjs.org/community/support.html)를 살펴봐라.
- In particular, [Reactiflux chat](https://reactjs.org/community/support.html#reactiflux-chat) is a great way to get quick help.
  - 특히, [여기](https://reactjs.org/community/support.html#reactiflux-chat)가 빠르게 도움을 받을 수 있는 좋은 방법이다.
- If you don't get a good answer anywhere, please file an issue, and we'll help you out.
  - 어디서든 좋은 해답을 찾지 못했다면, 우리가 도와줄테니 파일을 보내달라.

<br>

- With this out of the way, let's get started!
  - 이제 시작해보자.

------

## Overview

###### 개요

<br>

### What is React? (리액트란?)

- React is a declarative, efficient, and flexible JavaScript library for building user interfaces.
  - 리액트는 유저 인터페이스를 만들기 위한 선언적이고, 효율적이며, 유연한 JS 라이브러리이다.

<br>

- React has a few different kinds of components, but we'll start with `React.Component` subclasses:
  - 리액트는 조금 여러 종류의 컴포넌트를 가지고 있지만, 우리는 서브클래스 `React.Componen`로 시작할 것이다.

<br>

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
      )
   }
}

// Example usage: <ShoppingList name="Mark" />
```

- We'll get to the funny XML-like tags in a second.
  - XML 같은 태그를 잠깐 사용할 것이다.
- Your components tell React what you want to render -
  - 작성한 컴포넌트는 니가 렌더하고 싶은 것을 리액트에게 알려준다.
- then React will efficiently update and render just the right components when your data changes.
  - 그리고 리액트는 데이터가 변경될 때 컴포넌트를 효율적으로 업데이트 하고 렌더링한다.

<br>

- Here, ShoppingList is a **React component class, **or **React component type**.
  - 여기에서, ShoppingList는 **리액트 컴포넌트 클래스**이거나 **리액트 컴포넌트 타입**이다.
- A component takes in parameters, called `props`,
  - 컴포넌트는 `props`라 불리는 파라미터를 가져오고,
- and returns a hierarchy of views to display via the `render` method.
  - `render` 메소드를 통해 나타낼 계층 구조를 반환한다.

<br>

- The `render` method returns a *description* of what you want to render,
  - `render` 메소드는 렌더링하기를 원하는 내용을 반환하고,
- and then React takes that description and renders it to the screen.
  - 리액트는 그 내용을 가져와서 스크린에 렌더링한다.
- In particular, `render` returns a **React element**, which is a lightweight description of what to render.
  - 특히, `render`는 렌더링할 간단한 내용인 **리액트 엘리먼트**를 반환한다.
- Most React developers use a special syntax called JSX which makes it easier to write these structures.
  - 대부분의 리액트 개발자들은 이 구조를 더 쉽게 작성할 수 있게 해주는 JSX라는 특별한 문법을 사용한다.
- The `<div />` syntax is transformed at build time to `React.createElement('div')`.
  - `<div />` 문법은 빌드 시에 `React.createElement('div')`로 변환된다.
- The example above is equivalent to:
  - 위의 예제는 아래와 동일하다.

```react
React.createElement(
	"div",
   { className: "shopping-list"},
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

[전체 코드 확인](https://babeljs.io/repl/#?presets=react&code_lz=DwEwlgbgBAxgNgQwM5IHIILYFMC8AiJACwHsAHUsAOwHMBaOMJAFzwD4AoKKYQgRlYDKJclWpQAMoyZQAZsQBOUAN6l5ZJADpKmLAF9gAej4cuwAK5wTXbg1YBJSswTV5mQ7c7XgtgOqEETEgAguTuYFamtgDyMBZmSGFWhhYchuAQrADc7EA)

<br>

- If you're curious, `createElement()` is described in more detail in the [API reference](https://reactjs.org/docs/react-api.html#createelement),
  - `createElement()`에 대해 더 많은 내용이 궁금하다면, [여기](https://reactjs.org/docs/react-api.html#createelement)에 자세한 설명이 있다.
- but we won't be using it directly in this tutorial.
  - 그러나 이 튜토리얼에서는 직접적으로 사용하지 않을 것이다.
- Instead, we will keep using JSX.
  - 대신에, 계속 JSX를 사용할 것이다.

<br>

- You can put any JavaScript expression within braces inside JSX.
  - JSX에서는 중괄호 안에 어느 JS 표현이든 사용할 수 있다.
- Each React element is a real JavaScript object that you can store in a variable or pass around your program.
  - 각 리액트 엘리먼트는 변수에 저장하거나 프로그램에 전달할 수 있는 실제 JS 객체이다.

<br>

- The `ShoppingList` component only renders built-in DOM components,
  - `ShoppingList` 컴포넌트는 내장된 DOM 컴포넌트에만 렌더링할 수 있다.
- but you can compose custom React components just as easily, by writing `<ShoppingList />`.
  - 하지만 `<ShoppingList>`를 작성하여 커스텀 리액트 컴포넌트를 쉽게 구성할 수 있다.
- Each component is encapsulated so it can operate independently,
  - 각 컴포넌트는 캡슐화되어 독립적으로 작동할 수 있다.
- which allows you to build complex UIs out of simple components.
  - 심플한 컴포넌트로 복잡한 UI를 구현하도록 허용한다.

<br>

### Getting Started (시작하기)

- Start with this example: [Starter Code](https://codepen.io/gaearon/pen/oWWQNa?editors=0010).
  - [여기](https://codepen.io/gaearon/pen/oWWQNa?editors=0010) 예제 코드로 시작하자.

<br>

- It contains the shell of what we're building today.
  - 이 코드는 우리가 오늘 만들 틀을 포함한다.
- We've provided the styles so you only need to worry about the JavaScript.
  - 틀을 제공하였기 때문에 JS만 신경쓰면 된다.

<br>

- In particular, we have three components:
  - 3가지 컴포넌트가 있다.

> - Square (사각형)
> - Board (보드)
> - Game (게임)

<br>

- The Square component renders a single `<button>`,
  - Square 컴포넌트는 하나의 `<button>을 렌더링한다.
- the Board renders 9 squares,
  - Board 컴포넌트는 9개의 사각형을 렌더링한다.
- and the Game component renders a board with some placeholders that we'll fill in later.
  - Game 컴포넌트는 우리가 나중에 채워야 할 몇몇의 placeholder가 있는 보드를 렌더링한다.
- None of the components are interactive at this point.
  - 이 컴포넌트들은 여기에서 아무 작용도 하지 않는다.

<br>

### Passing Data Through Props (props를 통해 데이터 전달하기)

- Just to get our feet wet, let's try passing some data from the Board component to the Square component.
  - 본격적으로 시작하기 위해 Board 컴포넌트에서 Square 컴포넌트로 데이터를 전달해 보자.

<br>

- In Board's `renderSquare` method, change the code to pass a `value` prop to the Square:
  - Board의 `renderSquare` 메소드에서 Square 컴포넌트의 prop로 `value` 값을 전달하도록 코드를 변경해라.

```react
class Board extends React.Component {
   renderSquare(i) {
      return <Square value={i} />;
   }
}
```

<br>

- Then change Square's `render` method to show that value by replacing `{/* TODO */ }` with `{this.props.value}`:
  - 그런 다음, value 값을 보여주기 위해 Square 컴포넌트의 `render` 메소드를 변경해라.
  - `{/* TODO */}`를 `{this.props.value}`로

```react
class Square extends React.Component {
   render() {
      return (
      	<button className="square">
         	{this.props.value}
         </button>
      )
   }
}
```

<br>

- Before:

![Before](/assets/img/Before.png)



<br>

- After: You should see a number in each square in the rendered output.
  - 각 사각형 안에 출력된 숫자들을 확인할 수 있다.

![After](/assets/img/After.png)



[여기까지의 코드 확인](https://codepen.io/gaearon/pen/aWWQOG?editors=0010)

<br>

### An Interactive Component (대화형 컴포넌트)

- ​





































