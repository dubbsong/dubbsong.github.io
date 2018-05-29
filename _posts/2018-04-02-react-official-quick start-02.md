---
layout: post
title: "리액트 공식 문서 번역 - 02. Introducing JSX (quick start)"
categories: react
tags: react
---

[React 공식 문서 링크](https://reactjs.org/docs/introducing-jsx.html)

<br>

## Introducing JSX (JSX 소개)

- Consider this variable declaration:
  - 다음 변수 선언을 고려해라.

```react
const element = <h1>Hello, world!</h1>;
```

- This funny tag syntax is neither a string nor HTML.
  - 이 재미있는 태그 문법은 문자열도 아니고 HTML도 아니다.

<br>

- It is called JSX, and it is a syntax extension to JavaScript.
  - 이 문법은 JSX라고 불리는, JavaScript의 확장 문법이다.
- We recommend using it with React to describe what the UI should look like.
  - React로 UI를 표현할 때 JSX를 사용하는 것이 좋다.
- JSX may remind you of a template language, but it comes with the full power of JavaScript.
  - JSX는 템플릿 언어를 연상시킬 수도 있지만, JavaScript의 모든 기능을 제공한다.

<br>

- JSX produces React "elements".
  - JSX는 React "element"를 생성한다.
- We will explore rendering them to the DOM in the [next section](https://reactjs.org/docs/rendering-elements.html).
  - [다음 섹션](https://reactjs.org/docs/rendering-elements.html)에서 DOM에 렌더링 하는 것을 살펴볼 것이다.
- Below, you can find the basics of JSX necessary to get you started.
  - 아래에서, JSX를 시작하는 데 필요한 기본 사항을 확인할 수 있다.

<br>

#### Why JSX?

- React embraces the fact that rendering logic is inherently coupled with other UI logic: how events are handled, how the state changes over time, and how the data is prepared for display.
  - React는 렌더링 로직이 다른 UI 로직과 본질적으로 결합되어 있다는 사실을 포함한다.
  - 이벤트 처리 방법, 시간 경과에 따른 state 변경 방법, 데이터 표시 준비 방법을 포함한다.

<br>

- Instead of artificially separating *technologies* by putting markup and logic in separate files, React [separates concerns](https://en.wikipedia.org/wiki/Separation_of_concerns) with loosely coupled units called "components" that contain both.
  - React는 별도의 파일에 마크업과 로직을 넣어서 기술을 인위적으로 분리하는 대신,
  - 둘 다 포함하는 "컴포넌트"라고 불리는 느슨하게 연결된 unit과 [관심사를 분리](https://en.wikipedia.org/wiki/Separation_of_concerns)한다.
- We will come back to components in a [further section](https://reactjs.org/docs/components-and-props.html), but if you're not yet comfortable putting markup in JS, this talk might convince you otherwise.
  - [이후 섹션](https://reactjs.org/docs/components-and-props.html)에서 컴포넌트로 돌아올 예정이지만, JS에서 마크업을 익히기가 쉽지 않다면, 이 말은 그렇지 않을 수도 있다.

<br>

- React doesn't require using JSX, but most people find it helpful as a visual aid when working with UI inside the JavaScript code.
  - React는 JSX를 사용할 필요가 없지만, 대부분의 사람들은 JavaScript 코드 내부의 UI로 작업할 때 시작적 도움으로 유용하다고 생각한다.
- It also allows React to show more useful error and warning messages.
  - React가 더 유용한 에러 메시지와 경고 메시지도 표시할 수 있다.

<br>

- With that out of the way, let's get started!
  - 어쨌든, 시작해보자.

<br>

#### Embedding Expression in JSX (JSX에 표현식 삽입)

- In the example below, we declare a variable called `name` and then use it inside JSX by wrapping it in curly braces:
  - 아래 예제에서, `name`이라는 변수를 선언한 다음 괄호로 묶어서 JSX 안에서 사용한다.

```react
const name = 'Samuel Azor';
const element = <h1>Hello, {name}</h1>;

ReactDOM.render(
	element,
   document.getElementById('root')
);
```

<br>

- You can put any valid [JavaScript expression](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Expressions_and_Operators#Expressions) inside the curly braces in JSX.
  - 유효한 [JavaScript 표현식](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Expressions_and_Operators#Expressions)을 JSX의 중괄호 안에 넣을 수 있다.
- For example, `2 + 2`, `user.firstName`, or `formatName(user)` are all valid JavaScript expressions.
  - 예를 들어, `2 + 2`, `user.firstName`, `formatName(user)`은 모두 유효한 JavaScript 표현식이다.

<br>

- In the example below, we embed the result of calling a JavaScript function, `formatName(user)`, into an `<h1>` element.
  - 아래 예제에서, `<h1>` element에 JavaScript 함수 `formatName(user)`를 호출한 결과를 포함한다.

```react
function formatNumber(user) {
   return user.firstName + ' ' + user.lastName;
}

const user = {
   firstName: 'Samuel',
   lastName: 'Azor'
};

const element = (
	<h1>
   	Hello, {formatName(user)}!
   </h1>
);

ReactDOM.render(
	element,
   document.getElementById('root')
);
```

[Try it on CodePen](https://codepen.io/pen?&editors=0010)

<br>

- We split JSX over multiple lines for readability.
  - 가독성을 위해 JSX를 여러 줄로 나누었다.
- While it isn't required, when doing this, we also recommend wrapping it in parentheses to avoid the pitfalls of [automatic semicolon insertion](https://stackoverflow.com/questions/2846283/what-are-the-rules-for-javascripts-automatic-semicolon-insertion-asi).
  - 이 작업을 할 때 필수는 아니지만, 자동 세미콜론 삽입의 함정을 피하기 위해서 괄호로 묶는 것이 좋다.

<br>

#### JSX is an Expression Too (JSX는 표현식이기도 하다)

- After compilation, JSX expressions become regular JavaScript function calls and evaluate to JavaScript objects.
  - 컴파일이 끝나면, JSX 표현식이 정규 JavaScript 함수 호출이 되고, JavaScript 객체로 평가된다.

<br>

- This means that you can use JSX inside of `if` statements and `for` loops, assign it to variables, accept it as arguments, and return it from functions:
  - 즉, `if` 문과 `for` 루프에서 JSX를 사용할 수 있고, 변수에 할당하고, 인수로 받아들여, 함수에서 반환할 수 있다.

```react
function getGreeting(user) {
   if (user) {
      return <h1>Hello, {formatName(user)}!</h1>;
   }
   return <h1>Hello, Stranger.</h1>;
}
```

<br>

#### Specifying Attributes with JSX (JSX로 속성 지정)

- You may use quotes to specify string literals as attributes:
  - 따옴표를 사용해서 문자열 리터럴을 속성으로 지정할 수 있다:

```react
const element = <div tabIndex="0"></div>;
```

<br>

- You may also use curly braces to embed a JavaScript expression in an attribute:
  - 중괄호를 사용해서 속성에 JavaScript 표현식을 삽입할 수도 있다.

```react
const element = <img src={user.avatarUrl}></img>;
```

<br>

- Don't put quotes around curly braces when embedding a JavaScript expression in an attribute.
  - 속성에 JavaScript 표현식을 삽입할 때, 중괄호를 따옴표로 묶지 마라.
- You should either use quotes (for string values) or curly braces (for expressions), but not both in the same attribute.
  - 따옴표(문자열 값의 경우) 또는 중괄호(표현식의 경우) 중 하나를 사용해야 하지만, 같은 속성에 사용해야 하는 것은 아니다.

<br>

> **Warning:**
>
> Since JSX is closer to JavaScript than to HTML, React DOM uses `camelCase` property naming convention instead of HTML attribute names.
>
> JSX는 HTML보다 JavaScript에 가까우므로, React DOM은 HTML 속성 이름 대신 `camelCase` 속성 네이밍 컨벤션을 사용한다.

> For example, `class` becomes [className](https://developer.mozilla.org/en-US/docs/Web/API/Element/className) in JSX, and `tabindex` becomes [tabIndex](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/tabIndex).
>
> 예를 들어, `class`는 JSX에서 [className이](https://developer.mozilla.org/en-US/docs/Web/API/Element/className) 되고, `tabIndex`는 [tabIndex](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/tabIndex)가 된다.

<br>

#### Specifying Children with JSX (JSX로 자식 지정)

- If a tag is empty, you may close it immediately with `/>`, like XML:
  - 태그가 비어 있으면, XML처럼 `/>`로 즉시 닫아야 한다.

```react
const element = <img src={user.avatarUrl} />;
```

<br>

- JSX tags may contain children:
  - JSX 태그는 자식이 포함될 수 있다:

```react
const element = (
	<div>
   	<h1>Hello!</h1>
      <h2>Good to see you here.</h2>
   </div>
);
```

<br>

#### JSX Prevents Injection Attacks (JSX 삽입 공격 방지하기)

- It is safe to embed user input in JSX:
  - JSX에서 유저 입력은 안전하다.

```react
const title = response.potentiallyMaliciousInput;
// This is safe:
const element = <h1>{title}</h1>;
```

<br>

- By default, React DOM [escapes](https://stackoverflow.com/questions/7381974/which-characters-need-to-be-escaped-on-html) any values embedded in JSX before rendering them.
  - 기본적으로, React DOM은 렌더링 전에 JSX에 삽입된 값들을 이스케이프 처리한다.
- Thus it ensures that you can never inject anything that's not explicitly written in your application.
  - 따라서 애플리케이션에 명시적으로 작성되지 않은 값들은 절대 삽입할 수 없기 때문에 안전을 보장한다.
- Everything is converted to a string before being rendered.
  - 모든 것은 렌더링 되기 전에 문자열로 변환된다.
- This helps prevent [XSS (cross-site-scripting)](https://en.wikipedia.org/wiki/Cross-site_scripting) attacks.
  - 이렇게 하면 [XSS (사이트 간 스크립팅)](https://en.wikipedia.org/wiki/Cross-site_scripting) 공격을 방지할 수 있다.

<br>

#### JSX Represents Objects (JSX 객체 나타내기)

-  Babel compiles JSX down to `React.createElement()` calls.
  - Babel은 JSX를 `React.createElement()` 호출로 컴파일한다.

<br>

- These two examples are identical:
  - 이 두 예제는 동일하다.

```react
const element = (
	<h1 className="greeting">
   	Hello, world!
   </h1>
);
```

```react
const element = React.createElement(
	'h1',
   {className: 'greeting'},
   'Hello, world!'
);
```

<br>

- `React.createElement()` performs a few checks to help you write bug-free code but essentially it creates an object like this:
  - `React.createElement()`는 버그 없는 코드를 작성하는 데 도움이 되는 몇 가지 검사를 수행하지만, 기본적으로 다음과 같은 객체를 생성한다.

```react
// Note: this structure is simplified
const element = {
   type: 'h1',
   props: {
      className: 'greeting',
      children: 'Hello, world!'
   }
};
```

<br>

- These objects are called "React elements".
  - 이러한 객체를 "React elements"라고 한다.
- You can think of them as descriptions of what you want to see on the screen.
  - 이러한 객체들은 화면에서 보고 싶은 내용에 대한 설명으로 생각해도 좋다.
- React reads these objects and uses them to construct the DOM and keep it up to date.
  - React는 이러한 객체를 읽고 사용해서 DOM을 구성하고 최신 상태로 유지한다.

<br>

- We will explore rendering React elements to the DOM in the next section.
  - 다음 섹션에서 React element를 DOM에 렌더링 하는 방법을 살펴볼 것이다.

<br>

> **Tip:**
>
> We recommend using the ["Babel" language definition](http://babeljs.io/docs/editors) for your editor of choice so that both ES6 and JSX code is properly highlighted.
>
> ES6와 JSX 코드가 모두 올바르게 표시되도록 선택한 에디터에 ["Babel" language definition](http://babeljs.io/docs/editors)을 사용하는 것이 좋다.

> This website uses the [Oceanic Next](https://labs.voronianski.com/oceanic-next-color-scheme/) color scheme which is compatible with it.
>
> 이 웹사이트는 호환 가능한 [Oceanic Next](https://labs.voronianski.com/oceanic-next-color-scheme/) 색 구성표를 사용한다.

<br>