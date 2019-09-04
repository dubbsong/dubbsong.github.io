---
layout: post
title: "(Official VueJS 05) 템플릿"
categories: dev
tags: vue
---

###### [Vue.js](https://kr.vuejs.org/index.html) 참조

<br>

## 보간법 (Interpolation)

<br>

#### 문자열

- 데이터 바인딩의 가장 기본 형태는, `Mustache`(이중 중괄호) 구문을 사용한 텍스트 보간이다.

```html
<span>메시지: {{ msg }}</span>
```

<br>

#### 원시 HTML

- 이중 중괄호(mustache)는 HTML이 아닌 일반 텍스트로 데이터를 해석한다.
- 실제 HTML을 출력하려면, `v-html` 디렉티브를 사용해야 한다.

```html
<p>Using mustaches: {{ rawHtml }}</p>
<p>Using v-html directive: <span v-html="rawHtml"></span></p>
```

> **Note:**
>
> 임의의 HTML을 동적으로 렌더링하면 xss 취약점으로 쉽게 이어질 수 있다.
>
> 신뢰할 수 있는 컨텐츠에서만 HTML 보간을 사용하고, 사용자가 제공한 컨텐츠에는 `절대` 사용하면 안 된다.

<br>

#### JS 표현식 사용

- VueJS는 모든 데이터 바인딩 내에서 JS 표현식의 모든 기능을 지원한다.

```html
{{ number + 1 }}

{{ ok ? 'Yes' : 'No' }}

{{ message.split('').rever().join('') }}

<div v-bind:id="'list-' + id"></div>
```

<br>

<br>

## 디렉티브

- 디렉티브는 `v-` 접두사가 있는 특수 속성이다.
- 디렉티브 속성 값은 `단일 JS 표현식`이 된다.
  - `v-for`는 예외이다.
- 디렉티브의 역할은, 표현식의 값이 변경될 때 사이드이펙트를 반응적으로 DOM에 적용하는 것이다.

<br>

#### 전달인자

- 일부 디렉티브는 콜론(:)으로 표시되는 `전달인자`를 사용할 수 있다.
- `v-bind` 디렉티브는 반응적으로 HTML 속성을 갱신하는 데 사용된다.
- `v-on` 디렉티브는 DOM 이벤트를 수신한다.

<br>

#### 수식어

- 수식어는 점으로 표시되는 특수 접미사이다.
- 디렉티브를 특별한 방법으로 바인딩 해야 함을 나타낸다.

<br>

#### 약어

- `v-` 접두사는 템플릿의 Vue 특정 속성을 식별하기 위한 시각적인 신호 역할을 한다.
- 가장 자주 사용되는 `v-bind`와 `v-on`에 대해서만 특별한 약어를 제공한다.

<br>

###### `v-bind`의 약어 `:`

```html
<!-- 전체 문법 -->
<a v-bind:href="url"> ... </a>

<!-- 약어 -->
<a :href="url"> ... </a>
```

<br>

###### `v-on`의 약어 `@`

```html
<!-- 전체 문법 -->
<a v-on:click="doSomething"> ... </a>

<!-- 약어 -->
<a @click="doSomething"> ... </a>
```

<br>

<br>