---
layout: post
title: "리액트 공식 문서 번역 - Before We start"
categories: react
tags: react translation
---

[React 공식 문서 링크](https://reactjs.org/tutorial/tutorial.html)

<br>

## Before We Start

###### 시작하기 전에

<br>

### What We're Building (무엇을 만들 것인가)

- Today, we're going to build an interactive tic-tac-toe game.
  - 우리는 상호작용하는 틱택토 게임을 만들 것이다.

<br>

- If you like, you can check out the final result here: [Final Result](https://codepen.io/gaearon/pen/gWWZgR?editors=0010).
  - 원한다면, [여기서](https://codepen.io/gaearon/pen/gWWZgR?editors=0010) 최종 결과물을 확인할 수 있다.
- Don't worry if the code doesn't make sense to you yet, or if it uses an unfamiliar syntax.
  - 아직 코드가 이해되지 않거나 문법이 익숙하지 않아도 걱정하지 마라.
- We will be learning how to build this game step by step throughout this tutorial.
  - 우리는 튜토리얼을 통해서 이 게임을 어떻게 빌드하는지 단계별로 배울 것이다.

<br>

- Try playing the game.
  - 게임을 플레이해봐라.
- You can also click on a button in the move list to go "back in time"
  - 이동 목록에 있는 버튼을 클릭해서 "이전"으로 되돌릴 수 있고
- and see what the board looked like just after that move was made.
  - 되돌린 후 보드가 어떻게 보이는지 볼 수 있다.

<br>

- Once you get a little familiar with the game, feel free to close that tab,
  - 게임에 익숙해지면, 편할 때 탭을 닫고,
- as we'll start from a simpler template in the next sections.
  - 다음 섹션에서 간단한 템플릿부터 시작할 것이다.

<br>

### Prerequisites (사전 준비 사항)

- We'll assume some familiarity with HTML and JavaScript,
  - 당신이 HTML과 JavaScript에 익숙하다고 가정하지만,
- but you should be able to follow along even if you haven't used them before.
  - 이전에 사용한 적이 없어도 따라올 수 있어야 한다.

<br>

- If you need a refresher on JavaScript, we recommend reading [this guide](https://developer.mozilla.org/en-US/docs/Web/JavaScript/A_re-introduction_to_JavaScript).
  - JavaScript를 다시 배워야 한다면, [이 가이드](https://developer.mozilla.org/en-US/docs/Web/JavaScript/A_re-introduction_to_JavaScript)를 읽어보길 추천한다.
- Note that we're also using some features from ES6, a recent version of JavaScript.
  - JavaScript의 최신 버전인 ES6의 일부 기능도 사용할 것이다.
- In this tutorial, we're using [arrow function](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/Arrow_functions), [classes](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Classes), [let](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/let), and [const](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/const) statements.
  - 이 튜토리얼에서, [화살표 함수](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/Arrow_functions), [클래스](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Classes), [let](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/let), [const](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/const) 표현법을 사용할 것이다.
- You can use the [Babel REPL](https://babeljs.io/repl/#?presets=react&code_lz=MYewdgzgLgBApgGzgWzmWBeGAeAFgRgD4AJRBEAGhgHcQAnBAEwEJsB6AwgbgChRJY_KAEMAlmDh0YWRiGABXVOgB0AczhQAokiVQAQgE8AkowAUAcjogQUcwEpeAJTjDgUACIB5ALLK6aRklTRBQ0KCohMQk6Bx4gA) to check what ES6 code compiles to.
  - [Babel REPL](https://babeljs.io/repl/#?presets=react&code_lz=MYewdgzgLgBApgGzgWzmWBeGAeAFgRgD4AJRBEAGhgHcQAnBAEwEJsB6AwgbgChRJY_KAEMAlmDh0YWRiGABXVOgB0AczhQAokiVQAQgE8AkowAUAcjogQUcwEpeAJTjDgUACIB5ALLK6aRklTRBQ0KCohMQk6Bx4gA)을 사용해서 ES6 코드가 컴파일 되는 것을 확인할 수 있다.

<br>

### How to Follow Along (학습하는 방법)

- There are two ways to complete this tutorial:
  - 이 튜토리얼을 완료하는 데에는 두 가지 방법이 있다.
- you could either write the code right in the browser,
  - 브라우저에서 바로 코드를 작성하거나,
- or you could set up a local development environment on your machine.
  - 컴퓨터에 로컬 개발 환경을 설정할 수 있다.
- You can choose either option depending on what you feel comfortable with.
  - 편한 정도에 따라 두 가지 옵션 중 하나를 선택할 수 있다.

<br>

#### If You Prefer to Write Code in the Browser

###### 브라우저에서 코드 작성을 원한다면

- This is the quickest way to get started!
  - 이 방법은 가장 빠르게 시작할 수 있는 방법이다.

<br>

- First, open this [starter code](https://codepen.io/gaearon/pen/oWWQNa?editors=0010) in a new tab.
  - 먼저, [시작 코드](https://codepen.io/gaearon/pen/oWWQNa?editors=0010)를 새 탭에서 연다.
- It should display an empty tic-tac-toe field.
  - 비어 있는 틱택토 필드가 보일 것이다.
- We will be editing that code during this tutorial.
  - 이 튜토리얼을 진행하는 동안 저 코드를 편집할 것이다.

<br>

- You can now skip the next section about setting up a local development environment and head straight to the [overview](https://reactjs.org/tutorial/tutorial.html#overview).
  - 이제 로컬 개발 환경 설정에 대한 다음 섹션을 건너뛰고 바로 [개요](https://reactjs.org/tutorial/tutorial.html#overview)로 넘어갈 수 있다.

<br>

#### If You Prefer to Write Code in Your Editor

###### 에디터에서 코드 작성을 원한다면

- Alternatively, you can set up a project on your computer.
  - 다른 대안으로, 당신의 컴퓨터에서 프로젝트를 설정할 수 있다.

<br>

- Note: **this is completely optional and not required for this tutorial!**
  - 참고: **선택 사항이지 필수 사항이 아니다.**

<br>

- This is more work, but lets you work from the comfort of your editor.
  - 이 방법은 손이 더 많이 가겠지만, 에디터의 편리함을 누리며 작업할 수 있다.

<br>

- If you want to do it, here are the steps to follow:
  - 이렇게 하기를 원한다면, 따라야 할 단계는 다음과 같다.

<br>

1. Make sure you have a recent version of [Node.js](https://nodejs.org/en/) installed.
   - 최신 버전의 [Node.js](https://nodejs.org/en/)가 설치되어 있는지 확인해라.
2. Follow the [installation instructions](https://reactjs.org/docs/add-react-to-a-new-app.html) to create a new project.
   - [설치 방법](https://reactjs.org/docs/add-react-to-a-new-app.html)에 따라 새로운 프로젝트를 만들어라.
   - `$ npm install -g create-react-app`
   - `$ create-react-app my-app`
3. Delete all files in the `src/` folder of the new project (don't delete the folder, just its contents).
   - 새 프로젝트의 `src/` 폴더에 있는 모든 파일을 삭제해라 (폴더는 삭제하지 말고, 내용물만 삭제해라).
   - `$ cd my-app`
   - `$ rm -f src/*`
4. Add a file named `index.css` in the `src/` folder with [this CSS code](https://codepen.io/gaearon/pen/oWWQNa?editors=0100).
   - `src/` 폴더에 `index.css` 파일을 만들고 [이 CSS 코드](https://codepen.io/gaearon/pen/oWWQNa?editors=0100)를 작성해라.
5. Add a file named `index.js` in the `src/` folder with [this JS code](https://codepen.io/gaearon/pen/oWWQNa?editors=0010).
   - `src/` 폴더에 `index.js` 파일을 만들고 [이 JS 코드](https://codepen.io/gaearon/pen/oWWQNa?editors=0010)를 작성해라.
6. Add these three lines to the top of `index.js` in the `src/` folder:
   - `src/` 폴더의 `index.js` 파일 맨 위에 아래 코드를 작성해라.

```react
import React from 'react';
import ReactDOM from 'react-dom';
import './index.css';
```

<br>

- Now if you run `npm start` in the project folder and open `http://localhost:3000` in the browser,
  - 이제 프로젝트 폴더에서 `npm start`를 실행하고, 브라우저에서 `http://localhost:3000`을 열면,
- you should see an empty tic-tac-toe field.
  - 비어 있는 틱택토 필드가 보일 것이다.

<br>

- We recommend following [these instructions](http://babeljs.io/docs/editors) to configure syntax highlighting for your editor.
  - [이 방법들](http://babeljs.io/docs/editors)을 따라 에디터에서 하이라이팅 문법을 설정하는 것을 추천한다.

<br>

#### Help, I'm Stuck! (문제 발생 시)

- If you get stuck, check out the [community support resources](https://reactjs.org/community/support.html).
  - 문제가 발생하면, [커뮤니티 지원 자료](https://reactjs.org/community/support.html)를 확인해라.
- In particular, [Reactiflux chat](https://reactjs.org/community/support.html#reactiflux-chat) is a great way to get quick help.
  - 특히, [Reactiflux chat](https://reactjs.org/community/support.html#reactiflux-chat)가 빠르게 도움을 얻을 수 있는 좋은 방법이다.
- If you don't get a good answer anywhere, please file an issue, and we'll help you out.
  - 만약 좋은 답변을 얻지 못한다면, 문제를 제기해라, 도움을 주겠다.

<br>

- With this out of the way, let's get started!
  - 이제 시작해보자.

------

<br>