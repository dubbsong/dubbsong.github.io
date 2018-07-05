---
layout: post
title: "공식 리액트 문서 번역 - 01. Accessibility (advenced guides)"
categories: react
tags: react
---

[공식 리액트 문서 링크](https://reactjs.org/docs/accessibility.html)

<br>

## Accessibility (접근성)

<br>

### Why Accessibility?

###### 왜 접근성인가?

<br>

- Web accessibility (also referred to as [a11y](https://en.wiktionary.org/wiki/a11y)) is the design and creation of websites that can be used by everyone.
  - 웹 접근성([a11y](https://en.wiktionary.org/wiki/a11y)라고도 한다)은 모든 사람이 사용할 수 있는 웹 사이트 디자인 및 제작이다.
- Accessibility support is necessary to allow assistive technology to interpret web pages.
  - 보조 기술이 웹 페이지를 해석할 수 있도록 접근성 지원이 필요하다.

<br>

- React fully supports building accessible websites, often by using standard HTML techniques.
  - React는 표준 HTML 기술을 사용해서 접근 가능한 웹 사이트를 완벽하게 지원한다.

------

### Standards and Guidelines

###### 표준 및 가이드라인

<br>

#### WCAG

- The [Web Content Accessibility Guidelines](https://www.w3.org/WAI/standards-guidelines/wcag/) provides guidelines for creating accessible web sites.
  - [웹 컨텐츠 접근성 가이드라인](https://www.w3.org/WAI/standards-guidelines/wcag/)은 접근 가능한 웹 사이트를 만드는 가이드라인을 제공한다.

<br>

- The following WCAG checklists provide an overview:
  - 다음 WCAG 체크리스트에서 개요를 제공한다.

1. [WCAG checklist from Wuhcag](https://www.wuhcag.com/wcag-checklist/)
2. [WCAG checklist from WebAIM](https://webaim.org/standards/wcag/checklist)
3. [Checklist from The A11Y Project](https://a11yproject.com/checklist.html)

<br>

#### WAI-ARIA

- The [Web Accessibility Initiative - Accessible Rich Internet Applications](https://www.w3.org/WAI/standards-guidelines/aria/) document contains techniques for building fully accessible JavaScript widgets.
  - [Web Accessibility Initiative - Accessible Rich Internet Applications](https://www.w3.org/WAI/standards-guidelines/aria/) 문서에는 완벽하게 접근할 수 있는 JavaScript 위젯을 작성하는 기술이 포함되어 있다.

<br>

- Note that all `aria-*` HTML attributes are fully supported in JSX.
  - 모든 `aria-*` HTML 속성은 JSX에서 완벽하게 지원된다.
- Whereas most DOM properties and attributes in React are camelCased, these attributes should be lowercased:
  - React에서 대부분의 DOM property와 속성은 camelCase(낙타 대문자)이지만, 이러한 속성은 소문자로 처리해야 한다.

```react
<input
   type="text"
   aria-label={labelText}
   aria-required="true"
   onChange={onchangeHandler}
   value={inputValue}
   name="name"
/>
```

------

### Semantic HTML

###### 시멘틱 HTML

<br>

- Semantic HTML is the foundation of accessibility in a web application.
  - 시멘틱 HTML은 웹 애플리케이션에서 접근성의 토대이다.
- Using the various HTML elements to reinforce the meaning of information in our websites will often give us accessibility for free.
  - 다양한 HTML element를 사용해서 웹 사이트에서 정보의 의미를 강화하면, 종종 자유롭게 접근할 수 있게 된다.

> [MDN HTML elements reference](https://developer.mozilla.org/en-US/docs/Web/HTML/Element)

<br>

- Sometimes we break HTML semantics when we add `<div>` elements to our JSX to make our React code work, especially when working with lists (`<ol>`, `<ul>` and `<dl>`) and the HTML `<table>`.
  - `<div>` element를 JSX에 추가할 때, 특히 목록(`<ol>`, `<ul>` and `<dl>`)과 HTML `<table>`을 사용해서 작업할 때, React 코드가 작동하도록 HTML 시멘틱을 중단하는 경우가 있다.
- In these cases we should rather use React Fragments to group together multiple elements.
  - 이러한 경우 오히려 React Fragment를 사용해서 여러 element를 그룹화해야 한다.

<br>

- Use `<Fragment>` when a `key` prop is required:
  - `key` prop이 필요한 경우, `<Fragment>`를 사용해라.

```react
import React, { Fragment } from 'react';

function Glossary(props) {
   return (
   	<dl>
      	{props.items.map(item => (
         	// Without the 'key', React will fire a key warning
            <Fragment key={item.id}>
            	<dt>{item.term}</dt>
               <dt>{item.description}</dt>
            </Fragment>
         ))}
      </dl>
   );
}
```

<br>

- Use `<></>` syntax everywhere else:
  - 어디에서는 `<></>` 구문을 사용해라.

```react
function ListItem({ item }) {
   return (
   	<dt>{item.term}</dt>
      <dd>{item.description}</dd>
   );
}
```

------

### Accessible Forms

###### 접근 가능한 form

<br>

#### Labeling

- Every HTML form control, such as `<input>` and `<textarea>`, needs to be labeled accessibly.
  - `<input>`과 `<textarea>`와 같은 모든 HTML form 컨트롤에는 접근 가능하게 라벨링해야 한다.
- We need to provide descriptive labels that are also exposed to screen readers.
  - 스크린 리더에도 노출되는 설명적인 라벨을 제공해야 한다.

<br>

- The following resources show us how to do this:
  - 다음 리소스는 작업을 수행하는 방법을 보여준다.

1. [The W3C shows us how to label elements](https://www.w3.org/WAI/tutorials/forms/labels/)
2. [WebAIM shows us how to label elements](https://webaim.org/techniques/forms/controls)
3. [The Paciello Group explains accessible names](https://developer.paciellogroup.com/blog/2017/04/what-is-an-accessible-name/)

<br>

- Although these standard HTML practices can be directly used in React, onte that the `for` attribute is written as `htmlFor` in JSX:
  - 이러한 표준 HTML 실습은 React에서 직접 사용될 수 있지만, `for` 속성은 JSX에서 `htmlFor`로 작성된다.

```react
<label htmlFor="namedInput">Name:</label>
<input id="namedInput" type="text" name="name"/>
```

<br>

#### Notifying the user of errors

###### 사용자에게 에러 알림

<br>

- Error situations need to be understood by all users.
  - 에러 상황은 모든 사용자가 이해해야 한다.
- The following link shows us how to expose error texts to screen readers as well:
  - 다음 링크는 에러 텍스트를 스크린 리더에도 표시하는 방법을 보여준다.

1. [The W3C demonstrates user notifications](https://www.w3.org/WAI/tutorials/forms/notifications/)
2. [WebAIM looks at form validation](https://webaim.org/techniques/formvalidation/)

------

### Focus Control

- Ensure that your web application can be fully operated with the keyboard only:
  - 웹 애플리케이션이 키보드로만 완전히 작동할 수 있는지 확인해라.

> [WebAIM talks about keyboard accessibility](https://webaim.org/techniques/keyboard/)

<br>

#### Keyboard focus and focus outline

- Keyboard focus refers to the current element in the DOM that is selected to accept input from the keyboard.
  - 키보드 focus는 키보드의 입력을 허용하도록 선택된 DOM의 현재 element를 나타낸다.
- We see it everywhere as a focus outline similar to that shown in the following image:
  - 다음 이미지에서 볼 수 있는 것과 비슷한 focus outline으로 어디에서나 볼 수 있다.

![react img](/assets/img/react-advanced guides-01-01.png)

<br>

- Only ever use CSS that removes this outline, for example by setting `outline: 0`, if you are replacing it with another focus outline implementation.
  - 이 outline을 제거하는 CSS만 사용해라.
  - 예를 들어, `outline: 0`을 설정해서, 다른 focus outline 구현으로 바꾸는 경우이다.

<br>

#### Mechanisms to skip to desired content

###### 원하는 내용으로 건너뛰는 메커니즘

<br>

- Provide a mechanism to allow users to skip past navigation sections in your application as this assists and speeds up keyboard navigation.
  - 사용자가 애플리케이션의 이전 탐색 섹션을 건너뛸 수 있는 메커니즘을 제공한다.
  - 이것은 키보드 탐색을 돕고 빠르게 한다.

<br>

- Skiplinks or Skip Navigation Links are hidden navigation links that only become visible when keyboard users interact with the page.
  - Skiplink 또는 Skip Navigation Link는 사용자가 페이지와 상호작용할 때만 표시되는 숨겨진 탐색 링크이다.
- They are very easy to implement with internal page anchors and some styling:
  - 내부 페이지 앵커와 일부 스타일링을 사용해서 구현하는 것은 매우 쉽다.

> [WebAIM - Skip Navigation Links](https://webaim.org/techniques/skipnav/)

<br>

- Also use landmark elements and roles, such as `<main>` and `<aside>`, to demarcate page regions as assistive technology allow the user to quickly navigate to these sections.
  - 또한 `<main>`과 `<aside>` 같은 landmark element 및 role을 사용해서, 사용자가 이러한 섹션으로 빠르게 탐색할 수 있는 보조 기술로 페이지 영역을 구분할 수 있다.

<br>

- Read more about the use of these elements to enhance accessibility here:
  - 여기에 접근성을 높이기 위해 이러한 element를 사용하는 방법에 대해 읽어봐라.

> [Accessible Landmarks](https://www.scottohara.me/blog/2018/03/03/landmarks.html)

<br>

#### Programmatically managing focus

###### 프로그래밍 방식으로 focus 관리

<br>

- Our React applications continuously modify the HTML DOM during runtime, sometimes leading to keyboard focus being lost or set to an unexpected element.
  - React 런타임 중에 HTML DOM을 애플리케이션은 지속적으로 수정하므로, 키보드 focus가 손실되거나 예기치 않은 element로 설정되는 경우가 있다.
- In order to repair this, we need to programmatically nudge the keyboard focus in the right direction.
  - 이것을 바로잡기 위해 프로그래밍 방식으로 키보드 focus를 올바른 방향으로 해야 한다.
- For example, by resetting keyboard focus to a button that opened a modal window after that modal window is closed.
  - 예를 들어, 모달 창을 닫은 후에, 모달 창을 열었던 버튼에 키보드 focus를 다시 설정한다.

<br>

- MDN Web Docs takes a look at this and describes how we can build [keyboard-navigable JavaScript widgets](https://developer.mozilla.org/en-US/docs/Web/Accessibility/Keyboard-navigable_JavaScript_widgets).
  - MDN Web Docs는 이것을 살펴보고, [키보드 탐색 가능한 JavaScript 위젯](https://developer.mozilla.org/en-US/docs/Web/Accessibility/Keyboard-navigable_JavaScript_widgets)을 제작하는 방법을 설명한다.

<br>

- To set focus in React, we can use [Refs to DOM elements](https://reactjs.org/docs/refs-and-the-dom.html).
  - React에서 focus를 설정하려면, [DOM element에 대한 Refs](https://reactjs.org/docs/refs-and-the-dom.html)를 사용할 수 있다.

<br>

- Using this, we first create a ref to an element in the JSX of a component class:
  - 이를 사용해서, 컴포넌트 클래스의 JSX에서 element에 대한 참조를 먼저 생성한다.

```react
class CustomTextInput extends React.Component {
   constructor(props) {
      super(props);
      // Create a ref to store the textInput DOM element
      this.textInput = React.createRef();
   }
   render() {
      // Use the 'ref' callback to store a reference to the text input DOM
      // element in an instance field (for example, this.textInput).
      return (
      	<input
            type="text"
            ref={this.textInput}
            />
      );
   }
}
```

<br>

- Then we can focus it elsewhere in our component when needed:
  - 그런 다음 필요할 때마다 컴포넌트의 다른 부분에 focus 할 수 있다.

```react
focus() {
   // Explicitly focus the text input using the raw DOM API
   // Note: we're accessing "current" to get the DOM node
   this.textInput.current.focus();
}
```

<br>

- Sometimes a parent component needs to set focus to an element in a child component.
  - 때때로 부모 컴포넌트는 자식 컴포넌트의 element에 focus를 설정해야 한다.
- We can do this by [exposing DOM refs to parent components](https://reactjs.org/docs/refs-and-the-dom.html#exposing-dom-refs-to-parent-components) through a special prop on the child component that forwards the parent's ref to the child's DOM node.
  - 부모의 참조를 자식의 DOM node로 전달하는 자식 컴포넌트의 특별한 prop을 통해 [DOM 참조를 부모 컴포넌트에 노출](https://reactjs.org/docs/refs-and-the-dom.html#exposing-dom-refs-to-parent-components)함으로써 이를 수행할 수 있다.

```react
function CustomTextInput(props) {
   return (
   	<div>
      	<input ref={props.inputRef} />
      </div>
   );
}

class Parent extends React.Component {
   constructor(props) {
      super(props);
      this.inputElement = React.createRef();
   }
   render() {
      return (
      	<CustomTextInput inputRef={this.inputElement} />
      );
   }
}


// Now you can set focus when required.
this.inputElement.current.focus();
```

<br>

- When using a HOC to extend components, it is recommended to [forward the ref](https://reactjs.org/docs/forwarding-refs.html) to the wrapped component using the `forwardRef` function of React.
  - HOC을 사용해서 컴포넌트를 확장하는 경우, React의 `forwardRef` 함수를 사용해서 래핑 된 컴포넌트로 [참조를 전달](https://reactjs.org/docs/forwarding-refs.html)하는 것이 좋다.
- If a third party HOC does not implement ref forwarding, the above pattern can still be used as a fallback.
  - 제3자 HOC가 ref 전달을 구현하지 않으면, 위의 패턴을 예비로 사용할 수 있다.

<br>

- A great focus management example is the [react-aria-modal](https://github.com/davidtheclark/react-aria-modal).
  - focus 관리 예제는 [react-aria-modal](https://github.com/davidtheclark/react-aria-modal)이다.
- This is a relatively rare example of a fully accessible modal window.
  - 이것은 거의 접근할 수 없는 모달 창의 비교적 드문 예이다.
- Not only does it set initial focus on the cancel button (preventing the keyboard user from accidentally activating the success action) and trap keyboard focus inside the modal, it also resets focus back to the element that initially triggered the modal.
  - 취소 버튼에 초기 focus를 설정하고 (키보드 사용자가 실수로 success action을 활성화하지 못하게 예방), 키보드 focus를 모달 내부에 잡아둔다.
  - 또한 초기에 모달을 트리거한 element로 focus를 다시 설정한다.

<br>

> **Note:**
>
> While this is a very important accessibility feature, it is also a technique that should be used judiciously.
>
> 매우 중요한 접근성 기능이지만, 현명하게 사용해야 하는 기술이기도 하다.

> Use it to repair the keyboard focus flow when it is disturbed, not to try and anticipate how users want to use applications.
>
> 사용자가 애플리케이션을 사용하려는 방식을 시도하거나 예상하지 말고, 키보드 focus 흐름이 방해를 받으면 이를 복구하는 데 사용해라.

------

### More Complex Widgets

###### 더 복잡한 위젯

<br>

- 





































