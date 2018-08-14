---
layout: post
title: "리액트 공식 문서 번역 - 01. Hello World (Main Concepts)"
categories: react
tags: React
---

###### [React 공식 문서](https://reactjs.org/docs/hello-world.html) 번역

<br>

# React: Hello World

<br>

- The smallest React example looks like this:
  - 가장 작은 React 예제는 다음과 같다.

```react
ReactDOM.render(
	<h1>Hello, world!</h1>,
   document.getElementById('root')
);
```

[코드 실행 확인 링크](https://codepen.io/pen?&editors=0010)

<br>

- It displays a heading saying "Hello, world!" on the page.
  - 페이지에 "Hello, world!"라는 제목을 표시한다.

------

<br>

## How to Read This Guide

###### 이 가이드를 읽는 법

<br>

- In this guide, we will examine the building blocks of React apps: elements and components.
  - 이 가이드에서는, React 앱의 element와 컴포넌트 빌딩 블록을 살펴볼 것이다.
- Once you master them, you can create complex apps from small reusable pieces.
  - 일단 마스터하면, 재사용 가능한 작은 조각으로 복잡한 앱을 만들 수 있다.

<br>

- `You can learn most of React by reading the "Main Concepts" guide chapters in the order they appear in the sidebar.
  - "Main Concepts" 가이트 챕터를 읽어서 React의 대부분을 배울 수 있다.

------

<br>

## Knowledge Level Assumptions

###### 지식 수준 가정

<br>

- React is a JavaScript library, and so we'll assume you have a basic understanding of the JavaScript language.
  - React는 JavaScript 라이브러리이므로, JavaScript 언어에 대한 기본 이해가 있다고 가정한다.
- If you don't feel very confident, we recommend [going through a JavaScript tutorial](https://developer.mozilla.org/en-US/docs/Web/JavaScript/A_re-introduction_to_JavaScript) to check your knowledge level and enable you to follow along this guide without getting lost.
  - 확신이 부족하다면, [JavaScript 튜토리얼을 통해](https://developer.mozilla.org/en-US/docs/Web/JavaScript/A_re-introduction_to_JavaScript) 지식 수준을 체크한 후 이 가이드를 따르는 것이 좋다.

------

<br>