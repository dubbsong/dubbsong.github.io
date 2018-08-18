---
layout: post
title: "리액트 공식 문서 번역 - 10. state 끌어올리기 (Main Concepts)"
categories: react
tags: React
---

###### [React 공식 문서](https://reactjs.org/docs/lifting-state-up.html) 번역

<br>

# Lifting State Up

###### state 끌어올리기

<br>

- Often, several components need to reflect the same changing data.
  - 종종 여러 컴포넌트가 동일한 변경 데이터를 반영해야 한다.
- We recommend lifting the shared state up to their closest common ancestor.
  - 가장 가까운 공통 조상으로 공유된 state를 끌어올리는 것이 좋다.
- Let's see how this works in action.
  - 이것이 어떻게 작동하는지 살펴보자.

<br>

- In this section, we will create a temperature calculator that calculates whether the water would boil at a given temperature.
  - 이 섹션에서는 특정 온도에서 물이 끓는지 여부를 계산하는 온도 계산기를 작성한다.

<br>

- We will start with a component called `BoilingVerdict`.
  - `BoilingVerdict`라는 컴포넌트로 시작한다.
- It accepts the `celsius` temperature as a prop, and prints whether it is enough to boil the water:
  - 이 컴포넌트는 `celsius(섭씨)` 온도를 prop으로 받아들여, 물을 끓일 만큼 충분한지를 출력한다.

```react
function BoilingVerdict(props) {
   if (props.celsius >= 100) {
      return <p>The water would boil.</p>;
   }
   return <p>The water would not boil.</p>;
}
```

<br>

- Next, we will create a component called `Calculator`.
  - 다음으로, `Calculator`라는 컴포넌트를 만든다.
- It renders an `<input>` that lets you enter the temperature, and keeps its value in `this.state.temperature`.
  - 온도를 입력할 수 있는 `<input>`을 렌더링 하고, 이 값을 `this.state.temperature`에 유지한다.

<br>

- Additionally, it renders the `BoilingVerdict` for the current input value.
  - 게다가, 현재 input 값에 `BoilingVerdict`를 렌더링 한다.

```react
function BoilingVerdict(props) {
   if (props.celsius >= 100) {
      return <p>The water would boil.</p>;
   }
   return <p>The water would not boil.</p>;
}

class Calculator extends React.Component {
   constructor(props) {
      super(props);
      this.handleChange = this.handleChange.bind(this);
      this.state = {temperature: ''};
   }
   
   handleChange(e) {
      this.setState({temperature: e.target.value});
   }
   
   render() {
      const temperature = this.state.temperature;
      return (
      	<fieldset>
         	<legend>Enter temperature in Celsius:</legend>
            <input
               value={temperature}
               onChange={this.handleChange} />
            
            <BoilingVerdict
               celsius={parseFloat(temperature)} />
            
         </fieldset>
      );
   }
}

ReactDOM.render(
	<Calculator />,
   document.getElementById('root')
);
```

