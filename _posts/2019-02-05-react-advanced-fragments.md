---
layout: post
title: "(공식 리액트 Docs) Fragment 태그"
categories: dev
tags: react
---

###### [공식 리액트 Docs](https://reactjs.org/docs/fragments.html) 번역

<br>

### Fragments

###### \<React.Fragment> 태그

<br>

- A common pattern in React is for a component to return multiple elements.
  - React에서 컴포넌트의 일반적인 패턴은, 여러 element를 반환하는 것이다.
- Fragments let you group a list of children without adding extra nodes to the DOM.
  - Fragment를 사용하면, DOM에 별도의 node를 추가하지 않고도 children 목록을 그룹화할 수 있다.

```react
render() {
  return (
    <React.Fragment>
      <ChildA />
      <ChildB />
      <ChildC />
    </React.Fragment>
  );
}
```

<br>

- There is also a new [short syntax](https://reactjs.org/docs/fragments.html#short-syntax) for declaring them, but it isn't supported by all popular tools yet.
  - 선언을 위한 [짧은 구문](https://reactjs.org/docs/fragments.html#short-syntax)도 있지만, 아직 모든 툴에서 지원되지는 않는다.

------

<br>

### Motivation

###### 동기

<br>

- A common pattern is for a component to return a list of children.
  - 컴포넌트의 일반적인 패턴은, children 리스트를 반환하는 것이다.
- Take this example React snippet:
  - 다음 React 코드 예제를 살펴보자.

```react
class Table extends React.Component {
  render() {
    return (
      <table>
        <tr>
          <Columns />
        </tr>
      </table>
    );
  }
}
```

<br>

- `<Columns />` would need to return multiple `<td>` elements in order for the rendered HTML to be valid.
  - 렌더링 된 HTML이 유효하기 위해서는, `<Columns />`가 여러 `<td>` element를 반환해야 한다.
- If a parent div was used inside the `render()` of `<Columns />`, then the resulting HTML will be invalid.
  - parent div가 `<Columns />`의 `render()` 내에서 사용된 경우, 결과 HTML은 유효하지 않다.

```react
class Columns extends React.Component {
  render() {
    return (
      <div>
        <td>Hello</td>
        <td>World</td>
      </div>
    );
  }
}
```

<br>

- results in a `<Table />` output of:
  - `<Table />`의 출력 결과는 다음과 같다.

```react
<table>
  <tr>
    <div>
      <td>Hello</td>
      <td>World</td>
    </div>
  </tr>
</table>
```

<br>

- Fragments solve this problem.
  - Fragment는 이러한 문제를 해결한다.

------

<br>

### Usage

###### 사용 방법

<br>

```react
class Columns extends React.Component {
  render() {
    return (
      <React.Fragment>
        <td>Hello</td>
        <td>World</td>
      </React.Fragment>
    );
  }
}
```

<br>

- which results in a correct `<Table />` output of:
  - 올바른 `<Table />` 출력 결과는 다음과 같다.

```react
<table>
  <tr>
    <td>Hello</td>
    <td>World</td>
  </tr>
</table>
```

------

<br>

### Short Syntax

###### 짧은 구문

<br>

- There is a new, shorter syntax you can use for declaring fragments.
  - fragment를 선언하는 데 사용할 수 있는 새로운 짧은 구문이 있다.
- It looks like empty tags:
  - 이는 빈 태그처럼 보인다.

```react
class Columns extends React.Component {
  render() {
    return (
      <>
        <td>Hello</td>
        <td>World</td>
      </>
    );
  }
}
```

<br>

- You can use `<><\>` the same way you'd use any other element except that it doesn't support keys or attributes.
  - key 또는 속성을 지원하지 않는 점을 제외하고는, 다른 element를 사용하는 방법과 동일하게 `<></>`를 사용할 수 있다.

<br>

- Note that [many tools don't support it yet](https://reactjs.org/blog/2017/11/28/react-v16.2.0-fragment-support.html#support-for-fragment-syntax) so you might want to explicitly write `<React.Fragment>` until the tooling catches up.
  - [아직 많은 툴에서 빈 태그를 지원하지 않으므로](https://reactjs.org/blog/2017/11/28/react-v16.2.0-fragment-support.html#support-for-fragment-syntax), 해당 툴이 업데이트 될 때까지 `<React.Fragment>`를 명시적으로 작성해야 할 수 있다.

------

<br>

### Keyed Fragments

###### key가 지정된 Fragment

<br>

- Fragments declared with the explicit `<React.Fragment>` syntax may have keys.
  - 명시적 `<React.Fragment>` 구문으로 선언된 Fragment는 key를 가질 수 있다.
- A use case for this is mapping a collection to an array of fragments - for example, to create a description list:
  - 예를 들어 이를 위한 사용 사례는, collection을 fragment 배열에 매핑해서 description 리스트를 생성하는 것이다.

```react
function Glossary(props) {
  return (
    <dl>
      {props.items.map(item => (
        // Without the 'key', React will fire a key warning
        <React.Fragment key={item.id}>
          <dt>{item.term}</dt>
          <dd>{item.description}</dd>
        </React.Fragment>
      ))}
    </dl>
  );
}
```

<br>

- `key` is the only attribute that can be passed to `Fragment`.
  - `key`는 `Fragment`에 전달할 수 있는 유일한 속성이다.
- In the future, we may add support for additional attributes, such as event handlers.
  - 앞으로는, 이벤트 핸들러와 같은 추가 속성에 대한 지원이 추가될 수 있다.

------

<br>

<br>