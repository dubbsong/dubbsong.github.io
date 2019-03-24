---
layout: post
title: "(공식 리액트 Docs) 02. Introducing JSX"
categories: dev
tags: react
---

###### [공식 리액트 Docs](https://reactjs.org/docs/introducing-jsx.html) 번역

<br>

## Introducing JSX

###### JSX 소개

<br>

- Consider this variable declaration:
  - 다음 변수 선언을 살펴보자.

```react
const element = <h1>Hello World!</h1>;
```

<br>

- This funny tag syntax is neither a string nor HTML.
  - 이 이상한 태그 구문은 문자열도 아니고, HTML도 아니다.
- It is called JSX, and it is a syntax extension to JavaScript.
  - 이는 JSX라는 JavaScript의 구문 확장이다.
- We recommend using it with React to describe what the UI should look like.
  - UI를 그리기 위해 React와 함께 사용하는 것이 좋다.
- JSX may remind you of a template language, but it comes with the full power of JavaScript.
  - JSX가 템플릿 언어라고 생각할 수 있지만, JavaScript의 모든 기능을 포함한다.

- JSX produces React "elements".
  - JSX는 React "element"를 생성한다.

------

<br>

#### Why JSX?

###### 왜 JSX를 사용하는가?

<br>

- React embraces the fact that rendering logic is inherently coupled with other UI logic: how events are handled, how the state changes over time, and how the data is prepared for display.
  - React는 렌더링 로직이 다른 UI 로직과 본직적으로 연결되어 있다는 사실을 채택한다.
  - (이벤트가 어떻게 처리되는지, 시간이 지남에 따라 state가 어떻게 변하는지, data가 표시되기 위해 어떤 준비가 필요한지)

<br>

