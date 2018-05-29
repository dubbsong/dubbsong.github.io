---
layout: post
title: "리액트 공식 문서 번역 - React (basic)"
categories: react
tags: React basic
---

[React 공식 문서 링크](https://reactjs.org/)

<br>

## React (리액트)

- A JavaScript library for building user interfaces.
  - 유저 인터페이스 구축을 위한 JS 라이브러리.

<br>

#### Declarative (선언적)

- React makes it painless to create interactive UIs.
  - React는 대화형 UI를 어렵지 않게 만들 수 있다.
- Design simple views for each state in your application, and React will efficiently update and render just the right components when your data changes.
  - 애플리케이션의 각 state에 대한 간단한 view를 디자인해봐라.
  - React는 데이터에 변화가 있으면 컴포넌트를 효과적으로 업데이트하고 렌더링한다.
- Declarative views make your code more predictable and easier to debug.
  - 선언적 view는 코드를 더 잘 예측할 수 있게, 디버깅을 더 쉽게 만든다.

<br>

#### Component-Based (컴포넌트 기반)

- Build encapsulated components that manage their own state, then compose them to make complex UIs.
  - 자체 state를 관리하는 캡슐화된 컴포넌트를 작성한 다음, 복잡한 UI를 만들 수 있도록 구성해봐라.
- Since component logic is written in JavaScript instead of templates, you can easily pass rich data through your app and keep state out of the DOM.
  - 컴포넌트 로직은 템플릿 대신 JavaScript로 작성되므로, 앱을 통해 풍부한 데이터를 쉽게 전달할 수 있고, DOM에서 state를 유지할 수 있다.

<br>

#### Learn Once, Write Anywhere (한 번 배우고, 어디서나 사용해라)

- We don't make assumptions about the rest of your technology stack, so you can develop new features in React without rewriting existing code.
  - 기술 스택의 나머지 부분에 대해서는 가정하지 않았으므로, 기존 코드를 다시 작성하지 않고, React에서 새로운 기능을 개발할 수 있다.
- React can also render on the server using Node and power mobile apps using [React Native](https://facebook.github.io/react-native/).
  - React는 [React Native](https://facebook.github.io/react-native/)를 사용하고, Node와 power 모바일 앱을 사용해서, 서버에 렌더링도 할 수 있다.

<br>

## A simple Component (단순 컴포넌트)

- React components implement a `render()` method that takes input data and returns what to display.
  - React 컴포넌트는 입력 데이터를 가져와서 표시할 항목을 반환하는 `render()` 메소드를 구현한다.
- This example uses an XML-like syntax called JSX.
  - 이 예제에서는 JSX라는 XML과 유사한 문법을 사용한다.
- Input data that is passed into the component can be accessed by `render()` via `this.props`.
  - 컴포넌트에 전달된 입력 데이터는 `this.props`를 통한 `render()`에 의해 액세스 할 수 있다.
- **JSX is optional and not required to use React.**
  - **JSX는 선택사항이며, React를 사용하는 데 필요가 없다.**
- Try the [Babel REPL](https://babeljs.io/repl/#?presets=react&code_lz=MYewdgzgLgBApgGzgWzmWBeGAeAFgRgD4AJRBEAGhgHcQAnBAEwEJsB6AwgbgChRJY_KAEMAlmDh0YWRiGABXVOgB0AczhQAokiVQAQgE8AkowAUAcjogQUcwEpeAJTjDgUACIB5ALLK6aRklTRBQ0KCohMQk6Bx4gA) to see the raw JavaScript code produced by the JSX compilation step.
  - [Babel REPL](https://babeljs.io/repl/#?presets=react&code_lz=MYewdgzgLgBApgGzgWzmWBeGAeAFgRgD4AJRBEAGhgHcQAnBAEwEJsB6AwgbgChRJY_KAEMAlmDh0YWRiGABXVOgB0AczhQAokiVQAQgE8AkowAUAcjogQUcwEpeAJTjDgUACIB5ALLK6aRklTRBQ0KCohMQk6Bx4gA)을 사용해서, JSX 컴파일 단계에서 생성된 가공되지 않은 JavaScript 코드를 확인해라.

```react
// Not using JSX

class HelloMessage extends React.Component {
   render() {
      return React.createElement (
      	"div",
         null,
         "Hello",
         this.props.name
      );
   }
}

ReactDOM.render(React.createElement(HelloMessage, { name: "Song" }), mountNode);
```

```react
// Using JSX

class HelloMessage extends React.Component {
   render() {
      return (
      	<div>
         	Hello {this.props.name}
         </div>
      );
   }
}

ReactDOM.render(
	<HelloMessage name="Song" />,
   mountNode
);
```

```react
// RESULT

Hello Song
```

<br>

## A Stateful Component (state 변화가 있는 컴포넌트)

- In addition to taking input data (accessed via `this.props`), a component can maintain internal state data (accessed via `this.state`).
  - 입력 데이터(`this.props`를 통해 액세스된 데이터)를 취하는 것뿐만 아니라, 컴포넌트는 내부 state 데이터(`this.state`를 통해 액세스된 데이터)를 유지할 수 있다.
- When a component's state data changes, the rendered markup will be updated by re-invoking `render()`.
  - 컴포넌트의 state 데이터가 변경되면, `render()`를 다시 호출해서 렌더링 된 마크업을 업데이트한다.

```react
// Using JSX

class Timer extends React.Component {
   constructor(props) {
      super(props);
      this.state = { seconds: 0 };
   }
   
   tick() {
      this.setState(prevState => ({
         seconds: prevState.seconds + 1
      }));
   }
   
   componentDidMount() {
      this.interval = setInterval(() => this.tick(), 1000);
   }
   
   componentWillUnmount() {
      clearInterval(this.interval);
   }
   
   render() {
      return (
      	<div>
         	Seconds: {this.state.seconds}
         </div>
      );
   }
}

ReactDOM.render(<Timer />, mountNode);
```

```react
// RESULT

Seconds: (계속 1초씩 증가하는 숫자가 표시된다)
```

<br>

## An Application

- Using `props` and `state`, we can put together a small Todo application.
  - `props`와 `state`를 사용해서 작은 Todo 애플리케이션을 만들 수 있다.
- This example uses `state` to track the current list of items as well as the text that the user has entered.
  - 이 예제에서는 `state`를 사용해서 유저가 입력한 텍스트뿐만 아니라 항목의 현재 목록을 추적한다.
- Although event handlers appear to be rendered inline, they will be collected and implemented using event delegation.
  - 이벤트 핸들러는 인라인으로 렌더링되어서 표시되지만, 이벤트 위임을 사용해서 수집되고 구현된다.

```react
// Using JSX

class TodoApp extends React.Component {
   constructor(props) {
      super(props);
      this.state = { items: [], text: '' };
      this.handleChange = this.handleChange.bind(this);
      this.handleSubmit = this.handleSubmit.bind(this);
   }
   
   render() {
      return (
      	<div>
         	<h3>TODO</h3>
            <TodoList items={this.state.items} />
            <form onSubmit={this.handleSubmit}>
            	<label htmlFor="new-todo">
               	What needs to be done?
               </label>
               <input
                  id="new-todo"
                  onChange={this.handleChange}
                  value={this.state.text}
					/>
               <button>
               	Add #{this.state.items.length + 1}
               </button>
            </form>
         </div>
      );
   }
   
   handleChange(e) {
      this.setState({ text: e.target.value });
   }
   
   handleSubmit(e) {
      e.preventDefault();
      if (!this.state.text.length) {
         return;
      }
      const newItem = {
         text: this.state.text,
         id: Date.now()
      };
      this.setState(prevState => ({
         items: prevState.items.concat(newItem),
         text: ''
      }));
   }
}

class TodoList extends React.Component {
   render() {
      return (
      	<ul>
         	{this.props.items.map(item => (
            	<li key={item.id}>{item.text}</li>
            ))}
         </ul>
      );
   }
}

ReactDOM.render(<TodoApp />, mountNode);
```

```react
// RESULT

TODO
- (something)

What needs to be done?
[  input 창  ]
[ Add #2 버튼 ]
```

<br>

## A Component Using External Plugins (외부 플러그인을 사용한 컴포넌트)

- React is flexible and provides hooks that allow you to interface with other libraries and frameworks.
  - React는 유연하며 다른 라이브러리나 프레임워크와 인터페이스 할 수 있는 후킹을 제공한다.
  - `hooking`: 각종 컴퓨터 프로그램에서 소프트웨어 구성 요소 간에 발생하는 함수 호출, 메시지, 이벤트 등을 중간에서 바꾸거나 가로채는 명령, 방법, 기술이나 행위를 말한다. 이러한 간섭된 함수 호출, 메시지, 이벤트를 처리하는 코드를 `hook`라고 한다.
- This example uses **remarkable**, an external Markdown library, to convert the `<textarea>`'s value in real time.
  - 이 예제는 **주목할만한** 외부 마크다운 라이브러리를 사용해서, `<textarea>`의 값을 실시간으로 변환한다.

```react
class MarkdownEditor extends React.Component {
   constructor(props) {
      super(props);
      this.handleChange = this.handleChange.bind(this);
      this.state = { value: 'Hello, **world**' };
   }
   
   handleChange(e) {
      this.setState({ value: e.target.value });
   }
   
   getRawMarkup() {
      const md = new Remarkable();
      return { __html: md.render(this.state.value) };
   }
   
   render() {
      return (
      	<div className="MarkdownEditor">
         	<h3>Input</h3>
            <label htmlFor="markdown-content">
            	Enter some markdown
            </label>
            <textarea
            	id="markdown-content"
               onChange={this.handleChange}
               defaultValue={this.state.value}
            />
            <h3>Output</h3>
            <div
               className="content"
               dangerouslySetInnerHTML={this.getRawMarkup()}
            />
         </div>
      );
   }
}

ReactDOM.render(<MarkdownEditor />, mountNode);
```

```react
// RESULT

Input
Enter some markdown
[ input 창 ]

Output
(input 창에 입력한 내용이 그대로 표시된다)
```

<br>