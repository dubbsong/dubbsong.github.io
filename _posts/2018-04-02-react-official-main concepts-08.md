---
layout: post
title: "리액트 공식 문서 번역 - 08. list와 key (Main Concepts)"
categories: react
tags: React
---

###### [React 공식 문서](https://reactjs.org/docs/lists-and-keys.html) 번역

<br>

# React: Lists and Keys

###### list와 key

<br>

- First, let's review how you transform lists in JavaScript.
  - 먼저, JavaScript에서 list를 변환하는 방법을 살펴보자.

<br>

- Given the code below, we use the [map()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/map) function to take an array of `numbers` and double their values.
  - 아래 코드에서는, [map()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/map) 함수를 사용해서 `numbers` 배열을 가져와 값을 두 배로 늘린다.
- We assign the new array returned by `map()` to the variable `doubled` and log it:
  - `map()`에 의해 반환된 새로운 배열을 `doubled` 변수에 할당하고 로그를 확인한다.

```js
const numbers = [1, 2, 3, 4, 5];
const doubled = numbers.map((number) => number * 2);

console.log(doubled);
```

<br>

- This code logs `[2, 4, 6, 8, 10]` to the console.
  - 이 코드는 `[2, 4, 6, 8, 10]`을 콘솔에 표시한다.

<br>