- Instead of artificially separating *technologies* by putting markup and logic in separate files, React [separates concerns](https://en.wikipedia.org/wiki/Separation_of_concerns) with loosely coupled units called "components" that contain both.
  - React는 마크업과 로직을 별도의 파일에 넣어 인위적으로 분리하지 않는다.
  - 대신 마크업과 로직 둘 다 포함하는 "컴포넌트" 단위를 [관심사와 분리](https://en.wikipedia.org/wiki/Separation_of_concerns)한다.

<br>

- React [doesn't require](https://reactjs.org/docs/react-without-jsx.html) using JSX, but most people find it helpful as a visual aid when working with UI inside the JavaScript code.
  - React는 JSX를 사용하지 않아도 되지만, 대부분의 사람들은 JavaScript 코드 내부의 UI와 작업할 때 시각적으로 유용하다고 생각한다.
- It also allows React to show more useful error and warning messages.
  - JSX를 사용하면, React가 더 유용한 error 및 경고 메시지를 보여줄 수도 있다.

------

<br>

## Embedding Expressions in JSX

###### JSX에 표현식 삽입하기

<br>

- In the example below, we declare a variable called `name` and then use it inside JSX by wrapping it in curly braces:
  - 아래 예제에서는 `name`이라는 변수를 선언한 다음, 중괄호로 감싼 JSX 내부에서 사용한다.

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
  - 유효한 [JavaScript 표현식](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Expressions_and_Operators#Expressions)을 JSX의 중괄호 내에 넣을 수 있다.
- For example, `2 + 2`, `user.firstName`, or `formatName(user)` are all valid JavaScript expressions.
  - 예를 들어, `2 + 2`, `user.firstName`, `formatName(user)`는 모두 유효한 JavaScript 표현식이다.

<br>

- In the example below, we embed the result of calling a JavaScript function, `formatName(user)`, into an `<h1>` element.
  - 아래 예제에서는 `<h1>` element에 JavaScript 함수 `formatName(user)`을 호출한 결과를 삽입한다.

```react
function formatName(user) {
  return user.firstName + ' ' + user.lastName;
}

const user = {
  firstName: 'Samuel',
  lastName: 'Azor'
};

const element = (
  <h1>Hello, {formatName(user)}!</h1>
);

ReactDOM.render(
  element,
  document.getElementById('root')
);
```

[코드 실행 확인](https://reactjs.org/redirect-to-codepen/introducing-jsx)

<br>

- We split JSX over multiple lines for readability.
  - 가독성을 위해 JSX를 여러 줄로 나누었다.
- While it isn't required, when doing this, we also recommend wrapping it in parentheses to avoid the pitfalls of [automatic semicolon insertion](https://stackoverflow.com/questions/2846283/what-are-the-rules-for-javascripts-automatic-semicolon-insertion-asi).
  - 필수는 아니지만, [자동 세미콜론 삽입](https://stackoverflow.com/questions/2846283/what-are-the-rules-for-javascripts-automatic-semicolon-insertion-asi)의 함정을 피하기 위해 괄호로 감싸는 것이 좋다.

------

<br>

#### JSX is an Expression Too

###### JSX도 표현식이다

<br>

- After compilation, JSX expressions become regular JavaScript function calls and evaluate to JavaScript objects.
  - JSX 표현식은 컴파일 후 일반 JavaScript 함수 호출이 되고, JavaScript 객체로 평가된다.
- This means that you can use JSX inside of `if` statements and `for` loops, assign it to variables, accept it as arguments, and return it from functions:
  - 즉, JSX는 `if` 문과 `for` 루프에서 사용할 수 있고, 변수를 할당할 수 있고, 인수로 받아 함수에서 반환할 수 있다.

```react
function getGreeting(user) {
  if (user) {
    return <h1>Hello, {formatName(user)}!</h1>;
  }
  return <h1>Hello, Stranger.</h1>;
}
```

------

<br>

#### Specifying Attributes with JSX

###### JSX로 속성 지정하기

<br>

- You may use quotes to specify string literals as attributes:
  - 따옴표를 사용해서 문자열 리터럴을 속성으로 지정할 수 있다.

```react
const element = <div tabIndex="0"></div>;
```

<br>

- You may also use curly braces to embed a JavaScript expression in an attribute:
  - 중괄호를 사용해서 JavaScript 표현식을 속성에 삽입할 수도 있다.

```react
const element = <img src={user.avatarUrl}></img>;
```

<br>

- Don't put quotes around curly braces when embedding a JavaScript expression in an attribute.
  - JavaScript 표현식을 속성에 삽입할 때, 중괄호를 따옴표로 감싸지 않는다.
- You should either use quotes or curly braces, but not both in the same attribute.
  - 따옴표 또는 중괄호를 사용할 수 있지만, 같은 속성에 둘 다 사용할 수는 없다.

<br>

> **Warning:**
>
> Since JSX is closer to JavaScript than to HTML, React DOM uses `camelCase` property naming convention instead of HTML attribute names.
>
> JSX는 HTML보다 JavaScript에 가까우므로, React DOM은 `camelCase` 속성 명명 규칙을 사용한다.

> For example, `class` becomes [className](https://developer.mozilla.org/en-US/docs/Web/API/Element/className) in JSX, and `tabindex` becomes [tabIndex](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/tabIndex).
>
> 예를 들어, JSX에서 `class`는 [className](https://developer.mozilla.org/en-US/docs/Web/API/Element/className)이 되고, `tabindex`는 [tabIndex](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/tabIndex)가 된다.

------

<br>

#### Specifying Children with JSX

###### JSX로 children 지정하기

<br>

- If a tag is empty, you may close it immediately with `/>`, like XML:
  - empty 태그라면, XML처럼 `/>`를 사용해서 태그를 즉시 닫을 수 있다.

```react
const element = <img src={user.avatarUrl} />;
```

<br>

- JSX tags may contain children:
  - JSX 태그는 children을 포함할 수 있다.

```react
const element = (
  <div>
    <h1>Ssup bro?</h1>
    <h2>How are you?</h2>
  </div>
);
```

------

<br>

#### JSX Prevent Injection Attacks

###### JSX는 주입 공격을 방지한다

<br>

- It is safe to embed user input in JSX:
  - 사용자 입력을 JSX에 삽입하는 것은 안전하다.

```react
const title = response.potentiallyMaliciousInput;

// 이 코드는 안전하다
const element = <h1>{title}</h1>;
```

<br>

- By default, React DOM [escapes](https://stackoverflow.com/questions/7381974/which-characters-need-to-be-escaped-in-html) any values embedded in JSX before rendering them.
  - 기본적으로 React DOM은 렌더링 하기 전에, JSX에 삽입된 모든 값을 [이스케이프](https://stackoverflow.com/questions/7381974/which-characters-need-to-be-escaped-in-html) 한다.
- Thus it ensures that you can never inject anything that's not explicitly written in your application.
  - 따라서 애플리케이션에 명시적으로 작성되지 않은 것은 삽입할 수 없다.
- Everything is converted to a string before being rendered.
  - 모든 것은 렌더링 되기 전에 문자열로 변환된다.
- This helps prevent [XSS](https://en.wikipedia.org/wiki/Cross-site_scripting) (cross-site-scripting) attacks.
  - 이는 [XSS](https://en.wikipedia.org/wiki/Cross-site_scripting) (사이트 간 스크립팅) 공격을 방지할 수 있다.

------

<br>

#### JSX Represents Objects

###### JSX는 객체를 나타낸다

<br>

- Babel compiles JSX down to `React.createElement()` calls.
  - Babel은 JSX를 `React.createElement()` 호출로 컴파일한다.
- These two examples are identical:
  - 다음 두 예제는 동일하다.

<br>

###### Example 01

```react
const element = (
  <h1 className="greeting">Hello World!</h1>
);
```

<br>

###### Example 02

```react
const element = React.createElement(
  'h1',
  {className: 'greeting'},
  'Hello World!'
);
```

<br>

- `React.createElement()` performs a few checks to help you write bug-free code but essentially it creates an object like this:
  - `React.createElement()`는 버그 없는 코드를 작성하는 데 도움이 되는 검사를 수행하지만, 기본적으로 다음과 같은 객체를 생성한다.

```react
const element = {
  type: 'h1',
  props: {
    className: 'greeting',
    children: 'Hello World!'
  }
};
```

<br>

- These objects are called "React elements".
  - 이러한 객체를 "React element"라고 한다.
- You can think of them as descriptions of what you want to see on the screen.
  - 화면에서 보고 싶은 것에 대한 설명으로 생각할 수 있다.
- React reads these objects and uses them to construct the DOM and keep it up to date.
  - React는 이러한 객체를 읽고, 이를 사용해서 DOM을 구성하고, 이를 최신 상태로 유지한다.

<br>

> **Tip:**
>
> We recommend using the ["Babel" language definition](https://babeljs.io/docs/en/editors/) for your editor of choice so that both ES6 and JSX code is properly highlighted.
>
> ES6와 JSX 코드가 올바르게 강조 표시되도록 선택한 에디터에 ["Babel" 언어 정의](https://babeljs.io/docs/en/editors/)를 사용하는 것이 좋다.

------

<br>