[코드 실행 확인 링크](https://codepen.io/gaearon/pen/ZXeOBm?editors=0010)

------

<br>

## Adding a Second Input

###### 두 번째 input 추가하기

<br>

- Our new requirement is that, in addition to a Celsius input, we provide a Fahrenheit input, and they are kept in sync.
  - 새로운 요구사항은, Celsius input과 함께 Fahrenheit input을 제공하고, 동기화를 유지한다는 것이다.

<br>

- We can start by extracting a `TemperatureInput` component from `Calculator`.
  - `Calculator`에서 `TemperatureInput` 컴포넌트를 분리해서 시작할 수 있다.
- We will add a new `scale` prop to it that can either be `"c"` or `"f"`:
  - `"c"` 또는 `"f"` 중 하나가 될 새로운 `scale` prop을 추가한다.

```react
const scaleNames = {
   c: 'Celsius',
   f: 'Fahrenheit'
};

class TemperatureInput extends React.Component {
   constructor(props) {
      super(props);
      this.handleChange = this.handleChange.bind(this);
      this.state = {temperature: ''};
   }
   
   handleChange(e) {
      this.setState({temperature: e.target.value});
   }
   
   render() {
      const temperature = this.state.temperature;
      const scale = this.props.scale;
      return (
      	<fieldset>
         	<legend>Enter temperature in {scaleNames[scale]}:</legend>
            <input value={temperature}
               onChange={this.handleChange} />
         </fieldset>
      );
   }
}
```

<br>

- We can now change the `Calculator` to render two separate temperature inputs:
  - 이제 `Calculator`를 변경해서 두 개의 별도 온도 input을 렌더링 할 수 있다.

```react
class Calculator extends React.Component {
   render() {
      return (
      	<div>
         	<TemperatureInput scale="c" />
            <TemperatureInput scale="f" />
         </div>
      );
   }
}

ReactDOM.render(
	<Calculator />,
   document.getElementById('root')
);
```

[코드 실행 확인 링크](https://codepen.io/gaearon/pen/jGBryx?editors=0010)

<br>

- We have two inputs now, but when you enter the temperature in one of them, the other doesn't update.
  - 지금 두 개의 input을 가지고 있지만, 그 중 하나에 온도를 입력하면, 다른 하나는 업데이트되지 않는다.
- This contradicts our requirement: we want to keep them in sync.
  - 이는 두 값이 동기화 상태로 유지하기를 원하는 요구사항에 모순된다.

<br>

- We also can't display the `BoilingVerdict` from `Calculator`.
  - 또한 `Calculator`에서 `BoilingVerdict`를 표시할 수도 없다.
- The `Calculator` doesn't know the current temperature because it is hidden inside the `TemperatureInput`.
  - `Calculator`는 `TemperatureInput` 내에 숨겨져 있기 때문에 현재 온도를 알지 못한다.

------

<br>

## Writing Conversion Functions

- First, we will write two functions to convert from Celsius to Fahrenheit and back:
  - 먼저, Celsius와 Fahrenheit를 서로 변환하는 두 개의 함수를 작성한다.

```react
function toCelsius(fahrenheit) {
   return (fahrenheit - 32) * 5 / 9;
}

function toFahrenheit(celsius) {
   return (celsius * 9 / 5) + 32;
}
```

<br>

- These two functions convert numbers.
  - 이 두 함수는 숫자를 변환한다.
- We will write another function that takes a string `temperature` and a converter function as arguments and returns a string.
  - 문자열 `temperature`와 변환기 함수를 인수로 받은 다음, 문자열을 반환하는 또 다른 함수를 작성한다.
- We will use it to calculate the value of one input based on the other input.
  - 이 함수를 사용해서 다른 input을 기반으로 하나의 input 값을 계산한다.

<br>

- It returns an empty string on an invalid `temperature`, and it keeps the output rounded to the third decimal place:
  - 이 함수는 유효하지 않은 `temperature`에 빈 문자열을 반환하고, 결과값의 소수점 셋째 이하로 반올림한다.

```react
function tryConvert(temperature, convert) {
   const input = parseFloat(temperature);
   if (Number.isNaN(input)) {
      return '';
   }
   const output = convert(input);
   const rounded = Math.round(output * 1000) / 1000;
   return rounded.toString();
}
```

<br>

- For example, `tryConvert('abc', toCelsius)` returns an empty string, and `tryConvert('10.22', toFahrenheit)` returns `'50.396'`.
  - 예를 들어, `tryConvert('abc' toCelsius)`는 빈 문자열을 반환하고, `tryConvert('10.22', toFahrenheit)`은 `'50.396'`을 반환한다.

------

<br>

## Lifting State Up

###### state 끌어올리기

<br>

- Currently, both `TemperatureInput` components independently keep their values in the local state:
  - 현재 두 `TemperatureInput` 컴포넌트는 값을 로컬 state에서 독립적으로 유지한다.

```react
class TemperatureInput extends React.Component {
   constructor(props) {
      super(props);
      this.handleChange = this.handleChange.bind(this);
      this.state = {temperature: ''};
   }
   
   handleChange(e) {
      this.setState({temperature: e.target.value});
   }
   
   render() {
      const temperature = this.state.temperature;
      // ...
```

<br>

- However, we want these two inputs to be in sync with each other.
  - 하지만, 이 두 input이 서로 동기화 상태를 유지해야 한다.
- When we update the Celsius input, the Fahrenheit input should reflect the converted temperature, and vice versa.
  - Celsius input을 업데이트할 때, Fahrenheit input은 변환된 온도를 반영해야 하며, 그 반대의 경우도 마찬가지이다.

<br>

- In React, sharing state is accomplished by moving it up to the closest common ancestor of the components that need it.
  - React에서 state를 공유하려면, 그것을 필요로 하는 컴포넌트의 가장 가까운 공통 조상으로 state를 이동시킴으로써 이루어진다.
- This is called "lifting state up".
  - 이를 "state 끌어올리기"라고 한다.
- We will remove the local state from the `TemperatureInput` and move it into the `Calculator` instead.
  - `TemperatureInput`에서 로컬 state를 제거하고, 대신 `Calculator`로 옮긴다.

<br>

- If the `Calculator` owns the shared state, it becomes the "source of truth" for the current temperature in both inputs.
  - `Calculator`가 공유된 state를 소유하는 경우, 두 input의 현재 온도에 대한 "source of truth"가 된다.
- It can instruct them both to have values that are consistent with each other.
  - 이를 통해 두 input이 서로 일치하는 값을 갖도록 할 수 있다.
- Since the props of both `TemperatureInput` components are coming from the same parent `Calculator` component, the two inputs will always be in sync.
  - 두 `TemperatureInput` 컴포넌트의 props가 동일한 부모 `Calculator` 컴포넌트로부터 전달되기 때문에, 두 input이 항상 동기화 상태를 유지한다.

<br>

- Let's see how this works step by step.
  - 어떻게 단계적으로 작동하는지 살펴보자.

<br>

- First, we will replace `this.state.temperature` with `this.props.temperature` in the `TemperatureInput` component.
  - 먼저, `TemperatureInput` 컴포넌트에서 `this.state.temperature`를 `this.props.temperature`로 대체한다.
- For now, let's pretend `this.props.temperature` already exists, although we will need to pass it from the `Calculator` in the future:
  - `Calculator`에서 전달할 필요가 있지만, 이미 `this.props.temperature`가 존재한다고 가정해보자.

```react
render() {
   // Before: const temperature = this.state.temperature;
   const temperature = this.props.temperature;
   /// ...
```

<br>

- We know that [props are read-only](https://reactjs.org/docs/components-and-props.html#props-are-read-only).
  - [props는 읽기 전용](https://reactjs.org/docs/components-and-props.html#props-are-read-only)이다.
- When the `temperature` was in the local state, the `TemperatureInput` could just call `this.setState()` to change it.
  - `temperature`가 로컬 state에 있을 때, `TemperatureInput`은 `this.setState()`를 호출해서 변경할 수 있었다.
- However, now that the `temperature` is coming from the parent as a prop, the `TemperatureInput` has no control over it.
  - 하지만 이제 `temperature`가 부모로부터 prop으로 전달받기 때문에, `TemperatureInput`이 해당 값을 제어할 수 없다.

<br>

- In React, this is usually solved by making a component "controlled".
  - React에서는 일반적으로 "제어되는" 컴포넌트를 생성함으로써 해결된다.
- Just like the DOM `<input>` accepts both a `value` and an `onChange` prop, so can the custom `TemperatureInput` accept both `temperature` and `onTemperatureChange` props from its parent `Calculator`.
  - DOM `<input>`이 `value`와 `onChange` prop을 모두 전달받듯이, 사용자 정의 `TemperatureInput`도 부모 `Calculator`로부터 `temperature`와 `onTemperatureChange` props를 모두 전달받을 수 있다.

<br>

- Now, when the `TemperatureInput` wants to update its temperature, it calls `this.props.onTemperatureChange`:
  - 이제 `TemperatureInput`이 온도를 업데이트하려는 경우, `this.props.onTemperatureChange`를 호출한다.

```react
handleChange(e) {
   // Before: this.setState({temperature: e.target.value});
   this.props.onTemperatureChange(e.target.value);
   // ...
```

<br>

> Note:
>
> There is no special meaning to either `temperature` or `onTemperatureChange` prop names in custom components.
>
> 사용자 정의 컴포넌트의 `temperature` 또는 `onTemperatureChange` prop 이름에는 특별한 의미가 없다.

> We could have called them anything else, like name them `value` and `onChange` which is a common convention.
>
> 해당 이름을 일반적으로 사용하는 `value`와 `onChange` 같은 이름으로 변경해도 무방하다.

<br>

- The `onTemperatureChange` prop will be provided together with the `temperature` prop by the parent `Calculator` component.
  - `onTemperatureChange` prop은 `temperature` prop과 함께 부모 `Calculator` 컴포넌트로부터 제공된다.
- It will handle the change by modifying its own local state, thus re-rendering both inputs with the new values.
  - 이는 자체 로컬 state를 수정해서 변경을 처리하므로, 두 input을 새 값으로 다시 렌더링 한다.
- We will look at the new `Calculator` implementation very soon.
  - 곧 새로운 `Calculator` 구현을 살펴볼 것이다.

<br>

- Before diving into the changes in the `Calculator`, let's recap our changes to the `TemperatureInput` component.
  - `Calculator`의 변경을 살펴보기 전에, `TemperatureInput` 컴포넌트에 대한 변경을 요약해보자.
- We have removed the local state from it, and instead of reading `this.state.temperature`, we now read `this.props.temperature`.
  - 로컬 state를 제거하고, `this.state.temperature`를 읽는 대신, 이제 `this.props.temperature`를 읽는다.
- Instead of calling `this.setState()` when we want to make a change, we now call `this.props.onTemperatureChange()`, which will be provided by the `Calculator`:
  - 변경하려는 경우, `this.setState()`를 호출하는 대신, `Calculator`에서 제공된 `this.props.onTemperatureChange()`를 호출한다.

```react
class TemperatureInput extends React.Component {
   constructor(props) {
      super(props);
      this.handleChange = this.handleChange.bind(this);
   }
   
   handleChange(e) {
      this.props.onTemperatureChange(e.target.value);
   }
   
   render() {
      const temperature = this.props.temperature;
      const scale = this.props.scale;
      return (
      	<fieldset>
         	<legend>Enter temperature in {scaleNames[scale]}:</legend>
            <input value={temperature}
               onChange={this.handleChange} />
         </fieldset>
      );
   }
}
```

<br>

- Now let's turn to the `Calculator` component.
  - 이제 `Calculator` 컴포넌트를 살펴보자.

<br>

- We will store the current input's `temperature` and `scale` in its local state.
  - 현재 input의 `temperature`와 `scale`을 로컬 state에 저장한다.
- This is the state we "lifted up" from the inputs, and it will serve as the "source of truth" for both of them.
  - 이는 input으로부터 "끌어올린" state이며, 양쪽 모두에 대해 "source of truth"로 역할을 한다.
- It is the minimal representation of all the data we need to know in order to render both inputs.
  - 두 input을 렌더링 하기 위해 알아야 하는 모든 데이터를 최소한으로 표현한 것이다.

<br>

- For example, if we enter 37 into the Celsius input, the state of the `Calculator` component will be:
  - 예를 들어, Celsius input에 37을 입력하면, `Calculator` 컴포넌트의 state는 다음과 같다.

```react
{
   temperature: '37',
   scale: 'c'
}
```

<br>

- If we later edit the Fahrenheit field to be 212, the state of the `Calculator` will be:
  - 나중에 Fahrenheit field를 212로 편집하면, `Calculator`의 state는 다음과 같다.

```react
{
   temperature: '212',
   scale: 'f'
}
```

<br>

- We could have stored the value of both inputs but it turns out to be unnecessary.
  - 양쪽 input 값을 저장할 수 있지만, 불필요한 것으로 확인되었다.
- It is enough to store the value of the most recently changed input, and the scale that it represents.
  - 가장 최근에 변경된 input과, 그것이 나타내는 scale을 저장하는 것으로 충분하다.
- We can then infer the value of the other input based on the current `temperature` and `scale` alone.
  - 현재 `temperature`와 `scale`만으로 다른 input 값을 추론할 수 있다.

<br>

- The inputs stay in sync because their values are computed from the same state:
  - input 값은 동일한 state로부터 계산되기 때문에, 동기화 상태를 유지한다.

```react
const scaleNames = {
   c: 'Celsius',
   f: 'Fahrenheit'
};

function toCelsius(fahrenheit) {
   return (fahrenheit - 32) * 5 / 9;
}

function toFahrenheit(celsius) {
   return (celsius * 9 / 5) + 32;
}

function tryConvert(temperature, convert) {
   const input = parseFloat(temperature);
   if (Number.isNaN(input)) {
      return '';
   }
   const output = convert(input);
   const rounded = Math.round(output * 1000) / 1000;
   return rounded.toString();
}

function BoilingVerdict(props) {
   if (props.celsius >= 100) {
      return <p>The water would boil.</p>;
   }
   return <p>The water would not boil.</p>;
}

class TemperatureInput extends React.Component {
   constructor(props) {
      super(props);
      this.handleChange = this.handleChange.bind(this);
   }
   
   handleChange(e) {
      this.props.onTemperatureChange(e.tartget.value);
   }
   
   render() {
      const temperature = this.props.temperature;
      const scale = this.props.scale;
      return (
      	<fieldset>
         	<legend>Enter temperature in {scaleNames[scale]}:</legend>
            <input value={temperature}
               onChange={this.handleChange} />
         </fieldset>
      );
   }
}

class Calculator extends React.Component {
   constructor(props) {
      super(props);
      this.handleCelsiusChange = this.handleCelsiusChange.bind(this);
      this.handleFahrenheitChange = this.handleFahrenheitChange.bind(this);
      this.state = {temperature: '', scale: 'c'};
   }
   
   handleCelsiusChange(temperature) {
      this.setState({scale: 'c', temperature});
   }
   
   handleFahrenheitChange(temperature) {
      this.setState({scale: 'f', temperature});
   }
   
   render() {
      const scale = this.state.scale;
      const temperature = this.state.temperature;
      const celsius = scale === 'f' ? tryConvery(temperature, toCelsius) : temperature;
      const fahrenheit = scale === 'c' ? tryConvert(temperature, toFahrenheit) : temperature;
      
      return (
      	<div>
         	<TemperatureInput
               scale="c"
               temperature={celsius}
               onTemperatureChange={this.handleCelsiusChange} />
            
            <TemperatureInput
               scale="f"
               temperature={fahrenheit}
               onTemperatureChange={this.handleFahrenheitChange} />
            
            <BoilingVerdict
               celsius={parseFloat(celsius)} />
            
         </div>
      );
   }
}

ReactDOM.render(
	<Calculator />,
   document.getElementById('root')
);
```

[코드 실행 확인 링크](https://codepen.io/gaearon/pen/WZpxpz?editors=0010)

<br>

- Now, no matter which input you edit, `this.state.temperature` and `this.state.scale` in the `Calculator` get updated.
  - 이제 input을 편집해도 괜찮다.
  - `Calculator`의 `this.state.temperature`와 `this.state.scale`이 업데이트된다.
- One of the inputs gets the value as is, so any user input is preserved, and the other input value is always recalculated based on it.
  - input 중 하나가 값을 가져오므로, 모든 사용자 input이 보존되고, 다른 input 값은 그 값을 기반으로 항상 다시 계산된다.

<br>

- Let's recap what happens when you edit an input:
  - input을 편집할 때 일어나는 일을 요약해보자.

<br>

> React calls the function specified as `onChange` on the DOM `<input>`.
>
> React는 DOM `<input>`에서 `onChange`로 지정된 함수를 호출한다.
>
> In our case, this is the `handleChange` method in the `TemperatureInput` component.
>
> 이 경우, `TemperatureInput` 컴포넌트의 `handleChange` 메소드이다.

> The `handleChange` method in the `TemperatureInput` component calls `this.props.onTemperatureChange()` with the new desired value.
>
> `TemperatureInput` 컴포넌트의 `handleChange` 메소드는 `this.props.onTemperatureChange()`를 새로운 원하는 값으로 호출한다.
>
> Its props, including `onTemperatureChange`, were provided by its parent component, the `Calculator`.
>
> `onTemperatureChange`를 포함한 그 props는, 그 parent 컴포넌트인 `Calculator`에 의해 제공되었다.

> When it previously rendered, the `Calculator` has specified that `onTemperatureChange` of the Celsius `TemperatureInput` is the `Calculator`'s `handleCelsiusChange` method, and `onTemperatureChange` of the Fahrenheit `TemperatureInput` is the `Calculator`'s `handleFahrenheitChange` method.
>
> 이전에 렌더링 할 때, `Calculator`는 Celsius `TemperatureInput`의 `onTemperatureChange`가 `Calculator`의 `handleCelsiusChange` 메소드임을 지정하고, Fahrenheit `TemperatureInpiut`의 `onTemperatureChange`가 `Calculator`의 `handleFahrenheitChange` 메소드임을 지정한다.
>
> So either of these two `Calculator` methods gets called depending on which input we edited.
>
> 따라서 이 두 `Calculator` 메소드 중 하나가, 편집한 input에 따라 호출된다.

> Inside these methods, the `Calculator` component asks React to re-render itself by calling `this.setState()` with the new input value and the current scale of the input we just edited.
>
> 이러한 메소스들 안에서, `Calculator` 컴포넌트는 React에게 스스로를 다시 렌더링 하도록 요청한다.
>
> 새 input 값과, 방금 편집한 input의 현재 scale로 `this.setState()`를 호출한다.

> React calls the `Calculator` component's `render` method to learn what the UI should look like.
>
> React는 `Calculator` 컴포넌트의 `render` 메소드를 호출해서 UI가 어떻게 보이는지를 확인한다.
>
> The values of both inputs are recomputed based on the current temperature and the active scale.
>
> 두 input 값은 현재 temperature와 active scale에 따라 다시 계산된다.
>
> The temperature conversion is performed here.
>
> temperature 변환은 여기에서 수행된다.

> React calls the `render` methods of the individual `TemperatureInput` components with their new props specified by the `Calculator`.
>
> React는 개별 `TemperatureInput` 컴포넌트의 `render` 메소드를 `Calculator`에서 지정한 새 props로 호출한다.
>
> It learns what their UI should look like.
>
> UI가 어떻게 보이는지를 확인한다.

> React calls the `render` method of the `BoilingVerdict` component, passing the temperature in Celsius as its props.
>
> React는 `BoilingVerdict` 컴포넌트의 `render` 메소드를 호출하고, Celsius의 temperature를 해당 props로 전달한다.

> ReactDOM updates the DOM with the boiling verdict and to match the desired input values.
>
> ReactDOM은 끓는 점으로 DOM을 업데이트하고, 원하는 input 값을 일치시킨다.
>
> The input we just edited receives its current value, and the other input is updated to the temperature after conversion.
>
> 방금 편집한 input은 현재 값을 받고, 다른 input은 변환한 후 temperature로 업데이트된다.

<br>

- Every update goes through the same steps so the inputs stay in sync.
  - 모든 업데이트는 동일한 단계를 거치기 때문에 input이 동기화 상태를 유지한다.

------

<br>

## Lessons Learned

###### 교훈

<br>

- There should be a single "source of truth" for any data that changes in a React application.
  - React 애플리케이션에서 변경되는 모든 데이터에 대한 하나의 "source of truth"가 있어야 한다.
- Usually, the state is first added to the component that needs it for rendering.
  - 일반적으로, state는 렌더링을 위해 필요한 컴포넌트에 처음으로 추가된다.
- Then, if other components also need it, you can lift it up to their closest common ancestor.
  - 그런 다음, 다른 컴포넌트에서도 필요하다면, 가장 가까운 공통 조상까지 끌어올릴 수 있다.
- Instead of trying to sync the state between different components, you should rely on the [top-down data flow](https://reactjs.org/docs/state-and-lifecycle.html#the-data-flows-down).
  - 다른 컴포넌트 간에 state를 동기화하려는 대신, [하향식 데이터 흐름](https://reactjs.org/docs/state-and-lifecycle.html#the-data-flows-down)에 의존해야 한다.

<br>

- Lifting state involves writing more "boilerplate" code than two-way binding approaches, but as a benefit, it takes less work to find and isolate bugs.
  - state 끌어올리기는 "boilerplate" 코드를 작성하는 것이 양방향 바인딩 접근보다 더 많이 포함되지만, 이점으로 버그를 찾고 격리하는 작업이 줄어든다.
- Since any state "lives" in some component and that component alone can change it, the surface area for bugs is greatly reduced.
  - 모든 state가 일부 컴포넌트에 "존재"하고, 컴포넌트만 변경될 수 있기 때문에, 버그의 양이 크게 줄어든다.
- Additionally, you can implement any custom logic to reject or transform user input.
  - 게다가, 사용자 input을 거부하거나 변환하는 모든 사용자 정의 로직을 구현할 수 있다.

<br>

- If something can be derived from either props or state, it probably shouldn't be in the state.
  - props나 state에서 비롯될 수 있는 것이 있다면, 그것은 state에 있으면 안 된다.
- For example, instead of storing both `celsiusValue` and `fahrenheitValue`, we store just the last edited `temperature` and its `scale`.
  - 예를 들어, `celsiusValue`와 `fahrenheitValue`를 모두 저장하는 대신, 마지막으로 편집한 `temperature`와 그 `scale`을 저장한다.
- The value of the other input can always be calculated from them in the `render()` method.
  - 다른 input 값은 항상 `render()` 메소드에서 계산할 수 있다.
- This lets us clear or apply rounding to the other field without losing any precision in the user input.
  - 이를 통해 사용자 input에서 정밀함을 잃지 않고 다른 field에 반올림을 지우거나 적용할 수 있다.

<br>

- When you see something wrong in the UI, you can use [React Developer Tools](https://github.com/facebook/react-devtools) to inspect the props and move up the tree until you find the component responsible for updating the state.
  - UI에서 문제가 발생하면, [React 개발자 도구](https://github.com/facebook/react-devtools)를 사용해서 props를 검사하고, state 업데이트를 담당하는 컴포넌트를 찾을 때까지 트리 구조를 위로 이동시킬 수 있다.
- This lets you trace the bugs to their source:
  - 다음과 같이 버그를 소스로 찾을 수 있다.

![React img](/assets/img/react-official-main concepts-10-01.gif)

------

<br>