- In React, transforming array into lists of [elements](https://reactjs.org/docs/rendering-elements.html) is nearly identical.
  - React에서 배열을 [element](https://reactjs.org/docs/rendering-elements.html) list로 변환하는 것은 이와 거의 동일하다.

------

<br>

## Rendering Multiple Components

###### 여러 컴포넌트 렌더링 하기

<br>

- You can build collections of elements and [include them in JSX](https://reactjs.org/docs/introducing-jsx.html#embedding-expressions-in-jsx) using curly braces `{}`.
  - element 모음을 구축하고, 중괄호 `{}`를 사용해서 [이를 JSX에 포함](https://reactjs.org/docs/introducing-jsx.html#embedding-expressions-in-jsx)시킬 수 있다.

<br>

- Below, we loop through the `numbers` array using the JavaScript [map()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/map) function.
  - JavaScript [map()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/map) 함수를 사용해서 `numbers` 배열을 반복 실행한다.
- We return a `<li>` element for each item.
  - 각 항목에 대해 `<li>` element를 반환한다.
- Finally, we assign the resulting array of elements to `listItems`:
  - 마지막으로, element 배열의 결과를 `listItems`에 할당한다.

```js
const numbers = [1, 2, 3, 4, 5];
const listItems = numbers.map((number) =>
	<li>{number}</li>
);
```

<br>

- We include the entire `listItems` array inside a `<ul>` element, and [render it to the DOM](https://reactjs.org/docs/rendering-elements.html#rendering-an-element-into-the-dom):
  - 전체 `listItems` 배열을 `<ul>` element 안에 포함시키고, 이를 [DOM에 렌더링](https://reactjs.org/docs/rendering-elements.html#rendering-an-element-into-the-dom) 한다.

```react
const numbers = [1, 2, 3, 4, 5];
const listItems = numbers.map((numbers) =>
	<li>{numbers}</li>                           
);

ReactDOM.render(
	<ul>{listItems}</ul>,
   document.getElementById('root')
);
```

[코드 실행 확인 링크](https://codepen.io/gaearon/pen/GjPyQr?editors=0011)

<br>

- This code displays a bullet list of numbers between 1 and 5.
  - 이 코드는 글머리 기호가 있는 숫자 list를 1부터 5까지 표시한다.

------

<br>

## Basic List Component

###### 기본 list 컴포넌트

<br>

- Usually you would render lists inside a [component](https://reactjs.org/docs/components-and-props.html).
  - 일반적으로 컴포넌트 내에서 list를 렌더링 한다.

<br>

- We can refactor the previous example into a component that accepts an array of `numbers` and outputs an unordered list of elements.
  - 이전 예제를 `numbers` 배열을 허용하고, 정렬되지 않은 element list를 출력하는 컴포넌트로 리팩토링 할 수 있다.

```react
function NumberList(props) {
   const numbers = props.numbers;
   const listItems = numbers.map((number) =>
		<li>{number}</li>                           
	);
   return (
   	<ul>{listItems}</ul>
   );
}

const numbers = [1, 2, 3, 4, 5];

ReactDOM.render(
	<NumberList numbers={numbers} />,
   document.getElementById('root')
);
```

<br>

- When you run this code, you'll be given a warning that a key should be provided for list items.
  - 이 코드를 실행하면, list 항목에 key가 제공되어야 한다는 경고를 받게 된다.
- A "key" is a special string attribute you need to include when creating list of elements.
  - "key"는 list element를 생성할 때 포함해야 하는 특수 문자열 속성이다.
- We'll discuss why it's important in the next section.
  - 다음 섹션에서 key가 중요한 이유를 설명할 것이다.

<br>

- Let's assign a `key` to our list items inside `numbers.map()` and fix the missing key issue.
  - `numbers.map()` 내의 list 항목에 `key`를 할당하고, 누락된 주요 문제를 해결해보자.

```react
function NumberList(props) {
   const numbers = props.numbers;
   const listItems = numbers.map((number) =>
		<li key={number.toString()}>
			{number}
		</li>
	);
   return (
   	<ul>{listItems}</ul>
   );
}

const numbers = [1, 2, 3, 4, 5];

ReactDOM.render(
	<NumberList numbers={numbers} />,
   document.getElementById('root')
);
```

[코드 실행 확인 링크](https://codepen.io/gaearon/pen/jrXYRR?editors=0011)

------

<br>

## Keys

- Keys help React identify which items have changed, are added, or are removed.
  - React는 key를 통해 어떤 항목이 변경되었는지, 추가되었는지, 삭제되었는지 식별할 수 있다.
- Keys should be given to the elements inside the array to give the elements a stable identity:
  - element에 안정적인 id를 제공하려면, 배열 내의 element에 key를 지정해야 한다.

```react
const numbers = [1, 2, 3, 4, 5];
const listItems = numbers.map((number) =>
	<li key={number.toString()}>
   	{number}
   </li>
);
```

<br>

- The best way to pick a key is to use a string that uniquely identifies a list item among its siblings.
  - key를 선택하는 가장 좋은 방법은 siblings 중 list 항목을 고유하게 식별하는 문자열을 사용하는 것이다.
- Most often you would use IDs from your data as keys:
  - 대부분의 경우 데이터의 ID를 key로 사용한다.

```react
const todoItems = todos.map((todo) =>
	<li key={todo.id}>
   	{todo.text}
   </li>
);
```

<br>

- When you don't have stable IDs for rendered items, you may use the item index as a key as a last resort:
  - 렌더링 된 항목에 대한 안정적인 ID가 없는 경우, 최후의 수단으로 항목 인덱스를 key로 사용할 수 있다.

```react
const todoItems = todos.map((todo, index) =>
   // Only do this if items have no stable IDs
	<li key={index}>
   	{todo.text}
   </li>
);
```

<br>

- We don't recommend using indexes for keys if the order of items may change.
  - 항목 순서가 변경될 수 있는 경우, key에 인덱스를 사용하지 않는 것이 좋다.
- This can negatively impact performance and may cause issues with component state.
  - 이로 인해 성능이 저하되고, 컴포넌트 state와 관련된 문제가 발생할 수 있다.
- Check out Robin Pokorny's article for an [in-depth explanation on the negative impacts of using an index as a key](https://medium.com/@robinpokorny/index-as-a-key-is-an-anti-pattern-e0349aece318).
  - [인덱스를 key로 사용하는 부정적인 영향에 대한 설명](https://medium.com/@robinpokorny/index-as-a-key-is-an-anti-pattern-e0349aece318)은 Robin Pokorny의 기사를 확인해라.
- If you choose not to assign an explicit key to list items then React will default to using indexes as keys.
  - list 항목에 명시적인 key를 지정하지 않는다면, React는 기본적으로 인덱스를 key로 사용한다.

<br>

- Here is an [in-depth explanation about why keys are necessary](https://reactjs.org/docs/reconciliation.html#recursing-on-children) if you're interested in learning more.
  - 더 자세한 내용을 원하면 [key가 필요한 이유에 대한 설명](https://reactjs.org/docs/reconciliation.html#recursing-on-children)을 참고해라.

------

<br>

## Extracting Component with Keys

###### key로 컴포넌트 추출하기

<br>

- Keys only make sense in the context of the surrounding array.
  - key는 주변 배열의 context에서만 의미가 있다.

<br>

- For example, if you [extract](https://reactjs.org/docs/components-and-props.html#extracting-components) a `ListItem` component, you should keep the key on the `<ListItem />` elements in the array rather than on the `<li>` element in the `ListItem` itself.
  - 예를 들어, `ListItem` 컴포넌트를 [추출](https://reactjs.org/docs/components-and-props.html#extracting-components)하는 경우, `ListItem` 자체의 `<li>` element가 아니라, 배열의 `<ListItem />` element에 key를 유지해야 한다.

<br>

#### Example: Incorrect Key Usage

###### 예: 잘못된 key 사용

```react
function ListItem(props) {
   const value = props.value;
   return (
   	// Wrong! There is no need to specify the key here:
      <li key={value.toString()}>
      	{value}
      </li>
   );
}

function NumberList(props) {
   const numbers = props.numbers;
   const listItems = numbers.map(
   	// Wrong! The key should have been specified here:
      <ListItem value={number} />
   );
   return (
   	<ul>
      	{listItems}
      </ul>
   );
}

const numbers = [1, 2, 3, 4, 5];

ReactDOM.render(
	<NumberList numbers={numbers} />,
   document.getElementById('root')
);
```

<br>

#### Example: Correct Key Usage

###### 예: 올바른 key 사용

```react
function ListItem(props) {
   // Correct! There is no need to specify the key here:
   return <li>{props.value}</li>
}

function NumberList(props) {
   const numbers = props.numbers;
   const listItems = numbers.map(
   	// Correct! Key should be specified inside the array.
      <ListItem key={number.toString()}
         value={number} />
   );
   return (
   	<ul>
      	{listItems}
      </ul>
   );
}

const numbers = [1, 2, 3, 4, 5];

ReactDOM.render(
	<NumberList numbers={numbers} />,
   document.getElementById('root')
);
```

[코드 실행 확인 링크](https://codepen.io/gaearon/pen/ZXeOGM?editors=0010)

<br>

- A good rule of thumb is that elements inside the `map()` call need keys.
  - 경험적으로 좋은 법칙은, `map()` 호출 내의 element에는 key가 필요하다는 것이다.

------

<br>

## Keys Must Only Be Unique Among Siblings

###### key는 siblings 중 유일해야 한다

<br>

- Keys used within arrays should be unique among their siblings.
  - 배열 내에서 사용되는 key는 siblings 중에서 고유해야 한다.
- However they don't need to be globally unique.
  - 하지만 전역적으로 고유할 필요는 없다.
- We can use the same keys when we produce two different arrays:
  - 두 개의 다른 배열을 생성할 때, 동일한 key를 사용할 수 있다.

```react
function Blog(props) {
   const sidebar = (
   	<ul>
      	{props.posts.map((post) =>
         	<li key={post.id}>
            	{post.title}
            </li>
         )}
      </ul>
   );
   
   const content = props.posts.map((post) =>
   	<div key={post.id}>
      	<h3>{post.title}</h3>
         <p>{post.content}</p>
      </div>
   );
   return (
   	<div>
      	{sidebar}
         <hr />
         {content}
      </div>
   );
}

const posts = [
   {id: 1, title: 'Hello World', content: 'Welcome to learning React!'},
   {id: 2, title: 'Installation', content: 'You can install React from npm.'}
];

ReactDOM.render(
	<Blog posts={posts} />,
   document.getElementById('root')
);
```

[코드 실행 확인 링크](https://codepen.io/gaearon/pen/NRZYGN?editors=0010)

<br>

- Keys serve as a hint to React but they don't get passed to your components.
  - React에서 key는 힌트와 같은 역할을 하지만, 컴포넌트로 전달되지는 않는다.
- If you need the same value in your component, pass it explicitly as a prop with a different name:
  - 컴포넌트에서 동일한 값을 필요로 한다면, 다른 이름의 prop으로 명시적으로 전달해라.

```react
const content = posts.map((post) =>
	<Post
      key={post.id}
      id={post.id}
      title={post.title} />
);
```

<br>

- With the example above, the `Post` component can read `props.id`, but not `props.key`.
  - 위의 예제에서 `Post` 컴포넌트는 `props.id`를 읽을 수 있지만, `props.key`는 읽을 수 없다.

------

<br>

## Embedding map() in JSX

###### JSX에서 map() 삽입하기

<br>

- In the examples above we declared a separate `listItems` variable and included it in JSX:
  - 위의 예제에서 별도의 `listItems` 변수를 선언하고, 이를 JSX에 포함시켰다.

```react
function NumberList(props) {
   const numbers = props.numbers;
   const listItems = numbers.map((number) =>
   	<ListItem key={number.toString()}
         value={number} />
   );
   return (
   	<ul>
      	{listItems}
      </ul>
   );
}
```

<br>

- JSX allows [embedding any expression](https://reactjs.org/docs/introducing-jsx.html#embedding-expressions-in-jsx) in curly braces so we could inline the `map()` result:
  - JSX는 `map()` 결과를 inline으로 처리할 수 있도록 모든 표현식을 중괄호에 포함할 수 있다.

```react
function ListItem(props) {
   return <li>{props.value}</li>;
}

function NumberList(props) {
   const numbers = props.numbers;
   return (
   	<ul>
      	{numbers.map((number) =>
         	<ListItem key={number.toString()}
               value={number} />
         )}
      </ul>
   );
}

const numbers = [1, 2, 3, 4, 5];

ReactDOM.render(
	<NumberList numbers={numbers} />,
   document.getElementById('root')
);
```

[코드 실행 확인 링크](https://codepen.io/gaearon/pen/BLvYrB?editors=0010)

<br>

- Sometimes this results in clearer code, but this style can also be abused.
  - 때로 코드가 더 명확해지지만, 스타일이 남용될 수도 있다.
- Like in JavaScript, it is up to you to decide whether it is worth extracting a variable for readability.
  - JavaScript와 마찬가지로, 가독성을 위해 변수로 추출할 가치가 있는지 여부를 결정하는 것은 당신의 몫이다.
- Keep in mind that if the `map()` body is too nested, it might be a good time to [extract a component](https://reactjs.org/docs/components-and-props.html#extracting-components).
  - `map()` body가 너무 많이 중첩되어 있으면, [컴포넌트를 분리](https://reactjs.org/docs/components-and-props.html#extracting-components)하는 것이 좋다.

------

<br>