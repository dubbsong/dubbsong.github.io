---
layout: post
title: "공식 리액트 문서 번역 - 05. State and Lifecycle (Main Concepts)"
categories: react
tags: react
---

[공식 리액트 문서 링크](https://reactjs.org/docs/state-and-lifecycle.html)

<br>

## State and Lifecycle

###### state와 lifecycle

<br>

- ###### This page introduces the concept of state and lifecycle in a React component.

  - ###### 이 페이지에서는 React 컴포넌트에서의 state와 lifecycle 개념을 소개한다.

- ###### You can find a [detailed component API reference here](https://reactjs.org/docs/react-component.html).

  - ###### [자세한 컴포넌트 API 참조는 여기](https://reactjs.org/docs/react-component.html)서 확인할 수 있다.

------

<br>

- Consider the ticking clock example from [one of the previous sections](https://reactjs.org/docs/rendering-elements.html#updating-the-rendered-element).
  - [이전 섹션 중 하나](https://reactjs.org/docs/rendering-elements.html#updating-the-rendered-element)에서 똑딱 시계 예제를 보자.
- In [Rendering Elements](https://reactjs.org/docs/rendering-elements.html#rendering-an-element-into-the-dom), we have only learned one way to update the UI.
  - [Rendering Elements](https://reactjs.org/docs/rendering-elements.html#rendering-an-element-into-the-dom)에서, UI를 업데이트 하는 방법 중 하나만 배웠다.
- We call `ReactDOM.render()` to change the rendered output:
  - `ReactDOM.render()`를 호출해서 렌더링 된 출력을 변경한다.

```react
function tick() {
   const element = (
   	<div>
      	<h1>Hello, world!</h1>
         <h2>It is {new Date().toLocaleTimeString()}.</h2>
      </div>
   );
   ReactDOM.render(
   	element,
      document.getElementById('root')
   );
}

setInterval(tick, 1000);
```

[CodePen에서 시도](https://codepen.io/gaearon/pen/gwoJZk?editors=0010)

<br>

- In this section, we will learn how to make the `Clock` component truly reusable and encapsulated.
  - 이 섹션에서는, `Clock` 컴포넌트를 올바르게 재사용 및 캡슐화하는 방법을 배운다.
- It will set up its own timer and update itself every second.
  - 자체 타이머를 설정하고 매초 업데이트 한다.

<br>

- We can start by encapsulating how the clock looks:
  - 시계가 어떻게 보이는지 캡슐화함으로써 시작할 수 있다.

```react
function Clock(props) {
   return (
   	<div>
      	<h1>Hello, world!</h1>
         <h2>It is {props.date.toLocaleTimeString()}.</h2>
      </div>
   );
}

function tick() {
   ReactDOM.render(
   	<Clock date={new Date()} />,
      document.getElementById('root')
   );
}

setInterval(tick, 1000);
```

[CodePen에서 시도](https://codepen.io/gaearon/pen/dpdoYR?editors=0010)

<br>

- However, it misses a crucial requirement: the fact that the `Clock` sets up a timer and updates the UI every second should be an implementation detail of the `Clock`.
  - 하지만, 중요한 요구 사항을 빠뜨린다.
  - `Clock`이 타이머를 설정하고 매초 UI를 업데이트한다는 사실은 `Clock`의 구현 세부사항이어야 한다.

<br>

- Ideally we want to write this once and have the `Clock` update itself:
  - 이상적으로, 이것을 한 번 작성하고 `Clock` 자체를 업데이트하려고 한다.

```react
ReactDOM.render(
	<Clock />,
   document.getElementById('root')
);
```

<br>

- To implement this, we need to add "state" to the `Clock` component.
  - 이를 구현하려면, `Clock` 컴포넌트에 "state"를 추가해야 한다.

<br>

- State is similar to props, but it is private and fully controlled by the component.
  - state는 props와 비슷하지만, 독립적이며 컴포넌트에 의해 완전히 제어된다.

<br>

- We mentioned before that components defined as classes have some additional features.
  - 앞서 클래스에 정의된 컴포넌트에는 몇 가지 추가 기능이 있다.
- Local state is exactly that: a feature available only to classes.
  - 로컬 state는 정확히 클래스에 사용 가능한 기능이다.

------

<br>

### Converting a Function to a Class

###### 함수를 클래스로 변환

<br>

- You can convert a functional component like `Clock` to a class in five steps:
  - `Clock`과 같은 함수 컴포넌트를 5단계의 클래스로 변환할 수 있다.

<br>

1. Create an [ES6 class](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Classes), with the same name, that extends `React.Component`.
   - `React.Component`를 확장하는 동일한 이름의 [ES6 클래스](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Classes)를 만든다.
2. Add a single empty method to it called `render()`.
   - `render()`라는 단일 빈 메소드를 추가해라.
3. Move the body of the function into the `render()` method.
   - 함수의 body를 `render()` 메소드로 옮겨라.
4. Replace `props` with `this.props` in the `render()` body.
   - `props`를 `render()` body 안에서 `this.props`로 대체해라.
5. Delete the remaining empty function declaration.
   - 나머지 빈 함수 선언을 삭제해라.

```react
class Clock extends React.Component {
   render() {
      return (
      	<div>
         	<h1>Hello, world!</h1>
            <h2>It is {this.props.date.toLocaleTimeString()}.</h2>
         </div>
      );
   }
}
```

[CodePen에서 시도](https://codepen.io/gaearon/pen/zKRGpo?editors=0010)

<br>

- `Clock` is now defined as a class rather than a function.
  - `Clock`은 이제 함수가 아닌 클래스로 정의된다.

<br>

- This lets us use additional features such as local state and lifecycle hooks.
  - 이를 통해 로컬 state 및 lifecycle hook와 같은 추가 기능을 사용할 수 있다.

------

<br>

### Adding Local State to a Class

###### 클래스에 로컬 state 추가

<br>

- We will move the `date` from props to state in three steps:
  - 3단계로 `date`를 props로부터 state로 옮길 것이다.

<br>

- 1) Replace `this.props.date` with `this.state.date` in the `render()` method:
  - `render()` 메소드에서 `this.props.date`를 `this.state.date`로 대체해라.

```react
class Clock extends React.Component {
   render() {
      return (
      	<div>
         	<h1>Hello, world!</h1>
            <h2>It is {this.state.date.toLocalTimeString()}.</h2>
         </div>
      );
   }
}
```

<br>

- 2) Add a [class constructor](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Classes#Constructor) that assigns the initial `this.state`:
  - 초기 `this.state`를 할당하는 [클래스 생성자](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Classes#Constructor)를 추가해라.

```react
class Clock extends React.Component {
   constructor(props) {
      super(props);
      this.state = {date: new Date()};
   }
   
   render() {
      return (
      	<div>
         	<h1>Hello, world!</h1>
            <h2>It is {this.state.date.toLocalTimeString()}.</h2>
         </div>
      );
   }
}
```

<br>

- Note how we pass `props` to the base constructor:
  - 기본 생성자에 `props`를 전달하는 방법에 주의해라.

```react
constructor(props) {
   super(props);
   this. state = {date: new Date()};
}
```

<br>

- Class component should always call the base constructor with `props`.
  - 클래스 컴포넌트는 항상 기본 생성자를 `props`로 호출해야 한다.

<br>

- 3) Remove the `date` prop from the `<Clock />` element.
  - `<Clock />` element에서 `date` prop을 제거해라.

```react
ReactDOM.render(
	<Clock />,
   document.getElementById('root')
);
```

<br>

- We will later add the timer code back to the component itself.
  - 나중에 타이머 코드를 컴포넌트 자체에 다시 추가할 것이다.

<br>

- The result looks like this:
  - 결과는 다음과 같다.

```react
class Clock extends React.Component {
   constructor(props) {
      super(props);
      this.state = {date: new Date()};
   }
   
   render() {
      return (
      	<div>
         	<h1>Hello, world!</h1>
            <h2>It is {this.state.date.toLocaleTimeString()}.</h2>
         </div>
      );
   }
}

ReactDOM.render(
	<Clock />,
   document.getElementById('root')
);
```

[CodePen에서 시도](https://codepen.io/gaearon/pen/KgQpJd?editors=0010)

<br>

- Next, we'll make the `Clock` set up its own timer and update itself every second.
  - 다음에는, `Clock`을 자체 타이머로 설정하고 매초 업데이트할 것이다.

------

<br>

### Adding Lifecycle Methods to a Class

###### 클래스에 lifecycle 메소드 추가

<br>

- In applications with many components, it's very important to free up resources taken by the components when they are destroyed.
  - 많은 컴포넌트가 있는 애플리케이션에서는, 컴포넌트가 파괴될 때 사용된 리소스를 확보하는 것이 매우 중요하다.

<br>

- We want to [set up a timer](https://developer.mozilla.org/en-US/docs/Web/API/WindowOrWorkerGlobalScope/setInterval) whenever the `Clock` is rendered to the DOM for the first time.
  - `Clock`이 DOM에 처음 렌더링 될 때마다 [타이머를 설정](https://developer.mozilla.org/en-US/docs/Web/API/WindowOrWorkerGlobalScope/setInterval)하려고 한다.
- This is called "mounting" in React.
  - 이것을 React에서 "마운팅"이라고 한다.

<br>

- We also want to [clear that timer](https://developer.mozilla.org/en-US/docs/Web/API/WindowOrWorkerGlobalScope/clearInterval) whenever the DOM produced by the `Clock` is removed.
  - `Clock`에서 생성된 DOM이 제거될 때마다 [타이머를 초기화](https://developer.mozilla.org/en-US/docs/Web/API/WindowOrWorkerGlobalScope/clearInterval)하려고 한다.
- This is called "unmounting" in React.
  - 이것을 React에서 "언마운팅"이라고 한다.

<br>

- We can declare special methods on the component class to run some code when a component mounts and unmounts:
  - 컴포넌트가 마운트 및 언마운트 될 때, 특정 코드를 실행하기 위해 컴포넌트 클래스에 특수 메소드를 선언할 수 있다.

```react
class Clock extends React.Component {
   constructor(props) {
      super(props);
      this.state = {date: new Date()};
   }
   
   componentDidMount() {
      
   }
   
   componentWillUnmount() {
      
   }
   
   render() {
      return (
      	<div>
         	<h1>Hello, world!</h1>
            <h2>It is {this.state.date.toLocaleTimeString()}.</h2>
         </div>
      );
   }
}
```

<br>

- These methods are called "lifecycle hooks".
  - 이러한 메소드를 "lifecycle hooks"라고 한다.

<br>

- The `componentDidMount()` hook runs after the component output has been rendered to the DOM.
  - 컴포넌트 출력이 DOM에 렌더링 된 후에 `componentDidMount()` hook이 실행된다.
- This is a good place to set up a timer:
  - 이것은 타이머를 설정하기 좋은 장소다.

```react
componentDidMount() {
   this.timerID = setInterval(
   	() => this.tick(),
      1000
   );
}
```

<br>

- Note how we save the timer ID right on `this`.
  - `this`에 타이머 ID를 어떻게 저장하는지 주의해라.

<br>

- While `this.props` is set up by React itself and `this.state` has a special meaning, you are free to add additional fields to the class manually if you need to store something that doesn't participate in the data flow (like a timer ID).
  - `this.props`가 React 자체에 의해 설정되고 `this.state`가 특별한 의미를 가지지만, 데이터 흐름에 참여하지 않는 것을 저장해야 하는 경우 클래스에 수동으로 자유롭게 추가할 수 있다.

<br>

- We will tear down the timer in the `componentWillUnmount()` lifecycle hook:
  - `componentWillUnmount()` lifecycle hook에서 타이머를 종료한다.

```react
componentWillUnmount() {
   clearInterval(this.timerID);
}
```

<br>

- Finally, we will implement a method called `tick()` that the `Clock` component will run every second.
  - 마지막으로, `Clock` 컴포넌트가 매초 실행되는 `tick()`이라는 메소드를 구현할 것이다.

<br>

- It will use `this.setState()` to schedule updates to the component local state:
  - `this.setState()`를 사용해서 컴포넌트 로컬 state에 대한 업데이트를 예약한다.

```react
class Clock extends React.Component {
   constructor(props) {
      super(props);
      this.state = {date: new Date()};
   }
   
   componentDidMount() {
      this.timerID = setInterval(
      	() => this.tick(),
         1000
      );
   }
   
   componentWillMount() {
      clearInterval(this.timerID);
   }
   
   tick() {
      this.setState({
         date: new Date()
      });
   }
   
   render() {
      return (
      	<div>
         	<h1>Hello, world!</h1>
            <h2>It is {this.state.date.toLocaleTimeString()}.</h2>
         </div>
      );
   }
}

ReactDOM.render(
	<Clock />,
   document.getElementById('root')
);
```

[CodePen에서 시도](https://codepen.io/gaearon/pen/amqdNA?editors=0010)

<br>

- Now the clock ticks every second.
  - 이제 시계는 매초 째깍거린다.

<br>

- Let's quickly recap what's going on and the order in which the methods are called:
  - 무슨 일이 일어나는지와 메소드가 호출되는 순서를 빠르게 요약해보자.

<br>

1. When `<Clock />` is passed to `ReactDOM.render()`, React calls the constructor of the `Clock` component. Since `Clock` needs to display the current time, it initializes `this.state` with an object including the current time. We will later update this state.
   -  `<Clock />`이 `ReactDOM.render()`에 전달되면, React는 `Clock` 컴포넌트의 생성자를 호출한다.
   - `Clock`은 현재 시간을 표시해야 하므로, `this.state`를 현재 시간을 포함하는 객체로 초기화한다.
   - 나중에 이 state를 업데이트 할 것이다.
2. React then calls the `Clock` component's `render()` method. This is how React learns what should be displayed on the screen. React then updates the DOM to match the `Clock`'s render output.
   - 그런 다음 React는 `Clock` 컴포넌트의 `render()` 메소드를 호출한다.
   - 이것은 React가 무엇을 화면에 표시해야 하는지를 배우는 방법이다.
   - 그런 다음 React는 `Clock`의 렌더링 출력과 일치하도록 DOM을 업데이트 한다.
3. When the `Clock` output is inserted in the DOM, React calls the `componentDidMount()` lifecycle hook. Inside it, the `Clock` component asks the browser to set up a timer to call the component's `tick()` method once a second.
   - `Clock` 출력이 DOM에 삽입되면, React는 `componentDidMount()` lifecycle hook를 호출한다.
   - 그 안에서, `Clock` 컴포넌트가 브라우저에 컴포넌트의 `tick()` 메소드를 한 번씩 호출하는 타이머를 설정하도록 요청한다.
4. Every second the browser calls the `tick()` method. Inside it, the `Clock` component schedules a UI update by calling `setState()` with an object containing the current time. Thanks to the `setState()` call, React knows the state has changed, and calls the `render()` method again to learn what should be on the screen. This time, `this.state.date` in the `render()` method will be different, and so the render output will include the updated time. React updates the DOM accordingly.
   - 브라우저는 매초 `tick()` 메소드를 호출한다.
   - 그 안에서, `Clock` 컴포넌트는 현재 시간을 포함하는 객체로 `setState()`를 호출해서 UI 업데이트를 예약한다.
   - `setState()` 호출 덕분에 React는 state가 변경되는 것을 알고, `render()` 메소드를 다시 호출해서 화면에 무엇이 있어야 하는지를 확인한다.
   - 이번에는, `render()` 메소드의 `this.state.date`가 달라지므로, 렌더링 출력에 업데이트 된 시간이 포함된다.
   - React는 그에 따라 DOM을 업데이트 한다.
5. If the `Clock` component is ever removed from the DOM, React calls the `componentWillUnmount()` lifecycle hook so the timer is stopped.
   - `Clock` 컴포넌트가 DOM에서 제거된 경우, React는 `componentWillUnmount()` lifecycle hook을 호출해서 타이머가 중지된다.

------

<br>

### Using State Correctly

###### state의 올바른 사용

<br>

- There are three things you should know about `setState()`.
  - `setState()`에 대해 알아야 할 세 가지가 있다.

<br>

#### 01. Do Not Modify State Directly

###### state를 직접 수정하지 마라

<br>

- For example, this will not re-render a component:
  - 예를 들어, 다음과 같이 하면 컴포넌트가 다시 렌더링 되지 않는다.

```react
// Wrong

this.state.comment = 'Hello';
```

<br>

- Instead, use `setState()`:
  - 대신에, `setState()`를 사용해라.

```react
// Correct

this.setState({comment: 'Hello'});
```

<br>

- The only place where you can assign `this.state` is the constructor.
  - `this.state`를 할당할 수 있는 유일한 곳은 생성자이다.

<br>

#### 02. State Updates May Be Asynchronous

###### state 업데이트는 비동기가 될 수도 있다

<br>

- React may batch multiple `setState()` calls into a single update for performance.
  - React는 성능 향상을 위한 단일 업데이트로 여러 `setState()` 호출을 배치할 수 있다.

<br>

- Because `this.props` and `this.state` may be updated asynchronously, you should not rely on their values for calculating the next state.
  - `this.props`와 `this.state`는 비동기적으로 업데이트될 수 있으므로, 다음 state를 계산할 때 해당 값을 신뢰해서는 안 된다.

<br>

- For example, this code may fail to update the counter:
  - 예를 들어, 이 코드는 카운터 업데이트를 실패할 수도 있다.

```react
// Wrong

this.setState({
   counter: this.state.counter + this.props.increment,
});
```

<br>

- To fix it, use a second form of `setState()` that accepts a function rather than an object.
  - 이것을 해결하려면, 객체 보다는 함수를 받아들이는 두 번째 형식의 `setState()`를 사용해라.
- That function will receive the previous state as the first argument, and the props at the time the update is applied as the second argument:
  - 이 함수는 첫 번째 인수로 이전의 state를 받고, 업데이트가 두 번째 인수로 적용될 때의 props를 받는다.

```react
// Correct

this.setState((prevState, props) => ({
   counter: prevState.counter + props.increment
}));
```

<br>

- We used an [arrow function](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/Arrow_functions) above, but it also works with regular functions:
  - 위에 [화살표 함수](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/Arrow_functions)를 사용했는데, 일반 함수에서도 작동한다.

```react
// Correct

this.setState(function(prevState, props) {
   return (
   	counter: prevState.counter + props.increment
   );
});
```

<br>

#### 03. State Updates are Merged

###### state 업데이트는 병합된다

<br>

- When you call `setState()`, React merges the object you provide into the current state.
  - `setState()`를 호출하면, React가 제공한 객체를 현재 state로 병합한다.

<br>

- For example, your state may contain several independent variables:
  - 예를 들어, state는 여러 독립 변수가 포함될 수 있다.

```react
constructor(props) {
   super(props);
   this.state = {
      posts: [],
      comments: []
   };
}
```

<br>

- Then you can update them independently with separate `setState()` calls:
  - 그런 다음 각 `setState()` 호출을 사용해서 개별적으로 업데이트 할 수 있다.

```react
componentDidMount() {
   fetchPosts().then(response => {
      this.setState({
         posts: response.posts
      });
   });
   
   fetchComments().then(response => {
      this.setState({
         comments: response.comments
      });
   });
}
```

<br>

- The merging is shallow, so `this.setState({comments})` leaves `this.state.posts` intact, but completely replaces `this.state.comments`.
  - 병합이 얕아서, `this.setState({comments})`는 `this.state.posts`를 그대로 내버려 두지만, `this.state.comments`를 완전히 대체한다.

------

<br>

### The Data Flows Down

###### 아래로 흐르는 데이터 흐름

<br>

- Neither parent nor child components can know if a certain component is stateful or stateless, and they shouldn't care whether it is defined as a function or a class.
  - 부모 컴포넌트나 자식 컴포넌트는 특정 컴포넌트가 stateful 또는 stateless 인지 알 수 없고, 함수나 클래스가 정의되었는지를 신경 써서는 안 된다.

<br>

- This is why state is often called local or encapsulated.
  - 이것이 state가 종종 로컬 또는 캡슐화된 이유이다.
- It is not accessible to any component other than the one that owns and sets it.
  - 소유하고 설정하는 컴포넌트 외에는 액세스할 수 없다.

<br>

- A component may choose to pass its state down as props to its child components:
  - 컴포넌트는 state를 자식 컴포넌트로 전달할 수 있다.

```react
<h2>It is {this.state.date.toLocalTimeString}.</h2>
```

<br>

- This also works for user-defined components:
  - 이는 사용자 정의 컴포넌트에도 적용된다.

```react
<FormattedDate date={this.state.date} />
```

<br>

- The `FormattedDate` component would receive the `date` in its props and wouldn't know whether it came from the `Clock`'s state, from the `Clock`'s props, or was typed by hand:
  - `FormattedDate` 컴포넌트는 props에서  `date`를 수신하고, `Clock`의 state, `Clock`의 props, 손으로 입력했는지 여부를 알 수 없다.

```react
function FormattedDate(props) {
   return <h2>It is {props.date.toLocalTimeString()}.</h2>;
}
```

[CodePen에서 시도](https://codepen.io/gaearon/pen/zKRqNB?editors=0010)

<br>

- This is commonly called a "top-down" or "unidirectional" data flow.
  - 이를 일반적으로 "하향식" 또는 "단방향" 데이터 흐름이라고 한다.
- Any state is always owned by some specific component, and any data or UI derived from that state can only affect components "below" them in the tree.
  - 모든 state는 항상 특정 컴포넌트가 소유하고, 모든 데이터 또는 해당 state에서 파생된 UI는 컴포넌트 트리의 "아래"로만 영향을 미친다.

<br>

- If you imagine a component tree as a waterfall of props, each component's state is like an additional water source that joins it at an arbitrary point but also flows down.
  - props의 폭포로 컴포넌트 트리를 상상해보면, 각 컴포넌트의 state는 임의의 지점에서 합류하는 추가 수원과 비슷하다.
  - 하지만 또한 아래로 흐른다.

<br>

- To show that all components are truly isolated, we can create an `App` component that renders three `<Clock>`s:
  - 모든 컴포넌트가 실제로 분리되어 있음을 보여주기 위해, 세 개의 `<Clock>`을 렌더링 하는  `App` 컴포넌트를 생성할 수 있다.

```react
function App() {
   return (
   	<div>
      	<Clock />
         <Clock />
         <Clock />
      </div>
   );
}

ReactDOM.render(
	<App />,
   document.getElementById('root')
);
```

[CodePen에서 시도](https://codepen.io/gaearon/pen/vXdGmd?editors=0010)

<br>

- Each `Clock` sets up its own timer and updates independently.
  - 각 `Clock`은 자체 타미어를 설정하고 독립적으로 업데이트 된다.

<br>

- In React apps, whether a component is stateful or stateless is considered an implementation detail of the component that may change over time.
  - React 앱에서, 컴포넌트가 stateful 또는 stateless 인지는 시간이 지남에 따라 변경될 수 있는 컴포넌트의 구현 세부 사항으로 간주된다.
- You can use stateless components inside stateful components, and vice versa.
  - stateful 컴포넌트 안에서 stateless 컴포넌트를 사용할 수 있다.
  - 그 반대의 경우도 가능하다.

<br>