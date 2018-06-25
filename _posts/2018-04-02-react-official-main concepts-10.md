---
layout: post
title: "공식 리액트 문서 번역 - 10. Lifting State up (Main Concepts)"
categories: react
tags: react
---

[공식 리액트 문서 링크](https://reactjs.org/docs/lifting-state-up.html)

<br>

## Lifting State Up

###### state 끌어올리기

<br>

- ###### Often, several components need to reflect the same changing data.

  - ###### 종종 여러 컴포넌트가 동일한 변경 데이터를 반영해야 한다.

- ###### We recommend lifting the shared state up to their closest common ancestor.

  - ###### 가장 가까운 공통 조상까지 공유 state를 끌어올리는 것이 좋다.

- ###### Let's see how this works in action.

  - ###### 어떻게 작동하는지 보자.

<br>

- In this section, we will create a temperature calculator that calculates whether the water would boil at a given temperature.
  - 이 섹션에서는, 주어진 온도에서 물이 끓을지를 계산하는 온도 계산기를 만들 것이다.

<br>

- We will start with a component called `BoilingVerdict`.
  - `BoilingVerdict`라는 컴포넌트로 시작할 것이다.
- It accepts the `celsius` temperature as a prop, and prints whether it is enough to boil the water:
  - `celsius(섭씨)` 온도를 prop으로 받아들이고, 물을 끓일 만큼 충분한지를 출력한다.

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
  - 다음으로, `Calculator`라는 컴포넌트를 만들 것이다.
- It renders an `<input>` that lets you enter the temperature, and keeps its value in `this.state.temperature`.
  - 온도를 입력할 수 있는 `<input>`을 렌더링 하고, 이 값을 `this.state.temperature`에 유지한다.

<br>

- Additionally, it renders the `BoilingVerdict` for the current input value.
  - 게다가, 현재 입력 값에 대해 `BoilingVerdict`를 렌더링 한다.

```react
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
      render (
      	<fieldset>
         	<legend>Enter temperature in Celsius:</legend>
            <input
               value={temperature}
               onChange={this.handleChange} />
            <BoilingVerdict celsius={parseFloat(temperature)} />
         </fieldset>
      );
   }
}
```

[CodePen에서 시도](https://codepen.io/gaearon/pen/ZXeOBm?editors=0010)

------

<br>

### Adding a Second Input

###### 두 번째 입력 추가

<br>

- Our new requirement is that, in addition to a Celsius input, we provide a Fahrenheit input, and they are kept in sync.
  - 새로운 요구 사항은, Celsius(섭씨) 입력과 함께 Fahrenheit(화씨) 입력을 제공하고, 동기화를 유지하는 것이다.

<br>

- We can start by extracting a `TemperatureInput` component from `Calculator`.
  - `Calculator`에서 `TemperatureInput` 컴포넌트를 추출해서 시작할 수 있다.
- We will add a new `scale` prop to it that can either be `"c"` or `"f"`:
  - `"c"` 또는 `"f"` 중 하나가 될 새로운 `scale` prop을 추가할 것이다.

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
  - 이제 `Calculator`를 변경해서 두 개의 별도 온도 입력을 렌더링 할 수 있다.

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
```

[CodePen에서 시도](https://codepen.io/gaearon/pen/jGBryx?editors=0010)

<br>

- We have two inputs now, but when you enter the temperature in one of them, the other doesn't update.
  - 지금 두 개의 입력을 가지고 있지만, 그 중 하나에 온도를 입력하면 다른 하나는 업데이트되지 않는다.
- This contradicts our requirement: we want to keep them in sync.
  - 이것은 요구 사항과 모순된다.
  - 우리는 동기화 유지를 원한다.

<br>

- We also can't display the `BoilingVerdict` from `Calculator`.
  - 또한 `Calculator`에서 `BoilingVerdict`를 표시할 수 없다.
- The `Calculator` doesn't know the current temperature because it is hidden inside the `TemperatureInput`.
  - `Calculator`는 현재 온도를 알지 못한다.
  - `TemperatureInput` 내부에 숨겨져 있기 때문이다.

------

<br>

### Writing Conversion Functions

###### 변환 함수 작성

<br>

- First, we will write two functions to convert from Celsius to Fahrenheit and back:
  - 먼저, Celsius(섭씨)에서 Fahrenheit(화씨)로 변환하는 두 가지 함수를 작성할 것이다.

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
  - 문자열 `temperature`와 변환 함수를 인수로 취해서 문자열을 반환하는 또 다른 함수를 작성할 것이다.
- We will use it to calculate the value of one input based on the other input.
  - 다른 입력을 기반으로 하나의 입력 값을 계산하는 데 이 값을 사용할 것이다.

<br>

- It returns an empty string on an invalid `temperature`, and it keeps the output rounded to the third decimal place:
  - 유효하지 않은 `temperature`에서 빈 문자열을 반환하고, 소수점 셋째 자리까지 반올림해서 출력한다.

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
  - 예를 들어 `tryConvert('abc', toCelsius)`는 빈 문자열을 반환하고, `tryConvert('10.22', toFahrenheit)`은 `'50.396'`을 반환한다.

------

<br>

### Lifting State Up

###### state 끌어올리기

<br>

- Currently, both `TemperatureInput` components independently keep their values in the local state:
  - 현재 두 `TemperatureInput` 컴포넌트는 로컬 state에서 독립적으로 값을 유지한다.

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
   }
}
```

<br>

- However, we want these two inputs to be in sync with each other.
  - 하지만, 두 입력이 서로 동기화되기를 원한다.
- When we update the Celsius input, the Fahrenheit input should reflect the converted temperature, and vice versa.
  - Celsius(섭씨) 입력을 업데이트할 때, Fahrenheit(화씨) 입력은 변환된 온도를 반영해야 하며, 반대의 경우도 마찬가지이다.

<br>

- In React, sharing state is accomplished by moving it up to the closets common ancestor of the components that need it.
  - React에서, 공유 state는 그것을 필요로 하는 컴포넌트의 가장 가까운 공통 조상으로 이동시킴으로써 이루어진다.
- This is called "lifting state up".
  - 이것을 "state 끌어올리기"라고 한다.
- We will remove the local state from the `TemperatureInput` and move it into the `Calculator` instead.
  - `TemperatureInput`에서 로컬 state를 제거하고, 대신 `Calculator`로 옮긴다.

<br>

- If the `Calculator` owns the shared state, it becomes the "source of truth" for the current temperature in both inputs.
  - `Calculator`가 공유 state를 소유하면, 두 입력에서 현재 온도에 대한 "source of truth"가 된다.
- It can instruct them both to have values that are consistent with each other.
  - 서로에게 일관성 있는 값을 갖도록 알릴 수 있다.
- Since the props of both `TemperatureInput` components are coming from the same parent `Calculator` component, the two inputs will always be in sync.
  - 두 `TemperatureInput` 컴포넌트의 prop이 동일한 부모 `Calculator` 컴포넌트에서 나오므로, 두 입력이 항상 동기화된다.

<br>

- Let's see how this works step by step.
  - 이것이 어떻게 단계적으로 작동하는지 보자.

<br>

- First, we will replace `this.state.temperature` with `this.props.temperature` in the `TemperatureInput` component.
  - 먼저, `this.state.temperature`를 `TemperatureInput` 컴포넌트의 `this.props.temperature`로 바꿀 것이다.
- For now, let's pretend `this.props.temperature` already exists, although we will need to pass it from the `Calculator` in the future:
  - 앞으로 `Calculator`에서 전달할 필요가 있을지라도 우선은, `this.props.temperature`가 이미 존재한다고 가정하자.

```react
render() {
   // Before: const temperature = this.state.temperature;
   const temperature = this.props.temperature;
   // ...
}
```

<br>

- We know that [props are read-only](https://reactjs.org/docs/components-and-props.html#props-are-read-only).
  - prop은 [읽기 전용](https://reactjs.org/docs/components-and-props.html#props-are-read-only)이라는 것을 알고 있다.
- When the `temperature` was in the local state, the `TemperatureInput` could just call `this.setState()` to change it.
  - `temperature`가 로컬 state에 있을 때, `TemperatureInput`은 `this.setState()`를 호출해서 변경할 수 있다.
- However, now that the `temperature` is coming from the parent as a prop, the `TemperatureInput` has no control over it.
  - 하지만, `temperature`가 부모로부터 prop으로 전달됨에 따라, `TemperatureInput`은 제어할 수 없다.

<br>

- In React, this is usually solved by making a component "controlled".
  - React에서는 일반적으로 컴포넌트를 "제어"함으로써 해결된다.
- Just like the DOM `<input>` accepts both a `value` and an `onChange` prop, so can the custom `TemperatureInput` accept both `temperature` and `onTemperatureChange` props from its parent `Calculator`.
  - DOM `<input>`이 `value`와 `onChange` prop을 모두 받는 것처럼, 사용자 정의 `TemperatureInput`도 부모 `Calculator`에서 `temperature`와 `onTemperatureChange` prop을 모두 받는다.

<br>

- Now, when the `TemperatureInput` wants to update its temperature, it calls `this.props.onTemperatureChange`:
  - 이제, `TemperatureInput`이 온도를 업데이트하려고 할 때, `this.props.onTemperatureChange`를 호출한다.

```react
handleChange(e) {
   // Before: this.setState({temperature: e.target.value});
   this.props.onTemperatureChange(e.target.value);
   // ...
}
```

<br>

> **Note:**
>
> There is no special meaning to either `temperature` or `onTemperatureChange` prop names in custom components.
>
> 사용자 정의 컴포넌트에서 `temperature`나 `onTemperatureChange` prop 이름에 특별한 의미는 없다.

> We could have called them anything else, like name them `value` and `onChange` which is a common convention.
>
> 그것들을 `value`와 `onChange` 같은 일반적인 협약처럼 다른 무엇으로 부를 수 있었다.

<br>

- The `onTemperatureChange` prop will be provided together with the `temperature` prop by the parent `Calculator` component.
  - `onTemperatureChange` prop은 부모 `Calculator` 컴포넌트의 `temperature` prop과 함께 제공된다.
- It will handle the change by modifying its own lacal state, thus re-rendering both inputs with the new values.
  - 자체 로컬 state를 수정해서 변경 사항을 처리하므로, 두 입력을 새 값으로 다시 렌더링 한다.
- We will look at the new `Calculator` implementation very soon.
  - 곧 새로운 `Calculator` 구현을 살펴볼 것이다.

<br>

- Before diving into the changes in the `Calculator`, let's recap our changes to the `TemperatureInput` component.
  - `Calculator`의 변경 사항을 살펴보기 전에, `TemperatureInput` 컴포넌트에 대한 변경 사항을 요약해보자.
- We have removed the local state from it, and instead of reading `this.state.temperature`, we now read `this.props.temperature`.
  - 로컬 state를 제거하고, `this.state.temperature`를 읽는 대신, `this.props.temperature`를 읽는다.
- Instead of calling `this.setState()` when we want to make a change, we now call `this.props.onTemperatureChange()`, which will be provided by the `Calculator`:
  - 변경하려는 경우 `this.setState()`를 호출하는 대신, `Calculator`에서 제공할 `this.props.onTemperatureChange()`를 호출한다.

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
            <input value={temperature} onChange={this.handleChange} />
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
  - 현재 입력의 `temperature`와 `scale`을 로컬 state로 저장한다.
- This is the state we "lifted up" from the inputs, and it will serve as the "source of truth" for both of them.
  - 이것은 입력으로부터 "들어올린" state고, 양쪽 모두를 위한 "source of truth"로 작용할 것이다.
- It is the minimal representation of all the data we need to know in order to render both inputs.
  - 두 입력을 렌더링 하기 위해 알아야 하는 모든 데이터를 최소한으로 표현한 것이다.

<br>

- For example, if we enter 37 into the Celsius input, the state of the `Calculator` component will be:
  - 예를 들어, Celsius 입력에 37을 입력하면, `Calculator` 컴포넌트의 state는 다음과 같다.

```react
{
   temperature: '37',
      scale: 'c'
}
```

<br>

- If we later edit the Fahrenheit field to be 212, the state of the `Calculator` will be:
  - 나중에 Fahrenheit 필드를 212로 편집하면, `Calculator`의 state는 다음과 같다.

```react
{
   temperature: '212',
      scale: 'f'
}
```

<br>

- We could have stored the value of both inputs but it turns out to be unnecessary.
  - 양쪽 입력 값을 저장할 수 있었지만, 불필요한 것으로 드러났다.
- It is enough to store the value of the most recently changed input, and the scale that it represents.
  - 가장 최근에 변경된 입력 값과, 그것이 나타내는 scale을 저장하는 것으로 충분하다.
- We can then infer the value of the other input based on the current `temperature` and `scale` alone.
  - 현재 `temperature`와 `scale`만으로 다른 입력 값을 추론할 수 있다.

<br>

- The inputs stay in sync because their values are computed from the same state:
  - 입력 값은 동일한 state에서 계산되기 때문에, 동기화를 유지한다.

```react
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
      const celsius = scale === 'f' ? tryConvert(temperature, toCelsius) : temperature;
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
            
            <BoilingVerdict celsius={parseFloat(celsius)} />
         </div>
      );
   }
}
```

[CodePen에서 시도](https://codepen.io/gaearon/pen/WZpxpz?editors=0010)

<br>

- Now, no matter which input you edit, `this.state.temperature` and `this.state.scale` in the `Calculator` get updated.
  - 이제 입력을 편집해도, `Calculator`의 `this.state.temperature`와 `this.state.scale`이 업데이트된다.
- One of the inputs gets the value as is, so any user input is preserved, and the other input value is always recalculated based on it.
  - 입력 중 하나가 그대로 값을 값을 가져오므로, 모든 사용자 입력이 보존되고, 다른 입력 값은 항상 그 값을 기반으로 다시 계산된다.

<br>

- Let's recap what happens when you edit an input:
  - 입력을 편집할 때 무슨 일이 일어나는지 요약해보자.

<br>

1. React calls the function specified as `onChange` on the DOM `<input>`. In our case, this is the `handleChange` method in `TemperatureInput` component.
   - React는 DOM `<input>`에서 `onChange`로 지정된 함수를 호출한다.
   - 여기서는, `TemperatureInput` 컴포넌트의 `handleChange` 메소드이다.
2. The `handleChange` method in the `TemperatureInput` component calls `this.props.onTemperatureChange()` with the new desired value. Its props, including `onTemperatureChange`, were provided by its parent component, the `Calculator`.
   - `TemperatureInput` 컴포넌트의 `handleChange` 메소드는 `this.props.onTemperatureChange()`를 새로운 원하는 값으로 호출한다.
   - `onTemperatureChange`를 포함한 그 props는, 그 부모 컴포넌트인 `Calculator`에 의해서 제공되었다.
3. When it previously rendered, the `Calculator` has specified that `onTemperatureChange` of the Celsius `TemperatureInput` is the `Calculator`'s `handleChange` method, and `onTemperatureChange` of the Fahrenheit `TemperatureInput` is the `Calculator`'s `handleFahrenheitChange` method. So either of these two `Calculator` methods gets called depending on which input we edited.
   - 이전에 렌더링 할 때, `Calculator`는 Celsius `TemperatureInput`의 `onTemperatureChange`가 `Calculator`의 `handleCelsiusChange` 메소드임을 명시했었고, Fahrenheit `TemperatureInput`의 `onTemperatureChange`는 `Calculator`의 `handleFahrenheitChange` 메소드이다.
   - 따라서 이 두 가지 `Calculator` 메소드 중 하나가 편집한 입력에 따라 호출된다.
4. Inside these methods, the `Calculator` component asks React to re-render itself by calling `this.setState()` with the new input value and the current scale of the input we just edited.
   - 이 메소드들 안에서, `Calculator` 컴포넌트는 React에게 새로운 입력 값과 방금 편집한 입력의 현재 scale로 `this.setState()`를 호출함으로써, 스스로를 다시 렌더링하도록 요청한다.
5. React calls the `Calculator` component's `render` method to learn what the UI should look like. The values of both inputs are recomputed based on the current temperature and the active scale. The temperature conversion is performed here.
   - React는 `Calculator` 컴포넌트의 `render` 메소드를 호출해서 UI의 모양을 확인한다.
   - 두 입력 값은 현재 온도와 active scale을 기반으로 계산된다.
   - 온도 변환은 여기서 수행된다.
6. React calls the `render` methods of the individual `TemperatureInput` components with their new props specified by the `Calculator`. It learns what their UI should look like.
   - React는 개별 `TemperatureInput` 컴포넌트의 `render` 메소드를 `Calculator`에서 지정한 새로운 props로 호출한다.
   - 이것은 UI가 어떻게 생겼는지 확인한다.
7. React DOM updates the DOM to match the desired input values. The input we just edited receives its current value, and the other input is updated to the temperature after conversion.
   - React DOM은 원하는 입력 값과 일치하도록 DOM을 업데이트한다.
   - 방금 편집한 입력은 현재 값을 받고, 다른 입력은 변환 후 온도로 업데이트된다.

<br>

- Every update goes through the same steps so the inputs stay in sync.
  - 모든 업데이트는 동일한 단계를 거쳐서 입력이 동기화를 유지한다.

------

<br>

### Lessons Learnd

###### 교훈

<br>

- There should be a single "source of truth" for any data that changes in a React application.
  - React 애플리케이션에서 변경되는 모든 데이터에 대한 단일 "source of truth"가 있어야 한다.
- Usually, the state is first added to the component that needs it for rendering.
  - 일반적으로, state는 렌더링을 위해 필요한 컴포넌트에 첫 번째로 추가된다.
- Then, if other components also need it, you can lift it up to their closest common ancestor.
  - 그런 다음, 다른 컴포넌트에서도 필요하다면, 가장 가까운 공통 조상까지 끌어올릴 수 있다.
- Instead of trying to sync the state between different components, you should rely on the [top-down data flow](https://reactjs.org/docs/state-and-lifecycle.html#the-data-flows-down).
  - 다른 컴포넌트 간에 state를 동기화하려는 대신, 하향식 데이터 흐름에 의존해야 한다.

<br>

- Lifting state involves writing more "boilerplate" code than two-way binding approaches, but as a benefit, it takes less work to find and isolate bugs.
  - state 끌어올리기는 양방향 바인딩 접근 방식 보다 "boilerplate" 코드 작성이 더 많이 포함되지만, 버그를 찾고 격리하는 작업이 줄어드는 이점이 있다.
- Since any state "lives" in some component and that component alone can change it, the surface area for bugs is greatly reduced.
  - 모든 state는 일부 컴포넌트에 "존재"하고 컴포넌트만 변경될 수 있으므로, 버그의 표면이 크게 줄어든다.
- Additionally, you can implement any custom logic to reject or transform user input.
  - 추가적으로, 사용자 입력을 변환하거나 거부하는 모든 사용자 정의 로직을 구현할 수 있다.

<br>

- If something can be derived from either props or state, it probably shouldn't be in the state.
  - props나 state 중에서 파생될 수 있는 것이 있다면, 그것은 state에 있어서는 안 된다.
- For example, instead of storing both `celsiusValue` and `fahrenheitValue`, we store just the last edited `temperature` and its `scale`.
  - 예를 들어, `celsiusValue`와 `fahrenheitValue`를 모두 저장하는 대신, 마지막으로 편집한 `temperature`와 `scale`을 저장한다.
- The value of the other input can always be calculated from them in the `render()` method.
  - 다른 입력 값은 항상 `render()` 메소드에서 계산할 수 있다.
- This lets us clear or apply rounding to the other field without losing any precision in the user input.
  - 이를 통해, 사용자 입력에서 정밀함을 잃지 않고 다른 필드를 clear하거나 적용할 수 있다.

<br>

- When you see something wrong in the UI, you can use [React Developer Tools](https://github.com/facebook/react-devtools) to inspect the props and move up the tree until you find the component responsible for updating the state.
  - UI에서 문제가 발생하면, [React Developer Tools](https://github.com/facebook/react-devtools)를 사용해서 state 업데이트를 담당하는 컴포넌트를 찾을 때까지 props를 검사하고, 트리를 위로 이동할 수 있다.
- This lets you trace the bugs to their source:
  - 버그를 소스로 추적할 수 있다.

![React img](/assets/img/react-official-main concepts-10-01.gif)

<br>