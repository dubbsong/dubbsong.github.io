---
layout: post
title: "공식 리액트 문서 번역 - 12. Thinking In React (Main Concepts)"
categories: react
tags: react
---

[공식 리액트 문서 링크](https://reactjs.org/docs/thinking-in-react.html)

<br>

## Thinking in React

- ###### React is, in our opinion, the premier way to build big, fast Web apps with JavaScript.

  - ###### React는, JavaScript로 크고 빠른 웹 애플리케이션을 만드는 최고의 방법이라고 생각한다.

- ###### It has scaled very well for us at Facebook and Instagram.

  - ###### React는 Facebook과 Instagram에서 우리를 위해 아주 잘 확장되었다.

<br>

- One of the many great parts of React is how it makes you think about apps as you build them.
  - React의 많은 부분 중 하나는 애플리케이션을 제작할 때 애플리케이션을 어떻게 생각하게 만드는지이다.
- In this document, we'll walk you through the thought process of building a searchable product data table using React.
  - 이 문서에서는, React를 사용해서 검색 가능한 제품 데이터 테이블을 작성하는 방법을 설명한다.

------

<br>

### Start With A Mock

###### 모의 시작

<br>

- Imagine that we already have a JSON API and a mock from our designer.
  - 이미 JSON API와 디자이너가 만든 모의(모형)가 있다고 상상해보자.
- The mock looks like this:
  - 모의(모형)는 다음과 같다.

![React img](/assets/img/react-official-main concepts-12-01.png)

<br>

- Our JSON API returns some data that looks like this:
  - JSON API는 다음과 같은 데이터를 반환한다.

```json
[
   {category: "Sporting Goods", price: "$49.99", stocked: true, name: "Football"},
   {category: "Sporting Goods", price: "$9.99", stocked: true, name: "Baseball"},
   {category: "Sporting Goods", price: "$29.99", stocked: false, name: "Basketball"},
   {category: "Electronics", price: "$99.99", stocked: true, name: "iPod Touch"},
   {category: "Electronics", price: "$399.99", stocked: false, name: "iPhone 5"},
   {category: "Electronics", price: "$199.99", stocked: true, name: "Nexus 7"},
]
```

------

<br>

#### Step 1: Break The UI Into A Component Hierarchy

###### UI를 컴포넌트 계층 구조로 분해

<br>

- The first thing you'll want to do is to draw boxes around every component (and subcomponent) in the mock and give them all names.
  - 가장 먼저 해야 할 일은 모의의 모든 컴포넌트(와 하위 컴포넌트) 주위에 상자를 그리고 모든 이름을 지정하는 것이다.
- If you're working with a designer, they may have already done this, so go talk to them!
  - 디자이너와 함께 작업하는 경우, 이미 작업을 마친 상태일 수도 있다.
- Their Photoshop layer names may end up being the names of your React components!
  - 포토샵 레이어 이름이, React 컴포넌트 이름이 될 수 있다.

<br>

- But how do you know what should be its own components?
  - 하지만 자체 컴포넌트가 무엇인지 어떻게 알 수 있을까?
- Just use the same techniques for deciding if you should create a new function or object.
  - 새로운 함수나 객체를 생성해야 하는지를 결정하는 데에 같은 기술을 사용해라.
- One such technique is the [single responsibility principle](https://en.wikipedia.org/wiki/Single_responsibility_principle), that is, a component should ideally only do one thing.
  - 그러한 기술 중 하나는 [단일 책임 원칙](https://en.wikipedia.org/wiki/Single_responsibility_principle)이다.
  - 즉, 컴포넌트는 이상적으로 하나만 수행해야 한다.
- If it ends up growing, it should be decomposed into smaller subcomponents.
  - 그것이 끝나면, 더 작은 하위 컴포넌트로 분해되어야 한다.

<br>

- Since you're often displaying a JSON data model to a user, you'll find that if your model was built correctly, your UI (and therefore your component structure) will map nicely.
  - 사용자에게 JSON 데이터 모델을 자주 표시하므로, 모델을 올바르게 작성하면 UI(따라서 컴포넌트 구조)가 잘 매핑된다.
- That's because UI and data models tend to adhere to the same *information architecture*, which means the work of separating your UI into components is often trivial.
  - 이는 UI와 데이터 모델이 동일한 *정보 아키텍처*를 따르는 경향이 있기 때문이다.
  - 즉, UI를 컴포넌트로 분리하는 작업은 종종 사소한 것이다.
- Just break it up into components that represent exactly one piece of your data model.
  - 정확히 하나의 데이터 모델을 나타내는 컴포넌트로 분해해라.

![React img](/assets/img/react-official-main concepts-12-02.png)

<br>

- You'll see here that we have five components in our simple app.
  - 간단한 애플리케이션에는 다섯 가지 컴포넌트가 있다는 것을 알 수 있다.
- We've italicized the data each component represents.
  - 각 컴포넌트가 나타내는 데이터를 이탤릭체로 표시했다.

<br>

1. **FilterableProductTable (orange):** contains the entirety of the example
   - **FilterableProductTable (orange):** 예제 전체 포함
2. **SearchBar (blue):** receives all *user input*
   - **SearchBar (blue):** 모든 *사용자 입력* 수신
3. **ProductTable (green):** displays and filters the *data collection* based on *user input*
   - **ProductTable (green):** *사용자 입력*을 기반으로 *데이터 수집*을 표시하고 필터링한다.
4. **ProductCategoryRow (turquoise):** displays a heading for each *category*
   - **ProductCategoryRow (turquoise):** 각 *범주*의 제목을 표시
5. **ProductRow (red):** displays a row for each *product*
   - **ProductRow (red):** 각 *제품*에 대한 행을 표시

<br>

- If you look at `ProductTable`, you'll see that the table header (containing the "Name" and "Price" labels) isn't its own component.
  - `ProductTable`을 보면, table header("Name"과 "Price" 라벨 포함)가 자체 컴포넌트가 아니라는 것을 알 수 있다.
- This is a matter of preference, and there's an argument to be made either way.
  - 이것은 선호의 문제이며, 어느 쪽이든 논쟁이 있다.
- For this example, we left it as part of `ProductTable` because it is part of rendering the *data collection* which is `ProductTable`'s responsibility.
  - 이 예제에서는, `ProductTable`의 일부로 남겨두었다.
  - `ProductTable`의 책임인 *data collection* 렌더링의 일부이기 때문이다.
- However, if this header grows to be complex (i.e. if we were to add affordances for sorting), it would certainly make sense to make this its own `ProductTableHeader` component.
  - 하지만, 이 header가 복잡해지면(즉, 정렬을 위한 affordance를 추가한다면), 자체의 `ProductTableHeader` 컴포넌트를 만드는 것이 합리적일 것이다. 

<br>

- Now that we've identified the components in our mock, let's arrange them into a hierarchy.
  - 이제 모의 컴포넌트를 확인했으므로, 계층 구조로 정렬해보자.
- This is easy.
  - 이것은 쉽다.
- Components that appear within another component in the mock should appear as a child in the hierarchy:
  - mock의 다른 컴포넌트에 나타나는 컴포넌트는 계층 구조의 자식으로 나타난다.

<br>

> - `FilterableProductTable`
>   - `SearchBar`
>   - `ProductTable`
>     - `ProductCategortRow`
>     - `ProductRow`

------

<br>

#### Step 2: Build A Static Version in React

###### React로 static 버전 구축

<br>

- See the Pen [Thinking In React: Step 2](https://codepen.io/gaearon/pen/BwWzwm) on CodePen.
  - CodePen의 [Thinking In React: Step 2](https://codepen.io/gaearon/pen/BwWzwm)를 참조해라.

<br>

- Now that you have your component hierarchy, it's time to implement your app.
  - 이제 컴포넌트 계층 구조가 생겼으므로, 애플리케이션을 구현할 시간이다.
- The easiest way is to build a version that takes your data model and renders the UI but has no interactivity.
  - 가장 쉬운 방법은 데이터 모델을 가져와서 UI를 렌더링 하는 것이다.
  - 하지만 대화형이 아닌 버전을 만드는 것이다.
- It's best to decouple these processes because building a static version requires a lot of typing and no thinking, and adding interactivity requires a lot of thinking and not a lot of typing.
  - static 버전을 만드는 데에는 많은 타이핑과 생각이 필요하기 때문에, 프로세스를 분리하는 것이 가장 좋다.
- We'll see why.
  - 이유를 알게 될 것이다.

<br>

- To build a static version of your app that renders your data model, you'll want to build components that reuse other components and pass data using *props*.
  - 데이터 모델을 렌더링 하는 애플리케이션의 static 버전을 제작하려면, 다른 컴포넌트를 재사용하고, *props*를 사용해서 데이터를 전달하는 컴포넌트를 작성해야 한다.
- *props* are a way of passing data from parent to child.
  - *props*는 부모로부터 자식에게 데이터를 전달하는 방법이다.
- If you're familiar with the concept of *state*, **don't use state at all** to build this static version.
  - *state* 개념에 익숙하다면, static 버전을 빌드하기 위해 state를 전혀 사용하지 마라.
- State is reserved only for interactivity, that is, data that changes over time.
  - state는 대화형에 대해서만 예약된다.
  - 즉, 시간이 지남에 따라 변경되는 데이터에 대해서만 예약된다.
- Since this is a static version of the app, you don't need it.
  - 이것은 애플리케이션의 static 버전이므로, 필요하지 않다.

<br>

- You can build top-down or bottom-up.
  - 하향식 또는 상향식을 만들 수 있다.
- That is, you can either start with building the components higher up in the hierarchy (i.e. starting with `FilterableProductTable`) or with the ones lower in it (`ProductRow`).
  - 즉, 계층 구조에서 상위로 컴포넌트를 빌드하거나(즉, `FilterableProductTable`로 시작) 하위로 빌드하는 것에서부터 시작할 수 있다(`ProductRow`).
- In simpler examples, it's usually easier to go top-down, and on larger projects, it's easier to go bottom-up and write tests as you build.
  - 간단한 예제에서는 일반적으로 하향식으로 진행하는 것이 더 쉽고, 큰 프로젝트에서는 상향식으로 테스트를 작성하는 것이 더 쉽다.

<br>

- At the end of this step, you'll have a library of reusable components that render your data model.
  - 이 단계가 끝나면, 데이터 모델을 렌더링 하는 재사용 가능한 컴포넌트 라이브러리를 가지게 된다.
- The components will only have `render()` methods since this is a static version of your app.
  - 이 컴포넌트는 애플리케이션의 static 버전이므로, `render()` 메소드만 가질 것이다.
- The component at the top of the hierarchy (`FilterableProductTable`) will take your data model as a prop.
  - 계층 구조의 맨 위에 있는 컴포넌트(`FilterableProductTable`)는 데이터 모델을 prop으로 사용한다.
- If you make a change to your underlying data model and call `ReactDOM.render()` again, the UI will be updated.
  - 기본 데이터 모델을 변경하고, `ReactDOM.render()`를 다시 호출하면, UI가 업데이트된다.
- It's easy to see how your UI is updated and where to make changes since there's nothing complicated going on.
  - 복잡한 것이 없으므로, 어떻게 UI가 업데이트되고 어디서 변경해야 하는지를 쉽게 알 수 있다.
- React's **one-way data flow** (also called *one-way binding*) keeps everything modular and fast.
  - React의 **단방향 데이터 흐름**(*단방향 바인딩*이라고도 한다)은 모든 것을 모듈화해서 빠르게 유지한다.

<br>

- Simply refer to the [React docs](https://reactjs.org/docs/getting-started.html) if you need help executing this step.
  - 이 단계를 실행하는 데 도움이 필요하면, [React docs](https://reactjs.org/docs/getting-started.html)를 참조하면 된다.

<br>

#### A Brief Interlude: Props vs State

###### 간략한 에피소드: Props vs State

<br>

- There are two types of "model" data in React: props and state.
  - React에는 두 가지 유형의 "model" 데이터가 있다: prop와 state.
- It's important to understand the distinction between the two; skim [the official React docs](https://reactjs.org/docs/state-and-lifecycle.html) if you aren't sure what the difference is.
  - 이 둘의 차이점을 이해하는 것은 중요하다.
  - 그 차이가 무엇인지 모르는 경우, [the official React docs](https://reactjs.org/docs/state-and-lifecycle.html)를 훑어봐라.

------

<br>

#### Step 3: Identify The Minimal (but complete) Representation Of UI State

###### UI state의 최소(하지만 완전한) 표현 확인

<br>

- To make your UI interactive, you need to be able to trigger changes to your underlying data model.
  - 대화형 UI를 만들려면, 기본 데이터 모델에 대한 변경을 trigger 할 수 있어야 한다.
- React makes this easy with **state**.
  - React는 이것을 **state**로 쉽게 만든다.

<br>

- To build your app correctly, you first need to think of the minimal set of mutable state that your app needs.
  - 애플리케이션을 올바르게 빌드하려면, 먼저 애플리케이션에 필요한 최소한의 변경 가능한 state를 고려해야 한다.
- The key here is [DRY: *Don't Repeat Yourself*](https://en.wikipedia.org/wiki/Don%27t_repeat_yourself).
  - 여기서의 핵심은 [DRY: 자신을 반복하지 말라](https://en.wikipedia.org/wiki/Don%27t_repeat_yourself)는 것이다.
- Figure out the absolute minimal representation of the state your application needs and compute everything else you need on-demand.
  - 애플리케이션이 필요로 하는 state를 절대적으로 최소한으로 표현하고, 언제든지 필요한 모든 것을 계산해라.
- For example, if you're building a TODO list, just keep an array of the TODO items around; don't keep a separate state variable for the count.
  - 예를 들어, TODO 리스트를 작성하는 중이라면, TODO 항목의 배열을 유지해라.
  - 카운트를 위한 별도의 state 변수는 유지하지 않는다.
- Instead, when you want to render the TODO count, simply take the length of the TODO items array.
  - 대신, TODO 카운트를 렌더링 하려면, TODO 항목 배열의 길이를 취하면 된다.

<br>

- Think of all of the pieces of data in our example application.
  - 예제 애플리케이션에서 데이터 조각을 생각해보자.

<br>

1. The original list of products
   - 제품의 원래 목록
2. The search text the user has enterd
   - 사용자가 입력한 검색 텍스트
3. The value of the checkbox
   - 체크박스의 값
4. The filtered list of products
   - 필터링 된 제품 목록

<br>

- Let's go through each one and figure out which one is state.
  - 각각을 살펴보고 어느 것이 state인지 알아보자.
- Simply ask three questions about each piece of data:
  - 각 데이터 조각에 대해 세 가지 질문을 해보자.

<br>

1. Is it passed in from a parent via props? If so, it probably isn't state.
   - 그것은 props를 통해 부모로부터 전달되는가? 그렇다면, 그것은 아마도 state가 아니다.
2. Does it remain unchanged over time? If so, it probably isn't state.
   - 시간이 지나도 변함이 없는가? 그렇다면, 그것은 아마도 state가 아니다.
3. Can you compute it based on any other state or props in your component? If so, it isn't state.
   - 컴포넌트의 다른 state나 props를 기반으로 계산할 수 있는가? 그렇다면, 그것은 state가 아니다.

<br>

- The original list of products is passed in as props, so that's not state.
  - 제품의 원래 목록은 props로 전달되므로, state가 아니다.
- The search text and the checkbox seem to be state since they change over time and can't be computed from anything.
  - 검색 텍스트와 체크박스는 시간이 지남에 따라 변경되고, 아무것도 계산할 수 없으므로, state인 것 같다.
- And finally, the filtered list of products isn't state because it can be computed by combining the original list of products with the search text and value of the checkbox.
  - 마지막으로, 제품의 필터링 된 목록은 state가 아니다.
  - 제품의 원래 목록을 검색 텍스트 및 체크박스의 값과 결합해서 계산할 수 있기 때문이다.

<br>

- So finally, our state is:
  - 그래서 마침내 state는 다음과 같아.

<br>

1. The search text the user has entered
   - 사용자가 입력한 검색 텍스트
2. The value of the checkbox
   - 체크박스의 값

------

<br>

#### Step 4: Identify Where Your State Should Live

###### state가 살 수 있는 곳 확인

<br>

- See the Pen [Thinking In React: Step 4](https://codepen.io/gaearon/pen/qPrNQZ) on CodePen.
  - CodePen의 [Thinking In React: Step 4](https://codepen.io/gaearon/pen/qPrNQZ)를 참조해라.

<br>

- Ok, so we've identified what the minimal set of app state is.
  - 우리는 애플리케이션 state의 최소한이 무엇인지 확인했다.
- Next, we need to identify which component mutates, or *owns*, this state.
  - 다음으로, 변경 가능하거나 소유하는 컴포넌트를 확인해야 한다.

<br>

- Remember: React is all about one-way data flow down the component hierarchy.
  - 기억해라.
  - React는 컴포넌트 계층 구조에서 단방향 데이터 흐름에 관한 것이다.
- It may not be immediately clear which component should own what state.
  - 어떤 컴포넌트가 어떤 state를 소유하는지 명확하지 않을 수도 있다.
- **This is often the most challenging part for newcomers to understand**, so follow these steps to figure it out:
  - **이것은 종종 신입이 이해하기 어려운 부분이기 때문에**, 다음 단계를 수행해서 파악해라.

<br>

- For each piece of state in your application:
  - 애플리케이션에 있는 각 state마다:

<br>

1. Identify every component that renders something based on that state.
   - 해당 state를 기반으로 무언가를 렌더링 하는 모든 컴포넌트를 확인한다.
2. Find a common owner component (a single component above all the components that need the state in the hierarchy).
   - 공통 owner 컴포넌트를 찾아라.
   - (계층 구조에서 state가 필요한 모든 컴포넌트 위의 단일 컴포넌트)
3. Either the common owner or another component higher up in the hierarchy should own the state.
   - 공통 owner 또는 계층 구조에서 상위에 있는 다른 컴포넌트가 state를 소유해야 한다.
4. If you can't find a component where it makes sense to own the state, create a new component simply for holding the state and add it somewhere in the hierarchy above the common owner component.
   - state를 소유하고 있는 컴포넌트를 찾을 수 없는 경우, state를 보유하기 위한 새 컴포넌트를 만들고, 공통 owner 컴포넌트 위의 계층 구조에 추가해라.

<br>

- Let's run through this strategy for our application:
  - 애플리케이션에 대해서 이 전략을 실행해보자.

<br>

1. `ProductTable` needs to filter the product list based on state and `SearchBar` needs to display the search text and checked state.
   - `ProductTable`은 state에 기반해서 제품 목록을 필터링해야 하고, `SearchBar`는 검색 텍스트 및 체크박스 state를 표시해야 한다.
2. The common owner component is `FilterableProductTable`.
   - 공통 owner 컴포넌트는 `FilterableProductTable`이다.
3. It conceptually makes sense for the filter text and checked value to live in `FilterableProductTable`.
   - `FilterableProductTable`에 필터 텍스트와 체크된 값이 저장되는 것이 개념적이다.
   - 개념상 `FilterableProductTable`에 필터 텍스트와 체크된 값이 저장되어야 의미가 있다.

<br>

- Cool, so we've decided that our state lives in `FilterableProductTable`.
  - state를 `FilterableProductTable`에 저장하기로 결정했다.
- First, add an instance property `this.state = {filterText: '', inStockOnly: false}` to `FilterableProductTable`'s `constructor` to reflect the initial state of your application.
  - 먼저, 인스턴스 속성인 `this.state = {filterText: '', inStockOnly: false}`를 `FilterableProductTable`의 `constructor`에 추가해서 애플리케이션의 state를 반영한다.
- Then, pass `filterText` and `inStockOnly` to `ProductTable` and `SearchBar` as a prop.
  - 그런 다음, `filterText`와 `inStockOnly`를 `ProductTable`과 `SearchBar`에 prop으로 전달한다.
- Finally, use these props to filter the rows in `ProductTable` and set the values of the form fields in `SearchBar`.
  - 마지막으로, 이러한 props를 사용해서 `ProductTable`의 행을 필터링하고, `SearchBar`의 form 필드 값을 설정해라.

<br>

- You can start seeing how your application will behave: set `filterText` to `"ball"` and refresh your app.
  - 애플리케이션이 어떻게 동작하는지 볼 수 있다.
  - `filterText`를 `"ball"`로 설정하고 새로고침해라.
- You'll see that the data table is updated correctly.
  - 데이터 테이블이 올바르게 업데이트된 것을 볼 수 있다.

------

<br>

#### Step 5: Add Inverse Data Flow

###### 역 데이터 흐름 추가

<br>

- See the Pen [Thinking In React: Step 5](https://codepen.io/gaearon/pen/LzWZvb) on CodePen.
  - CodePen의 [Thinking In React: Step 5](https://codepen.io/gaearon/pen/LzWZvb)를 참조해라.

<br>

- So far, we've built an app that renders correctly as a function of props and state flowing down the hierarchy.
  - 지금까지, 계층 구조 아래로 흐르는 props와 state의 함수로 올바르게 렌더링 하는 애플리케이션을 만들었다.
- Now it's time to support data flowing the other way: the form components deep in the hierarchy need to update the state in `FilterableProductTable`.
  - 이제 다른 방향으로 흐르는 데이터를 지원해야 한다.
  - 계층 구조의 깊숙한 form 컴포넌트는 `FilterableProductTable`에서 state를 업데이트해야 한다.

<br>

- React makes this data flow explicit to make it easy to understand how your program works, but it does require a little more typing than traditional two-way data binding.
  - React를 사용하면 데이터 흐름을 명시적으로 처리해서 프로그램 작동 방식을 쉽게 이해할 수 있지만, 기존의 양방향 데이터 바인딩보다 약간 더 많은 타이핑이 필요하다.

<br>

- If you try to type or check the box in the current version of the example, you'll see that React ignores your input.
  - 예제의 현재 버전에서 박스에 타이핑하거나 체크하면, React가 입력을 무시하는 것을 볼 수 있다.
- This is intentional, as we've set the `value` prop of the `input` to always be equal to the `state` passed in from `FilterableProductTable`.
  - 이는 의도적인 것이다.
  - `input`의 `value` prop을 항상 `FilterableProductTable`에서 전달된 `state`와 동일하게 설정했기 때문이다.

<br>

- Let's think about what we want to happen.
  - 우리가 원하는 것을 생각해보자.
- We want to make sure that whenever the user changes the form, we update the state to reflect the user input.
  - 사용자가 form을 변경할 때마다 사용자 입력을 반영하도록 state를 업데이트해야 한다.
- Since components should only update their own state, `FilterableProductTable` will pass callbacks to `SearchBar` that will fire whenever the state should be updated.
  - 컴포넌트는 자체 state만 업데이트해야 하므로, `FilterableProductTable`은 state를 업데이트해야 할 때마다 실행되는 `SearchBar`에 콜백을 전달한다.
- We can use the `onChange` event on the inputs to be notified of it.
  - 입력에 대해 `onChange` 이벤트를 사용해서 알림을 받을 수 있다.
- The callbacks passed by `FilterableProductTable` will call `setState()`, and the app will be updated.
  - `FilterableProductTable`에 의해 전달된 콜백은 `setState()`를 호출하고, 애플리케이션이 업데이트된다.

<br>

- Though this sounds complex, it's really just a few lines of code.
  - 이 작업은 복잡해 보이지만, 실제로는 몇 줄의 코드이다.
- And it's really explicit how your data is flowing throughout the app.
  - 애플리케이션 전체에서 데이터가 어떻게 흐르고 있는지는 매우 분명하다.

------

<br>

### And That's It

- Hopefully, this gives you an idea of how to think about building components and applications with React.
  - 다행히도, React를 사용해서 컴포넌트와 애플리케이션을 작성하는 방법을 생각해볼 수 있다.
- While it may be a little more typing than you're used to, remember that code is read far more than it's written, and it's extremely easy to read this modular, explicit code.
  - 이전보다 약간 더 타이핑 할 수 있지만, 코드가 작성된 것보다 훨씬 많이 읽혀지므로, 이 모듈화의 명시적 코드를 읽기가 매우 쉽다는 것을 기억해라.
- As you start to build large libraries of components, you'll appreciate this explicitness and modularity, and with code reuse, your lines of code will start to shrink. :)
  - 커다란 컴포넌트 라이브러리를 빌드하기 시작할 때, 명백함과 모듈성에 감사할 것이고, 코드의 재사용으로 코드가 줄어들기 시작할 것이다. :)

<br>