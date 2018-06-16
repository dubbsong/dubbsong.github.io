---
layout: post
title: "공식 리액트 문서 번역 - 03. Rendering Elements (Main Concepts)"
categories: react
tags: react
---

[공식 리액트 문서 링크](https://reactjs.org/docs/rendering-elements.html)

<br>

## Rendering Elements

###### 렌더링 elements

<br>

- ###### Elements are the smallest building blocks of React apps.

  - ###### element는 React 앱의 가장 작은 빌딩 블록이다.

<br>

- An element describes what you want to see on the screen:
  - element는 화면에 표시할 내용을 설명한다.

```react
const element = <h1>Hello, world</h1>;
```

<br>

- Unlike browser DOM elements, React elements are plain objects, and are cheap to create.
  - 브라우저 DOM element와 달리 React element는 일반 객체이므로, 값싸게 만들 수 있다.
- React DOM takes care of updating the DOM to match the React elements.
  - React DOM은 React element와 일치하도록 DOM을 업데이트한다.

<br>

> **Note:**
>
> One might confuse elements with a more widely known concept of "components".
>
> element를 "컴포넌트"라는 더 널리 알려진 개념과 혼동할 수 있다.

> We will introduce components in the [Next section](https://reactjs.org/docs/components-and-props.html).
>
> 다음 섹션에서 컴포넌트를 소개할 것이다.

> Elements are what components are "made of", and we encourage you to read this section before jumping ahead.
>
> element가 어떤 컴포넌트로 이루어져 있는지, 앞으로 가기 전에 이 섹션을 읽는 것이 좋다.

------

<br>

### Rendering an Element into the DOM

- Let's say there is a `<div>` somewhere in your HTML file:
  - HTML 파일 어딘가에 `<div>`가 있다고 가정해보자.

```react
<div id="root"></div>
```

<br>

- We call this a "root" DOM node because everything inside it will be managed by React DOM.
  - 이것을 "root" DOM 노드라고 부른다.
  - 내부의 모든 것이 React DOM에 의해서 관리되기 때문이다.

<br>

- Applications built with just React usually have a single root DOM node.
  - React로 구축된 애플리케이션은 대개 단일 root DOM 노드를 가지고 있다.
- If you are integrating React into an existing app, you may have as many isolated root DOM nodes as you like.
  - React를 기존 앱에 통합하는 경우, 원하는 만큼 많은 수의 분리된 root DOM 노드가 있을 수 있다.

<br>

- To render a React element into a root DOM node, pass both to `ReactDOM.render()`:
  - React element를 root DOM 노드에 렌더링하려면, `ReactDOM.render()`에 모두 전달한다.

```react
const element = <h1>Hello, world</h1>;
ReactDOM.render(element, document.getElementById('root'));
```

[CodePen에서 시도](https://codepen.io/pen?&editors=0010)

<br>

- It displays "Hello, world" on the page.
  - 페이지에 "Hello, world"를 표시한다.

------

<br>

### Updating the Rendered Element

###### 렌더링 된 element 업데이트

<br>

- React elements are [immutable](https://en.wikipedia.org/wiki/Immutable_object).
  - React element는 [immutable](https://en.wikipedia.org/wiki/Immutable_object)(불변)이다.
- Once you create an element, you can't change its children or attributes.
  - element를 만든 후에는, 자식과 특성을 변경할 수 없다.
- An element is like a single frame in a movie: it represents the UI at a certain point in time.
  - element는 영화의 단일 프레임과 같다.
  - 특정 시점의 UI를 나타낸다.

<br>

- With our knowledge so far, the only way to update the UI is to create a new element, and pass it to `ReactDOM.render()`.
  - 지금까지 아는 한, UI를 업데이트하는 유일한 방법은 새로운 element를 만들어서 `ReactDOM.render()`에 전달하는 것이다.

<br>

- Consider this ticking clock example:
  - 똑딱 시계의 예를 보자.

```react
function tick() {
   const element = (
   	<div>
      	<h1>Hello, world!</h1>
         <h2>It is {new Date().toLocaleTimeString()}.</h2>
      </div>
   );
   ReactDOM.render(element, document.getElementById('root'));
}

setInterval(tick, 1000);
```

[CodePen에서 시도](https://codepen.io/pen?&editors=0010)

<br>

- It calls `ReactDOM.render()` every second from a [setInterval()](https://developer.mozilla.org/en-US/docs/Web/API/WindowOrWorkerGlobalScope/setInterval) callback.
  - 매초마다 [setInterval()](https://developer.mozilla.org/en-US/docs/Web/API/WindowOrWorkerGlobalScope/setInterval) 콜백에서 `ReactDOM.render()`를 호출한다.

<br>

> **Note:**
>
> In practice, most React apps only call `ReactDOM.render()` once.
>
> 실제로, 대부분의 React 앱은 `ReactDOM.render()`를 한 번만 호출한다.

> In the next sections we will learn how such code gets encapsulated into [stateful components](https://reactjs.org/docs/state-and-lifecycle.html).
>
> 다음 섹션에서 그러한 코드가 어떻게 [stateful component](https://reactjs.org/docs/state-and-lifecycle.html)로 캡슐화되는지 배울 것이다.

> We recommend that you don't skip topics because they build on each other.
>
> 서로 연관성이 있기 때문에 건너뛰지 않는 것이 좋다.

------

<br>

### React Only Updates What's Necessary

###### 필요한 것만 업데이트하는 React

<br>

- React DOM compares the element and its children to the previous one, and only applies the DOM updates necessary to bring the DOM to the desired state.
  - React DOM은 element와 그 자식 element를 이전 element와 비교해서, 원하는 state로 가져오기 위해 필요한 DOM 업데이트만 적용한다.

<br>

- You can verify by inspecting the [last example](https://reactjs.org/redirect-to-codepen/rendering-elements/update-rendered-element) with the browser tools:
  - 브라우저 도구를 사용해서 [마지막 예제](https://reactjs.org/redirect-to-codepen/rendering-elements/update-rendered-element)를 검사해서 확인할 수 있다.

![react img](/assets/img/official-react-main concepts-03-01.gif)

<br>

- Even though we create an element describing the whole UI tree on every tick, only the text node whose contents has changed gets updated by React DOM.
  - 매초마다 UI 트리 전체를 설명하는 element를 만들었지만, 내용이 변경된 텍스트 노드만 React DOM에 의해 업데이트 된다.

<br>

- In our experience, thinking about how the UI should look at any given moment rather than how to change it over time eliminates a whole class of bugs.
  - 경험상, 시간이 지남에 따라 UI를 변경하는 것보다, 주어진 순간에 UI가 어떻게 보여야 하는지 생각해보면 버그 전체가 제거된다.

------

<br>
