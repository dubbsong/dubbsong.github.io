---
layout: post
title: "리액트 공식 문서 번역 - 09. form (Main Concepts)"
categories: react
tags: React
---

###### [React 공식 문서](https://reactjs.org/docs/forms.html) 번역

<br>

# React: Forms

- HTML form elements work a little bit differently from other DOM elements in React, because form elements naturally keep some internal state.
  - HTML form element는 React의 다른 DOM element와 조금 다르게 작동한다.
  - form element가 선천적으로 내부 state를 유지하기 때문이다.
- For example, this form in plain HTML accepts a single name:
  - 예를 들어, 일반 HTML form은 하나의 이름을 허용한다.

```react
<form>
	<label>
   	Name:
      <input type="text" name="name" />
   </label>
   <input type="submit" value="Submit" />
</form>
```

<br>

- This form has the default HTML form behavior of browsing to a new page when the user submits the form.
  - 이 form에는 사용자가 form을 제출할 때 새 페이지로 이동하는 기본 HTML form 동작이 포함되어 있다.
- If you want this behavior in React, it just works.
  - React에서 이 동작을 원하는 경우, 그대로 사용할 수 있다.
- But in most cases, it's convenient to have a JavaScript function that handles the submission of the form and has access to the data that the user entered into the form.
  - 하지만 대부분의 경우, form 제출을 처리하고, 사용자가 form에 입력한 데이터에 액세스하는 JavaScript 함수를 갖는 게 편리하다.
- The standard way to achieve this is with a technique called "controlled components".
  - 이를 달성하기 위한 표준 방법은 "제어되는 컴포넌트"라는 기법을 사용하는 것이다.

------

<br>

## Controlled Components

###### 제어되는 컴포넌트

<br>

- In HTML, form elements such as `<input>`, `<textarea>`, and `<select>` typically maintain their own state and update it based on user input.
  - HTML에서 `<input>`, `<textarea>`, `<select>`와 같은 form element는 일반적으로 자체 state를 유지하고, 사용자 입력에 따라 이를 업데이트한다.
