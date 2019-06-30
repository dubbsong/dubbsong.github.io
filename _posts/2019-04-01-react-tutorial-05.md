---
layout: post
title: "(공식 리액트 튜토리얼 05) 개발자 도구"
categories: dev
tags: react
---

###### [공식 리액트 튜토리얼](https://reactjs.org/tutorial/tutorial.html#developer-tools) 번역

<br>

#### Developer Tools

###### 개발자 도구

<br>

- The React DevTools extension for Chrome and Firefox lets you inspect a React component tree with your browser's developer tools.
  - React DevTools 확장 프로그램을 사용하면, 브라우저의 개발자 도구로 React 컴포넌트 트리를 살펴볼 수 있다.

```html
<Game>
  <div className="game">
    <div className="game-board">
      <Board>
        <div>
          <div className="status">Next player: X</div>
          <div className="board-row">
            <Square value={0}>...</Square>
            <Square value={1}>...</Square>
            <Square value={2}>...</Square>
          </div>
          <div className="board-row">
            <Square value={3}>...</Square>
            <Square value={4}>...</Square>
            <Square value={5}>...</Square>
          </div>
          <div className="board-row">
            <Square value={6}>...</Square>
            <Square value={7}>...</Square>
            <Square value={8}>
              <button className="square">X</button>
            </Square>
          </div>
        </div>
      </Board>
    </div>
    <div className="game-info">
      <div></div>
      <ol></ol>
    </div>
  </div>
</Game>
```

<br>

- The React DevTools let you check the props and the state of your React components.
  - React DevTools를 사용하면, React 컴포넌트의 props와 state를 확인할 수 있다.

<br>

- After installing React DevTools, you can right-click on any element on the page, click "Inspect" to open the developer tools, and the React tab will appear as the last tab to the right.
  1. React DevTools를 설치한다.
  2. 페이지의 아무 element를 우클릭한다.
  3. `검사`를 클릭해서 개발자 도구를 연다.
  4. 오른쪽 마지막 탭에 React 탭이 나타난다.

------

<br><br>