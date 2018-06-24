---
layout: post
title: "공식 리액트 문서 번역 - 09. Forms (Main Concepts)"
categories: react
tags: react
---

[공식 리액트 문서 링크](https://reactjs.org/docs/forms.html)

<br>

## Forms

- ###### HTML form elements work a little bit differently from other DOM elements in React, because form elements naturally keep some internal state.

  - ###### HTML form element는 React의 다른 DOM element와 조금 다르게 작동한다.

  - ###### form element가 자연스럽게 내부 state를 유지하기 때문이다.

- ###### For example, this form in plain HTML accepts a single name:

  - ###### 예를 들어, 일반 HTML의 form은 단일 이름을 허용한다.

```html
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
  - 이 form에는 사용자가 form을 제출할 때 새 페이지를 탐색하는 기본 HTML form 동작이 있다.
- If you want this behavior in React, it just works.
  - React에서 이 동작을 원하면, 그냥 작동한다.
- But in most cases, it's convenient to have a JavaScript function that handles the submission of the form and has access to the data that the user entered into the form.
  - 하지만 대부분의 경우, form 제출을 처리하고, 사용자가 form에 입력한 데이터에 액세스할 수 있는 JavaScript 함수를 갖는 게 편리하다.
- The standard way to achieve this is with a technique called "controlled components".
  - 이를 달성하기 위한 표준 방법은 "controlled 컴포넌트"라는 기술을 사용하는 것이다.

------

<br>

### Controlled Components

###### controlled 컴포넌트

<br>

- In HTML, form elements such as `<input>`, `<textarea>`, and `<select>` typically maintain their own state and update it based on user input.
  - HTML에서, `<input>`, `<textarea>`, `<select>`와 같은 form element는 일반적으로 자체 state를 유지하고, 사용자 입력을 기반으로 업데이트 한다.
- In React, mutable state is typically kept in the state property of components, and only updated with [setState()](https://reactjs.org/docs/react-component.html#setstate).
  - React에서는 변경할 수 있는 state가 일반적으로 컴포넌트의 state 속성에 유지되며, [setState()](https://reactjs.org/docs/react-component.html#setstate)로만 업데이트 된다.

<br>

- We can combine the two by making the React state be the "single source of truth".
  - React의 state를 "single source of truth"로 만들어 두 가지를 결합할 수 있다.
  - `Single Source of Truth`: 대부분의 React 애플리케이션에서는 state 데이터를 root 컴포넌트에 모아둘 수 있다. state 데이터를 프로퍼티를 통해 컴포넌트 트리의 아랫방향으로 전달할 수 있고, 양방향 함수 바인딩을 활용해 트리 아래쪽에서 수집한 데이터를 다시 올려 보낼 수 있다. 그 결과 애플리케이션 전체의 상태 데이터가 한 곳에 존재하게 된다. 이를 '진실의 유일한 근원'이라 부른다.
- Then the React component that renders a form also controls what happens in that form on subsequent user input.
  - 그런 다음, form을 렌더링 하는 React 컴포넌트는 사용자 입력 시 해당 form에 이어서 일어나는 일을 제어한다.
- An input form element whose value is controlled by React in this way is called a "controlled component".
  - 이러한 방식으로 React에 의해 값이 제어되는 입력 form element를 "controlled 컴포넌트"라고 한다.

<br>

- For example, if we want to make the previous example log the name with it is submitted, we can write the form as a controlled component:
  - 예를 들어, 이전 예제가 제출될 때 이름을 기록하게 하려면, controlled 컴포넌트로 form을 작성할 수 있다.

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
```

[CodePen에서 시도](https://codepen.io/gaearon/pen/VmmPgp?editors=0010)

<br>

- Since the `value` attribute is set on our form element, the displayed value will always be `this.state.value`, making the React state the source of truth.
  - `value` 속성은 form element에 설정되므로, 표시되는 값은 항상 `this.state.value`가 되어, React의 state가 source of truth가 된다.
- Since `handleChange` runs on every keystroke to update the React state, the displayed value will update as the user types.
  - React의 state를 업데이트 하기 위해 모든 keystroke에서 `handleChange`가 실행되므로, 사용자가 입력할 때 표시된 값이 업데이트 된다.

<br>

- With a controlled component, every state mutation will have an associated handler function.
  - controlled 컴포넌트를 사용하면, 모든 state 변화에 연관된 핸들러 함수가 생긴다.
- This makes it straightforward to modify or validate user input.
  - 이렇게 하면, 사용자 입력을 수정하거나, 유효성을 검사하는 것이 수월해진다.
- For example, if we wanted to enforce that names are written with all uppercase letters, we could write `handleChange` as:
  - 예를 들어, 이름에 대문자가 쓰이도록 하고 싶다면, `handleChange`를 다음과 같이 작성할 수 있다.

```react
handleChange(event) {
   this.setState({value: event.target.value.toUpperCase()});
}
```

------

<br>

### The textarea Tag

###### 텍스트 영역 태그

<br>

- In HTML, a `<textarea>` element defines its text by its children:
  - HTML에서 `<textarea>` element는 텍스트를 자식으로 정의한다.

```react
<textarea>
	Hello there, this is some text in a text area
</textarea>
```

<br>

- In React, a `<textarea>` uses a `value` attribute instead.
  - React에서 `<textarea>`는 `value` 속성을 대신 사용한다.
- This way, a form using a `<textarea>` can be written very similarly to a form that uses a single-line input:
  - 이렇게 하면, `<textarea>`를 사용하는 form은 한 줄 입력을 사용하는 form과 매우 비슷하게 작성할 수 있다.

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
   
   handleChange(event){
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

- Notice that `this.state.value` is initialized in the constructor, so that the text area starts off with some text in it.
  - `this.state.value`가 생성자에서 초기화되므로, 텍스트 영역은 그 안에서 텍스트로 시작된다.

------

<br>

### The select Tag

###### select 태그

<br>

- In HTML, `<select>` creates a drop-down list.
  - HTML에서 `<select`는 드랍-다운 목록을 생성한다.
- For example, this HTML creates a drop-down list of flavors:
  - 예를 들어, 이 HTML은 다음과 같은 flavor 드랍-다운 목록을 생성한다.

```html
<select>
   <option value="grapefruit">Grapefruit</option>
   <option value="lime">Lime</option>
   <option selected value="coconut">Coconut</option>
   <option value="mango">Mango</option>
</select>
```

<br>

- Note that the Coconut option is initially selected, because of the `selected` attribute.
  - `selected` 속성 때문에, Coconut 옵션이 처음 선택된다.
- React, instead of using this `selected` attribute, uses a `value` attribute on the root `select` tag.
  - React는 `selected` 속성을 사용하는 대신, root `select` 태그에 `value` 속성을 사용한다.
- This is more convenient in a controlled component because you only need to update it in one place.
  - 한 곳에서 업데이트만 하면 되기 때문에 controlled 컴포넌트에서 더 편리하다.
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
            	Pick your favorite La Croix flavor:
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
```

[CodePen에서 시도](https://codepen.io/gaearon/pen/JbbEzX?editors=0010)

<br>

- Overall, this makes it so that `<input type="text">`, `<textarea>`, and `<select>` all work very similarly - they all accept a `value` attribute that you can use to implement a controlled component.
  - 전반적으로 이렇게 하면, `<input type="text">`, `<textarea>`, `<select>`는 모두 유사하게 작동한다.
  - 모두 controlled 컴포넌트를 구현하는 데 사용할 수 있는 `value` 속성을 허용한다.

<br>

> **Note**
>
> You can pass an array into the `value` attribute, allowing you to select multiple options in a `select` tag:
>
> `select` 태그에서 여러 옵션을 선택할 수 있도록`value` 속성에 배열을 전달할 수 있다.

```react
<select multiple={true} value={['B', 'C']}>
```

------

<br>

### The file input Tag

###### 파일 입력 태그

<br>

- In HTML, an `<input type="file">` lets the user choose one or more files from their device storage to be uploaded to a server or manipulated by JavaScript via the [File API](https://developer.mozilla.org/en-US/docs/Web/API/File/Using_files_from_web_applications).
  - HTML에서는, `<input type="file">`을 사용해서, 사용자가 장치 저장소에서 하나 이상의 파일을 선택하여 서버에 업로드하거나, [File API](https://developer.mozilla.org/en-US/docs/Web/API/File/Using_files_from_web_applications)를 통해 JavaScript로 조작할 수 있다.

```react
<input type="file" />
```

<br>

- Because its value is read-only, it is an **uncontrolled** component in React.
  - 이 값은 읽기 전용이므로, React에서 **uncontrolled 않는** 컴포넌트이다.
- It is discussed together with other uncontrolled components [later in the documentation](https://reactjs.org/docs/uncontrolled-components.html#the-file-input-tag).
  - 문서의 뒷부분에서 다른 uncontrolled 컴포넌트와 함께 검토된다.

------

<br>

### Handling Multiple Inputs

###### 여러 입력 처리

<br>

- When you need to handle multiple controlled `input` elements, you can add a `name` attribute to each element and let the handler function choose what to do based on the value of `event.target.name`.
  - 여러 개의 controlled `input` element를 처리해야 하는 경우, 각 element에 `name` 속성을 추가할 수 있고, 핸들러 함수가 `event.target.name`의 값에 따라 수행할 작업을 선택하게 할 수 있다.

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
            <lable>
            	Number of guests:
               <input
                  name="numberOfGuests"
                  type="number"
                  value={this.state.numberOfGuests}
                  onChange={this.handleInputChange} />
            </lable>
         </form>
      );
   }
}
```

[CodePen에서 시도](https://codepen.io/gaearon/pen/wgedvV?editors=0010)

<br>

- Note how we used the ES6 [computed property name](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Object_initializer#Computed_property_names) syntax to update the state key corresponding to the given input name:
  - 주어진 입력 이름에 해당하는 state key를 업데이트 하기 위해, ES6 [computed property name](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Object_initializer#Computed_property_names) 구문을 사용한 방법에 유의해라.

```react
this.setState({
   [name]: value
});
```

<br>

- It is equivalent to this ES5 code:
  - 위의 예제는 아래 ES5 코드와 동일하다.

```react
var partialState = {};
partialState[name] = value;
this.setState(partialState);
```

<br>

- Also, since `setState()` automatically [merges a partial state into the current state](https://reactjs.org/docs/state-and-lifecycle.html#state-updates-are-merged), we only needed to call it with the changed parts.
  - 또한, `setState()`는 부분 state를 현재 state로 자동 병합하므로, 변경된 부분만 호출하면 된다.

------

<br>

### Controlled Input Null Value

###### controlled 입력 Null 값

<br>

- Specifying the value prop on a [controlled component](https://reactjs.org/docs/forms.html#controlled-components) prevents the user from changing the input unless you desire so.
  - [controlled 컴포넌트](https://reactjs.org/docs/forms.html#controlled-components)에 prop 값을 지정해서, 원하는 경우가 아니면 사용자가 입력을 변경할 수 없다.
- If you've specified a `value` but the input is still editable, you may have accidentally set `value` to `undefined` or `null`.
  - `value`를 지정했지만 입력을 편집할 수 있는 경우, 실수로 `value`를 `undefiend`나 `null`로 설정할 수 있다.

<br>

- The following code demonstrates this. (The input is locked at first but becomes editable after a short delay.)
  - 다음 코드는 이를 보여준다.
  - 입력은 처음에 잠겨있지만, 잠시 후에 편집이 가능하게 된다.

```react
ReactDOM.render(<input value="hi" />, mountNode);

setTimeout(function() {
   ReactDOM.render(<input value={null} />, mountNode);
}, 1000);
```

------

<br>

### Alternatives to Controlled Components

###### controlled 컴포넌트에 대한 대안

<br>

- It can sometimes be tedious to use controlled components, because you need to write an event handler for every way your data can change and pipe all of the input state through a React component.
  - 때로는 controlled 컴포넌트를 사용하는 것이 지겨울 수 있다.
  - 데이터를 변경할 수 있는 모든 방법에 대해 이벤트 핸들러를 작성해야 하고, React 컴포넌트를 통해 모든 입력 state를 pipe해야 하기 때문이다.
- This can become particularly annoying when you are converting a preexisting codebase to React, or integrating a React application with a non-React library.
  - 기본의 코드 베이스를 React로 변환하거나, React 애플리케이션을 React 이외의 라이브러리와 통합할 때 특히 성가신 일이 될 수 있다.
- In these situations, you might want to check out [uncontrolled components](https://reactjs.org/docs/uncontrolled-components.html), an alternative technique for implementing input forms.
  - 이러한 상황에서는, 입력 form을 구현하기 위한 대체 기술인 [uncontrolled 컴포넌트](https://reactjs.org/docs/uncontrolled-components.html)를 확인해야 한다.

<br>