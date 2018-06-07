---
layout: post
title: "공식 리액트 블로그 번역 - 01. Why did we build React?"
categories: react
tags: react
---

[공식 리액트 블로그 링크](https://reactjs.org/blog/2013/06/05/why-react.html)

<br>

## Why did we build React?

###### 우리가 React를 만든 이유

<br>

###### There are a lot of JavaScript MVC frameworks out there.

###### 이미 많은 JavaScript MVC 프레임워크가 있다.

###### Why did we build React and why would you want to use it?

###### 우리는 왜 React를 만들었고, 당신은 왜 React를 사용하고 싶은가?

------

<br>

### React isn't an MVC framework.

###### React는 MVC 프레임워크가 아니다.

<br>

- React is a library for building composable user interfaces.
  - React는 유저 인터페이스를 구축하기 위한 라이브러리다.
- It encourages the creation of reusable UI components which present data that changes over time.
  - 시간이 지남에 따라 변하는 데이터를 나타내는, 재사용 가능한 UI 컴포넌트 생성을 권장한다.

------

<br>

### React doesn't use templates.

###### React는 템플릿을 사용하지 않는다.

<br>

- Traditionally, web application UIs are built using templates or HTML directives.
  - 전통적으로, 웹 애플리케이션 UI는 템플릿이나 HTML 지시문을 사용해서 작성된다.
- These templates dictate the full set of abstractions that you are allowed to use to build your UI.
  - 이러한 템플릿은 UI를 구축하는 데 사용할 수 있는 추상 모델 전체에 영향을 준다.

<br>

- React approaches building user interfaces differently by breaking them into **components**.
  - React는 유저 인터페이스를 **컴포넌트**로 분리해서 다르게 구축하는 방식으로 접근한다.
- This means React uses a real, full featured programming language to render views, which we see as an advantage over templates for a few reasons:
  - 즉, React가 view를 그리기 위한 모든 기능을 갖춘 프로그래밍 언어를 사용한다는 것을 의미한다.
  - 몇 가지 이유로 템플릿에 비해 몇 가지 이점이 있다.

<br>

1. **JavaScript is a flexible, powerful programming language** with the ability to build abstractions. This is incredibly important in large applications.
   - **JavaScript**는 추상화 기능을 갖춘 **유연하고,  강력한 프로그래밍 언어**이다. 이것은 대규모 애플리케이션에서 매우 중요하다.
2. By unifying your markup with its corresponding view logic, React can actually make views **easier to extend and maintain**.
   - React는 마크업을 해당 view 로직과 통합함으로써, view의 확장과 유지 보수를 쉽게 만든다.
3. by baking an understanding of markup and content into JavaScript, there's **no manual string concatenation** and therefore less surface area for XSS vulnerabilities.
   - 마크업과 컨텐츠를 JavaScript에 넣으므로써, **수동 문자열 연결이 없으므로**, XSS 취약점에 대한 노출이 적다.

<br>

- We've also created [JSX](https://reactjs.org/docs/jsx-in-depth.html), an optional syntax extension, in case you prefer the readability of HTML to raw JavaScript.
  - JavaScript에 대한 HTML의 가독성을 더 선호할 경우를 대비해서 선택적 확장 문법인 [JSX](https://reactjs.org/docs/jsx-in-depth.html)도 만들었다.

------

<br>

### Reactive updates are dead simple.

###### 반응형 업데이트는 간단하다.

<br>

- React really shines when your data changes over time.
  - React는 데이터가 지속적으로 변경될 때 정말 뛰어나다.

<br>

- In a traditional JavaScript application, you need to look at what data changed and imperatively make changes to the DOM to keep it up-to-date.
  - 전통적인 JavaScript 애플리케이션에서는 어떤 데이터가 변경되었는지 확인해야 하고, 최신 정보를 유지하기 위해 DOM을 변경해야 한다.
- Even AngularJS, which provides a declarative interface via directives and data binding [requires a linking function to manually update DOM nodes](https://code.angularjs.org/1.0.8/docs/guide/directive#reasonsbehindthecompilelinkseparation).
  - 지시자와 데이터 바인딩을 통해 선언적 인터페이스를 제공하는 AngularJS에서도, 수동으로 DOM node를 업데이트 하기 위해 linking function을 필요로 한다.

<br>

- React takes a different approach.
  - React는 다르게 접근한다.

<br>

- When your component is first initialized, the `render` method is called, generating a lightweight representation of your view.
  - component가 처음 초기화되면, `render` 메소드가 호출되서 view의 간단한 표현을 생성한다.
- From that representation, a string of markup is produced, and injected into the document.
  - 이 표현으로부터, 마크업의 문자열이 생성되어, 문서에 삽입된다.
- When your data changes, the `render` method is called again.
  - 데이터가 변경되면, `render` 메소드는 다시 호출된다.
- In order to perform updates as efficiently as possible, we diff the return value from the previous call to `render` with the new one, and generate a minimal set of changes to be applied to the DOM.
  - 가능한 한 효율적으로 업데이트를 수행하기 위해, 이전 호출에서 반환한 값과 새롭게 렌더링 된 값을 비교해서 DOM에 적용할 최소한의 변경 집합을 생성한다.

<br>

> **The data returned from `render` is neither a string nor a DOM node - it's a lightweight description of what the DOM should look like.**
>
> **`render`에서 반환된 데이터는 문자열도 DOM 노드도 아니며, DOM의 모양을 나타내는 간단한 설명이다.**

<br>

- We call this process **reconciliation**.
  - 이 과정을 **reconciliation(조정, 조화)**이라고 부른다.
- Check out this [jsFiddle](http://jsfiddle.net/2h6th4ju/) to see an example of reconciliation in action.
  - 이 [jsFiddle](http://jsfiddle.net/2h6th4ju/)에서 reconciliation의 예제를 확인해라.

<br>

- Because this re-render is so fast (around 1ms for TodoMVC), the developer doesn't need to explicitly specify data bindings.
  - 이 re-render는 매우 빠르기 때문에 (TodoMVC의 경우 약 1ms), 개발자는 명시적으로 데이터 바인딩을 지정할 필요가 없다.
- We've found this approach makes it easier to build apps.
  - 이 접근이 애플리케이션 구현을 더 쉽게 해주는 것을 찾아냈다.

------

<br>

### HTML is just the beginning.

###### HTML은 시작일 뿐이다.

<br>

- Because React has its own lightweight representation of the document, we can do some pretty cool things with it:
  - React는 문서의 가벼운 표현 방법을 가지고 있기 때문에, 꽤 멋진 것들을 할 수 있다.

<br>

1. Facebook has dynamic charts that render to `<canvas>` instead of HTML.
   - Facebook은 HTML 대신 `<canvas>`를 렌더링하는 동적 차트가 있다.
2. Instagram is a "single page" web app built entirely with React and `Backbone.Router`. Designers regularly contribute React code with JSX.
   - Instagram은 오로지 React와 `Backbone.Router`로 만들어진 "단일 페이지" 웹 애플리케이션이다.
   - 디자이너는 JSX를 사용해서 React 코드에 정기적으로 기여한다.
3. We've built internal prototypes that run React apps in a web worker and use React to drive **native iOS views** via an Objective-C bridge.
   - 웹 작업자에서 React 애플리케이션을 실행하고 React를 사용해서 Objective-C 브릿지를 통해 **native iOS view**를 구동하는 내부 프로토타입을 만들었다.
4. You can run React [on the server](https://github.com/petehunt/react-server-rendering-example) for SEO, performance, code sharing and overall flexibility.
   - SEO, 성능, 코드 공유 및 전반적인 유연성을 위해 React를 서버에서 실행할 수 있다.
5. Events behave in a consistent, standards-compliant way in all browsers (including IE8) and automatically use [event delegation](https://davidwalsh.name/event-delegate).
   - 이벤트는 모든 브라우저(IE8 포함)에서 일관되고 표준을 준수하는 방식으로 동작하며, 자동으로 [이벤트 위임](https://davidwalsh.name/event-delegate)을 사용한다.

<br>

- Head on over to [https://reactjs.org](https://reactjs.org) to check out what we have built.
  - 우리가 구축한 것을 확인하려면 [https://reactjs.org](https://reactjs.org)를 살펴봐라.
- Our documentation is geared towards building apps with the framework, but if you are interested in the nuts and bolts [get in touch](https://reactjs.org/community/support.html) with us!
  - 우리의 문서는 프레임워크를 사용해서 애플리케이션을 구축하는 방향으로 만들어졌지만, 만약 작동부에 관심이 있다면 [여기](https://reactjs.org/community/support.html)서 연락을 취해라.

<br>

- Thanks for reading.

<br>