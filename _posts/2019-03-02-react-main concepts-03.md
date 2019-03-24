---
layout: post
title: "(공식 리액트 Docs) 03. Rendering Elements"
categories: dev
tags: react
---

###### [공식 리액트 Docs](https://reactjs.org/docs/rendering-elements.html) 번역

<br>

## Rendering Elements

###### element 렌더링 하기

<br>

- Elements are the smallest building blocks of React apps.
  - element는 React app의 가장 작은 빌딩 블록이다.

- An element describes what you want to see on the screen:
  - element는 화면에 보여줄 것을 설명한다.

```react
const element = <h1>Hello World!</h1>;
```

<br>

- Unlike browser DOM elements, React elements are plain objects, and are cheap to create.
  - React element는 브라우저 DOM element와 달리 일반 객체이므로, 쉽게 생성할 수 있다.
- React DOM takes care of updating the DOM to match the React elements.
  - React DOM은 React element와 일치하도록 DOM을 업데이트한다.

<br>

> **Note:**
>
> One might confuse elements with a more widely known concept of "components".
>
> element를 "컴포넌트"라는 개념과 혼동할 수 있다.

------

<br>

#### Rendering an Element into the DOM

###### element를 DOM에 렌더링 하기

<br>

- Let's say there is a `<div>` somewhere in your HTML file:
  - HTML 파일 어딘가에 `<div>`가 있다고 가정해보자.

```html
<div id="root"></div>
```

<br>

- We call this a "root" DOM node because everything inside it will be managed by React DOM.
  - 이를 "root" DOM node라고 부른다.
  - 내부의 모든 것이 React DOM에 의해 관리된다.

<br>

- Applications built with just React usually have a single root DOM node.
  - React로 구축된 애플리케이션은 대개 하나의 root DOM node를 가진다.
- If you are integrating React into an existing app, you may have as many isolated root DOM nodes as you like.
  - React를 기존 앱에 통합하는 경우, 원하는 만큼 많은 수의 분리된 root DOM node가 있을 수 있다.

<br>

- To render a React element into a root DOM node, pass both to `ReactDOM.render()`:
  - React element를 root DOM node에 렌더링 하기 위해, `ReactDOM.render()`에 모두 전달한다.

```react
const element = <h1>Hello World!</h1>;

ReactDOM.render(element, document.getElementById('root'));
```

[코드 실행 확인](https://reactjs.org/redirect-to-codepen/rendering-elements/render-an-element)

<br>

- It displays "Hello World!" on the page.
  - 위 코드는 웹 페이지에 "Hello World!"를 표시한다.

------

<br>

#### Updating the Rendered Element

###### 렌더링 된 element 업데이트하기

<br>

- React elements are [immutable](https://en.wikipedia.org/wiki/Immutable_object).
  - React element는 [불변](https://en.wikipedia.org/wiki/Immutable_object)(변경할 수 없는)이다.
- Once you create an element, you can't change its children or attributes.
  - element를 생성한 후에는 children 또는 속성을 변경할 수 없다.
- An element is like a single frame in a movie: it represents the UI at a certain point in time.
  - element는 영화의 frame과 같다.
  - 특정 시점의 UI를 나타낸다.

<br>

- With our knowledge so far, the only way to update the UI is to create a new element, and pass it to `ReactDOM.render()`.
  - 지금까지 우리가 아는 한 UI를 업데이트하는 유일한 방법은, 새 element를 생성해서 `ReactDOM.render()`에 전달하는 것이다.

<br>

- Consider this ticking clock example:
  - ticking clock 예제를 살펴보자.

```react
function tick() {
  const element = (
    <div>
      <h1>Hello World!</h1>
      <h2>{new Date().toLocaleTimeString()}</h2>
    </div>
  );
  
  ReactDOM.render(element, document.getElementById('root'));
}

setInterval(tick, 1000);
```

[코드 실행 확인](https://reactjs.org/redirect-to-codepen/rendering-elements/update-rendered-element)

<br>

- It calls `ReactDOM.render()` every second from a [setInterval()](https://developer.mozilla.org/en-US/docs/Web/API/WindowOrWorkerGlobalScope/setInterval) callback.
  - 위 코드는 매초 [setInterval()](https://developer.mozilla.org/en-US/docs/Web/API/WindowOrWorkerGlobalScope/setInterval) 콜백에서 `ReactDOM.render()`를 호출한다.

<br>

> **Note:**
>
> In practice, most React apps only call `ReactDOM.render()` once.
>
> 사실 대부분의 React 앱은 `ReactDOM.render()`를 한 번만 호출한다.

------

<br>

#### React Only Updates What's Necessary

###### React는 필요한 것만 업데이트한다

<br>

- React DOM compares the element and its children to the previous one, and only applies the DOM updates necessary to bring the DOM to the desired state.
  - React DOM은 element와 그 children element를 이전 element와 비교한다.
  - 그리고 DOM을 원하는 상태로 만드는 데 필요한 DOM 업데이트만 적용한다. 

<br>

- You can verify by inspecting the [last example](https://codepen.io/pen?&editable=true&editors=0010) with the browser tools:
  - 브라우저 도구를 사용해서 [ticking clock 예제](https://codepen.io/pen?&editable=true&editors=0010)를 확인할 수 있다.

![img](/assets/img/react-main concepts-03-01.gif)

<br>

- Even though we create an element describing the whole UI tree on every tick, only the text node whose contents has changed gets updated by React DOM.
  - 매초 UI tree 전체를 그려내는 element를 생성했지만, 내용이 변경된 텍스트 node만 React DOM에 의해 업데이트된다.
- In our experience, thinking about how the UI should look at any given moment rather than how to change it over time eliminates a whole class of bugs.
  - 경험상 시간이 지남에 따라 UI를 변경하는 것이 아니라, 주어진 순간에 UI가 어떻게 보여야 하는지를 생각하면 모든 버그가 제거된다.

------

<br>