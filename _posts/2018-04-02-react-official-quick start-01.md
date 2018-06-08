---
layout: post
title: "공식 리액트 문서 번역 - 01. Hello World (Quick Start)"
categories: react
tags: react
---

[공식 리액트 문서 링크](https://reactjs.org/docs/hello-world.html)

<br>

## Hello World

- ###### The easiest way to get started with React is to use [this Hello World example code on CodePen](https://codepen.io/pen?&editors=0010).

  - React를 시작하는 가장 쉬운 방법은 [이 Hello World 예제 코드를 CodePen에서](https://codepen.io/pen?&editors=0010) 사용하는 것이다.
- ###### You don't need to install anything; you can just open it in another tab and follow along as we go through examples.

  - 아무것도 설치할 필요가 없다; 다른 탭에서 열고, 예제를 따라가면 된다.
- ###### If you'd rather use a local development environment, check out the [Installation](https://reactjs.org/docs/try-react.html) section.

  - 로컬 개발 환경을 사용하려면, [설치](https://reactjs.org/docs/try-react.html) 섹션을 확인해라.

<br>

- The smallest React example looks like this:
  - 가장 간단한 React 예제는 다음과 같다.

```react
ReactDOM.render(
	<h1>Hello, world!</h1>,
   document.getElementById('root')
);

// Hello, world!
```

- It renders a heading saying "Hello, world!" on the page.
  - 이 예제는 페이지에서 `"Hello, world!"`라고 표제를 렌더링한다.

<br>

- The next few sections will gradually introduce you to using React.
  - 다음 몇 섹션은 차차 React 사용법을 소개한다.
- We will examine the building blocks of React apps: elements and components.
  - React 애플리케이션의 빌딩 블록인 `element`와 `component`를 살펴볼 것이다.
- Once you master them, you can create complex apps from small reusable pieces.
  - 일단 마스터하면, 재사용이 가능한 작은 조각으로 복잡한 애플리케이션을 만들 수 있다.

------

<br>

### A Note on JavaScript

###### JS에 대한 참고 사항

<br>

- React is a JavaScript library, and so we'll assume you have a basic understanding of the JavaScript language.
  - React는 JavaScript 라이브러리이므로, 당신이 JavaScript 언어에 대한 기본 지식이 있다고 가정한다.
- If you don't feel very confident, we recommend [refreshing your JavaScript knowledge](https://developer.mozilla.org/en-US/docs/Web/JavaScript/A_re-introduction_to_JavaScript) so you can follow along more easily.
  - 자신이 없다면, 더 쉽게 따라올 수 있도록 [JavaScript 지식을 새롭게 하는 것](https://developer.mozilla.org/en-US/docs/Web/JavaScript/A_re-introduction_to_JavaScript)을 권장한다.

<br>

- We also use some of the ES6 syntax in the examples.
  - 예제에서 ES6 문법 중 일부도 사용한다.
- We try to use it sparingly because it's still relatively new, but we encourage you to get familiar with [arrow functions](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/Arrow_functions), [classes](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Classes), [template literals](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Template_literals), [let](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/let), and [const](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/const) statements.
  - 비교적 새로운 기술이기 때문에 삼가해서 사용하려고 한다.
  - 하지만 [화살표 함수](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/Arrow_functions), [클래스](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Classes), [템플릿 리터럴](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Template_literals), [let](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/let), [const](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/const) 문에 익숙해지는 것이 좋다.
- You can use the [Babel REPL](https://babeljs.io/repl/#?presets=react&code_lz=MYewdgzgLgBApgGzgWzmWBeGAeAFgRgD4AJRBEAGhgHcQAnBAEwEJsB6AwgbgChRJY_KAEMAlmDh0YWRiGABXVOgB0AczhQAokiVQAQgE8AkowAUAcjogQUcwEpeAJTjDgUACIB5ALLK6aRklTRBQ0KCohMQk6Bx4gA) to check what ES6 code compiles to.
  - [Babel REPL](https://babeljs.io/repl/#?presets=react&code_lz=MYewdgzgLgBApgGzgWzmWBeGAeAFgRgD4AJRBEAGhgHcQAnBAEwEJsB6AwgbgChRJY_KAEMAlmDh0YWRiGABXVOgB0AczhQAokiVQAQgE8AkowAUAcjogQUcwEpeAJTjDgUACIB5ALLK6aRklTRBQ0KCohMQk6Bx4gA)을 사용해서 ES6 코드가 컴파일 되는 것을 확인할 수 있다.

------

<br>