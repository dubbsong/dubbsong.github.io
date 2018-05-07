---
layout: post
title: "러닝 리액트(Learning React) - 5. JSX"
categories: react
tags: react
---

###### \<Learning React>, Alex Banks, Eve Porcello 저 | 오현석 역

<br>

## CHAPTER 05 JSX를 사용하는 리액트

- React.createElement를 번거롭게 입력하는 대신 사용할 수 있는 대안이 JSX이다.
- JSX는 JS의 확장으로 HTML과 비슷한 구문을 사용해 리액트 엘리먼트를 정의할 수 있게 해준다.

<br>

### JSX로 리액트 엘리먼트 정의하기

- JSX는 애트리뷰트가 붙은 복잡한 DOM 트리를 작성할 수 있는 간편한 문법을 제공한다.
- JSX에서는 태그를 사용해 엘리먼트의 타입을 지정한다. 태그의 애트리뷰트는 프로퍼티를 표현한다. 여는 태그와 닫는 태그 사이에 엘리먼트의 자식을 넣는다.
- 배열을 컴포넌트로 넘길 때는 중괄호 {}로 감싸야 한다. 중괄호로 감싼 코드를 JS 식이라고 부른다.
- 컴포넌트에 프로퍼티 값으로 JS 값을 넘기려면 JS 식을 사용해야 한다.

<br>

#### JSX 팁

- 대부분의 문법은 HTML과 비슷하다.

<br>

###### 내포된 컴포넌트

- JSX에서는 다른 컴포넌트의 자식으로 컴포넌트를 추가할 수 있다.

```react
// Ingredient 컴포넌트를 3개 내포하는 IngredientsList

<IngredientsList>
	<Ingredient />
   <Ingredient />
   <Ingredient />
</IngredientsList>
```

<br>

###### className

- JS에서는 class가 예약어이므로 class 애트리뷰트 대신 className을 사용한다.

```react
<h1 className="fnacy">Baked Salmon</h1>
```

<br>

###### JS 식

- JS 식을 중괄호로 감싸면 중괄호 안의 식을 평가해서 결과값을 돌려주어야 한다는 뜻이다.

```react
<h1>{this.props.title}</h1>
```

<br>

###### 평가

- 중괄호 안에 들어간 JS 코드는 그 값을 평가받는다.
- 이는 덧셈이나 문자열 이어붙임 등의 여러 연산이 일어날 수 있다는 뜻이다.
- 이는 JS 식 안에 함수 호출 구문이 있다면 그 함수가 호출된다는 뜻이기도 하다.

```react
<h1>{"Hello" + this.props.title}</h1>

<h1>{this.props.title.toLowerCase().replace}</h1>

function appendTitle({this.props.title}) {
	console.log(`${this.props.title} is great`)
}
```

<br>

###### 배열을 JSX로 매핑

- JSX는 JS이므로 JS 함수 안에서 JSX를 직접 사용할 수 있다.

```react
<ul>
	{this.props.ingredients.map((ingredient, i) =>
		<li key={i}>{ingredient}</li>
	)}
</ul>
```

<br>

### 바벨

- JS는 인터프리터 언어라서 브라우저가 코드 텍스트를 해석하기 때문에 컴파일할 필요가 없다.
- 하지만 모든 브라우저가 ES6나 ES7 문법을 지원하지는 않는다.
- 그리고 어떤 브라우저도 JSX를 지원하지 않는다.
- 우리는 JSX와 함께 최신 JS 기능을 활용하고 싶기 때문에 작성한 소스 코드를 브라우저가 해석할 수 있는 코드로 변환해줄 수단이 필요하다.
- 이런 변환 과정을 `트랜스파일링`이라고 부르며 `바벨`이 그런 일을 해준다.
- 바벨 프로젝트는 처음에 6to5라고 불렸다. 6to5는 ES6 문법으로 작성된 코드를 ES5 문법에 맞는 코드로 변환해주는 도구였다. 프로젝트가 커짐에 따라 이후 발생한 ECMAScript의 변화를 모두 지원하는 플랫폼 역할을 하는 것으로 목표를 재설정했다.

<br>

### JSX 작성

- JSX는 코드에서 리액트 엘리먼트를 멋지고 깔끔하게 기술할 수 있게 해주며, 작성자 스스로 볼 때도 이해하기 쉽다.
- JSX의 단점은 브라우저가 JSX를 해석하지 못한다는 것이다. 따라서 JSX를 순수 리액트로 변환해야 한다.

<br>

### 웹팩 소개