- In React, mutable state is typically kept in the state property of components, and only updated with [setState()](https://reactjs.org/docs/react-component.html#setstate).
  - React에서는, 일반적으로 컴포넌트의 state 속성에 변경 가능한 state가 유지되며, [setState()](https://reactjs.org/docs/react-component.html#setstate)를 통해서만 업데이트된다.

<br>

- We can combine the two by making the React state be the "single source of truth".
  - React state를 "single source of truth(신뢰할 수 있는 단일 소스)"로 만들어 두 가지를 결합할 수 있다.
- Then the React component that renders a form also controls what happens in that form on subsequent user input.
  - 그런 다음, form을 렌더링 하는 React 컴포넌트가 이후 사용자 입력 시 해당 form에서 일어나는 일을 제어한다.
- An input form element whose value is controlled by React in this way is called a "controlled component".
  - React에 의해 값이 제어되는 입력 form element를 "제어되는 컴포넌트"라고 한다.

<br>

- For example, if we want to make the previous example log the name when it is submitted, we can write the form as a controlled component:
  - 예를 들어, 이전 예제가 제출될 때 이름을 표시하도록 하려면, 제어되는 컴포넌트로 form을 작성할 수 있다.

```react
class NameForm extends React.Component {
   constructor(props) {
      super(props);
      this.state = {value: ''};
      
      this.handleChange = this.handleChange.bind(this);
      this.handleSubmit = this.handleSubmit.bind(this);
   }
   
   handleChange(event) {
      this.setState({value: event.target.value});
   }
   
   handleSubmit(event) {
      alert('A name was submitted: ' + this.state.value);
      event.preventDefault();
   }
   
   render() {
      return (
      	<form onSubmit={this.handleSubmit}>
         	<label>
            	Name:
               <input type="text" value={this.state.value} onChange={this.handleChange} />
            </label>
            <input type="submit" value="Submit" />
         </form>
      );
   }
}

ReactDOM.render(
	<NameForm />,
   document.getElementById('root')
);
```

[코드 실행 확인 링크](https://codepen.io/gaearon/pen/VmmPgp?editors=0010)

<br>

- Since the `value` attribute is set on our form element, the displayed value will always be `this.state.value`, making the React state the source of truth.
  - `value` 속성은 form element에 설정되므로, 표시되는 값은 항상 `this.state.value`가 된다.
  - React state가 source of truth가 된다.
- Since `handleChange` runs on every keystroke to update the React state, the displayed value will update as the user types.
  - React state를 업데이트하기 위해 키를 입력할 때마다 `handleChange`가 실행되기 때문에, 사용자의 입력에 따라 표시되는 값이 업데이트된다.

<br>

- With a controlled component, every state mutation will have an associated handler function.
  - 제어되는 컴포넌트를 사용한다는 것은, state가 변경될 때마다 연관된 핸들러 함수가 있다는 것이다.
- This makes it straightforward to modify or validate user input.
  - 간단하게 사용자 입력을 수정하거나 유효성을 검사할 수 있다.
- For example, if we wanted to enforce that names are written with all uppercase letters, we could write `handleChange` as:
  - 예를 들어, 입력된 이름을 모두 대문자로 쓰여지도록 하려면, `handleChange`를 다음과 같이 작성할 수 있다.

```react
handleChange(event) {
   this.setState({value: event.target.value.toUpperCase()});
}
```

------

<br>

## The textarea Tag

###### textarea 태그

<br>

- In HTML, a `<textarea>` element defines its text by its children:
  - HTML에서 `<textarea>` element는 자신의 텍스트를 children으로 정의한다.

```react
<textarea>
	Hello there, this is some text in a text area
</textarea>
```

<br>

- In React, a `<textarea>` uses a `value` attribute instead.
  - React에서 `<textarea>`는 `value` 속성을 대신 사용한다.
- This way, a form using a `<textarea>` can be written very similarly to a form that uses a single-line input:
  - 이렇게 하면, `<textarea>`를 사용하는 form을 한 줄 입력을 사용하는 form과 매우 유사하게 작성할 수 있다.

```react
class EssayForm extends React.Component {
   constructor(props) {
      super(props);
      this.state = {
         value: 'Please write an essay about your favorite DOM element.'
      };
      
      this.handleChange = this.handleChange.bind(this);
      this.handleSubmit = this.handleSubmit.bind(this);
   }
   
   handleChange(event) {
      this.setState({value: event.target.value});
   }
   
   handleSubmit(event) {
      alert('An essay was submitted: ' + this.state.value);
      event.preventDefault();
   }
   
   render() {
      return (
      	<form onSubmit={this.handleSubmit}>
         	<label>
            	Essay:
               <textarea value={this.state.value} onChange={this.handleChange} />
            </label>
            <input type="submit" value="Submit" />
         </form>
      );
   }
}
```

<br>

- Notice that `this.state.value` is initialized in the constructor, so that the text area starts off with some text in it.
  - `this.state.value`가 생성자에서 초기화되므로, 시작부터 텍스트 영역에 일부 텍스트가 포함된다.

------

<br>

## The select Tag

###### select 태그

<br>

- In HTML, `<select>` creates a drop-down list.
  - HTML에서 `<select>`는 드롭다운 list를 생성한다.
- For example, this HTML creates a drop-down list of flavors:
  - 예를 들어, HTML은 다음과 같은 맛의 드롭다운 list를 생성한다.

```react
<select>
	<option value="grapefruit">Grapefruit</option>
   <option value="lime">Lime</option>
   <option selected value="coconut">Coconut</option>
   <option value="mango">Mango</option>
</select>
```

<br>

- Note that the Coconut option is initially selected, because of the `selected` attribute.
  - `selected` 속성 때문에 Coconut 옵션이 처음에 선택된다.
- React, instead of using this `selected` attribute, uses a `value` attribute on the root `select` tag.
  - React는 `selected` 속성을 사용하는 대신, root `select` 태그에 `value` 속성을 사용한다.
- This is more convenient in a controlled component because you only need to update it in one place.
  - 한 곳에서 업데이트만 하면 되기 때문에, 제어되는 컴포넌트에서 더 편리하다.

<br>

- For example:

```react
class FlavorForm extends React.Component {
   constructor(props) {
      super(props);
      this.state = {value: 'coconut'};
      
      this.handleChange = this.handleChange.bind(this);
      this.handleSubmit = this.handleSubmit.bind(this);
   }
   
   handleChange(event) {
      this.setState({value: event.target.value});
   }
   
   handleSubmit(event) {
      alert('Your favorite flavor is: ' + this.state.value);
      event.preventDefault();
   }
   
   render() {
      return (
      	<form onSubmit={this.handleSubmit}>
         	<label>
            	Pick your favorite flavor:
               <select value={this.state.value} onChange={this.handleChange}>
               	<option value="grapefruit">Grapefruit</option>
                  <option value="lime">Lime</option>
                  <option value="coconut">Coconut</option>
                  <option value="mango">Mango</option>
               </select>
            </label>
            <input type="submit" value="Submit" />
         </form>
      );
   }
}

ReactDOM.render(
	<FlavorForm />,
   document.getElementById('root')
);
```

[코드 실행 확인 링크](https://codepen.io/gaearon/pen/JbbEzX?editors=0010)

<br>

- Overall, this makes it so that `<input type="text">`, `<textarea>`, and `<select>` all work very similarly - they all accept a `value` attribute that you can use to implement a controlled component.
  - 전반적으로 이렇게 하면, `<input type="text">`, `<textarea>`, `<select>` 모두 매우 유사하게 작동한다.
  - 제어되는 컴포넌트를 구현하는 데 사용할 수 있는 `value` 속성을 모두 허용한다.

<br>

> Note
>
> You can pass an array into the `value` attribute, allowing you to select multiple options in a `select` tag:
>
> `select` 태그에서 여러 옵션을 선택할 수 있도록 `value` 속성에 배열을 전달할 수 있다.
>
> ```react
> <select multiple={true} value={['B', 'C']}>
> ```

------

<br>

## The file input Tag

###### 파일 input 태그

<br>

- In HTML, an `<input type="file">` lets the user choose one or more files from their device storage to be uploaded to a server or manipulated by JavaScript via the [File API](https://developer.mozilla.org/en-US/docs/Web/API/File/Using_files_from_web_applications).
  - HTML에서 `<input type="file">`을 사용하는 경우, 사용자가 장치 저장소에서 하나 이상의 파일을 선택하여 서버에 업로드하거나, [File API](https://developer.mozilla.org/en-US/docs/Web/API/File/Using_files_from_web_applications)를 통해 JavaScript로 조작할 수 있다.

```react
<input type="file" />
```

<br>

- Because its value is read-only, it is an `uncontrolled` component in React.
  - 이 값은 읽기 전용이므로, React에서 `제어되지 않는` 컴포넌트이다.
- It is discussed together with other uncontrolled components [later in the documentation](https://reactjs.org/docs/uncontrolled-components.html#the-file-input-tag).
  - 문서의 뒷부분에서 다른 제어되지 않는 컴포넌트와 함께 설명된다.

------

<br>

## Handling Multiple Inputs

###### 여러 input 핸들링

<br>

- When you need to handle multiple controlled `input` elements, you can add a `name` attribute to each element and let the handler function choose what to do based on the value of `event.target.name`.
  - 여러 제어되는 `input` element를 처리해야 하는 경우, 각 element에 `name` 속성을 추가할 수 있고, 핸들러 함수가 `event.target.name`의 값에 따라 수행할 작업을 선택할 수 있다.

<br>

- For example:

```react
class Reservation extends React.Component {
   constructor(props) {
      super(props);
      this.state = {
         isGoing: true,
         numberOfGuests: 2
      };
      
      this.handleInputChange = this.handleInputChange.bind(this);
   }
   
   handleInputChange(event) {
      const target = event.target;
      const value = target.type === 'checkbox' ? target.checked : target.value;
      const name = target.name;
      
      this.setState({
         [name]: value
      });
   }
   
   render() {
      return (
      	<form>
         	<label>
            	Is going:
               <input
                  name="isGoing"
                  type="checkbox"
                  checked={this.state.isGoing}
                  onChange={this.handleInputChange} />
            </label>
            <br />
            <label>
            	Number of guests:
               <input
                  name="numberOfGuests"
                  type="number"
                  value={this.state.numberOfGuests}
                  onChange={this.handleInputChange} />
            </label>
         </form>
      );
   }
}

ReactDOM.render(
	<Reservation />,
   document.getElementById('root')
);
```

[코드 실행 확인 링크](https://codepen.io/gaearon/pen/wgedvV?editors=0010)

<br>

- Note how we used the ES6 [computed property name](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Object_initializer#Computed_property_names) syntax to update the state key corresponding to the given input name:
  - ES6 [계산된 속성 이름](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Object_initializer#Computed_property_names) 구문을 사용해서 주어진 input name에 해당하는 state key를 업데이트한다.

```react
this.setState({
   [name]: value
});
```

<br>

- It is equivalent to this ES5 code:
  - 아래 ES5 코드와 동일하다.

```react
var partialState = {};
partialState[name] = value;
this.setState(partialState);
```

<br>

- Also, since `setState()` automatically [merges a partial state into the current state](https://reactjs.org/docs/state-and-lifecycle.html#state-updates-are-merged), we only needed to call it with the changed parts.
  - `setState()`는 자동으로 부분적인 state를 현재 state로 병합하므로, 변경된 부분만 호출하면 된다.

------

<br>

## Controlled Input Null Value

###### 제어되는 input Null 값

<br>

- Specifying the value prop on a [controlled component](https://reactjs.org/docs/forms.html#controlled-components) prevents the user from changing the input unless you desire so.
  - [제어되는 컴포넌트](https://reactjs.org/docs/forms.html#controlled-components)에 prop 값을 지정하면, 원하는 경우를 제외하고 사용자가 input을 변경할 수 없다.
- If you've specified a `value` but the input is still editable, you may have accidentally set `value` to `undefined` or `null`.
  - `value`를 지정했지만 여전히 input을 편집할 수 있는 경우, 실수로 `value`를 `undefined` 또는 `null`로 설정할 수 있다.

<br>

- The following code demonstrates this. (The input is locked at first but becomes editable after a short delay.)
  - 다음 코드는 이를 보여준다.
  - (input은 처음에 잠겨있지만, 잠시 후 편집 가능하게 된다.)

```react
ReactDOM.render(<input value="h1" />, mountNode);

setTimeout(function() {
   ReactDOM.render(<input value={null} />, mountNode);
}, 1000);
```

------

<br>

## Alternatives to Controlled Components

###### 제어되는 컴포넌트에 대한 대안

<br>

- It can sometimes be tedious to use controlled components, because you need to write an event handler for every way your data can change and pipe all of the input state through a React component.
  - 데이터가 변경될 수 있는 모든 방법에 대한 이벤트 핸들러를 작성해야 하고, React 컴포넌트를 통해 모든 input state를 연결해야 하기 때문에, 때로는 제어되는 컴포넌트를 사용하는 것이 번거로울 수 있다.
- This can become particularly annoying when you are converting a preexisting codebase to React, or integrating a React application with a non-React library.
  - 기존의 코드베이스를 React로 변환하거나, React 애플리케이션을 React 이외의 라이브러리와 통합하려는 경우, 이는 특히 성가시게 될 수 있다.
- In these situations, you might want to check out [uncontrolled components](https://reactjs.org/docs/uncontrolled-components.html), an alternative technique for implementing input forms.
  - 이러한 상황에서는 input form을 구현하기 위한 대체 기술인 [제어되지 않는 컴포넌트](https://reactjs.org/docs/uncontrolled-components.html)를 확인해야 할 수 있다.

------

<br>