- 웹팩은 모듈 번들러(module bundler)로 알려져 있다.
- 모듈 번들러는 여러 파일(JS, CSS, JSX, ES6 등)을 받아서 하나의 파일로 묶어준다.
- 모듈을 하나로 묶어서 얻는 두 가지 이익은 **모듈성(modularity)**과 **네트워크 성능(network performance)**이다.
- 모듈성은 소스 코드를 작업하기 쉽게 여러 부분 또는 모듈로 나눠서 다룰 수 있게 해준다. 특히 팀 환경에서는 모듈성이 중요하다.
- 트랜스파일링 외에 웹팩이 처리할 수 있는 일
  - 코드 분리
  - 코드 축소
  - 특징 켜고 끄기
  - HMR: 소스 코드가 바뀌는지 감지해서 변경된 모듈만 즉시 갱신해준다.

<br>

###### 웹팩 로더

- **로더(loader)**는 빌드 과정에서 코드를 변환하는 방식을 처리하는 기능이다.
- 애플리케이션이 ES6, JSX, 그 외에 브라우저가 이해할 수 없는 다른 언어 등을 사용한다면 webpack.config.js에 필요한 로더를 지정해서 애플리케이션 코드를 브라우저가 이해할 수 있는 코드로 변환하게 만들어야 한다.

<br>

###### 웹팩 의존관계 설치

- 웹팩으로 정적인 빌드 프로세스를 만들려면 몇몇 모듈을 설치해야 한다.
- `$ sudo npm install -g webpack`
- 웹팩은 바벨을 사용해 JSX와 ES6 코드를 모든 브라우저에서 사용할 수 있는 JS 코드로 트랜스파일링한다.
- 바벨을 설치하면서 작업에 필요한 몇 가지 프리셋을 함께 설치해야 한다.
- `$ npm install babel-core babel-loader babel-preset-env babel-preset-react babel-preset-state-0 --save-dev`
- `$ npm install react react-dom --save`

<br>

###### 웹팩 설정

- 모듈화한 앱이 작동하게 만들려면 소스 코드를 어떻게 하나의 번들 파일로 만들 수 있는지 웹팩에 알려주어야 한다.
- 웹팩의 디폴트 설정 파일 이름은 항상 webpack.config.js이다.
- 앱의 시작 파일은 index.js이다. index.js는 React, ReactDOM, Menu.js 파일을 임포트한다. 이는 브라우저에서 가장 먼저 실행해야 하는 부분이다. 웹팩은 import 문을 발견할 때마다 파일시스템에서 해당 모듈을 찾아 번들에 포함시켜준다.
- 웹팩은 임포트 트리를 쫓아가면서 필요한 모듈을 모두 번들에 넣어준다.
- 대부분의 오류는 임포트 참조가 잘못된 경우에 발생한다.
- 웹팩 오류를 디버깅할 때에는 import 문에 사용한 파일 이름과 경로를 자세히 살펴봐야 한다.

<br>

###### 번들 로딩

- 웹팩은 번들을 dist 폴더에 넣는다. 이 폴더에는 웹 서버에서 번들을 실행할 때 필요한 파일이 들어 있다.

<br>

###### 소스 매핑

- 코드를 하나의 번들 파일로 만들면 브라우저에서 앱을 디버깅할 때 약간 곤란해진다. 이런 문제는 소스 맵을 제공하여 해결할 수 있다. 소스 맵은 번들과 원래 소스 파일을 연결해주는 파일이다.
- 웹팩에서는 webpack.config.js 파일에 몇 줄을 추가하면 이런 소스 매핑을 추가할 수 있다.

<br>

###### 번들 최적화

- 출력 번들도 여전히 단순한 텍스트 파일이다. 따라서 그 파일에 들어 있는 텍스트의 양을 줄이면 파일 크기가 줄고 그에 따라 HTTP 전송을 통한 번들 로딩도 더 빨라진다.
- JS 파일의 크기를 줄이는 작업을 **축소(minifying)** 또는 **난독화(uglifying)**라고 부른다.
- 웹팩에는 번들을 난독화하는 내장 플러그인이 있다. 난독화 플러그인을 사용하려면 웹팩을 로컬에 설치해야 한다.
- `$ npm install webpack --save-dev`

<br>

###### create-react-app

- 리액트 팀은 자동으로 리액트 프로젝트를 생성해주는 create-react-app이라는 명령줄 도구를 만들었다.
- create-react-app은 개발자가 직접 웹팩, 바벨, ESLint 등 여러 도구의 설정을 손보지 않아도 빠르게 리액트 프로젝트를 시작할 수 있게 해준다.
- `$ npm install -g create-react-app`
- `$ create-react-app my-react-project`
- 이 명령은 리액트 프로젝트를 my-react-project 디렉토리에 만들면서 React, ReactDOM, react-scripts에 대한 의존관계를 설정해준다.
- App.js 파일이 루트 컴포넌트이므로 그 파일을 열어서 다른 컴포넌트 파일을 임포트하면 된다.
- yarn의 경우에는 yarn build를 해라. 이 명령은 트랜스파일링과 축소를 거친 프로덕션에 사용할 수 있는 번들을 만든다.

<br>