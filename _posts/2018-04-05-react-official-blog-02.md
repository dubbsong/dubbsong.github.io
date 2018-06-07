---
layout: post
title: "공식 리액트 블로그 번역 - 02. New in React v0.4: Autobind by Default"
categories: react
tags: react
---

[공식 리액트 블로그 링크](https://reactjs.org/blog/2013/07/02/react-v0-4-autobind-by-default.html)

<br>

## New in React v0.4: Autobind by Default

###### React v0.4의 새로운 기능: Autobind by Default

<br>

###### React v0.4 is very close to completion.

###### React v0.4는 완성에 가장 가깝다.

###### As we finish it off, we'd like to share with you some of the major changes we've made since v0.3.

###### v0.3 이후의 주요 변경 사항을 공유하고자 한다.

###### This is the first of several posts we'll be making over the next week.

###### 이것은 다음 주에 작성하게 될 여러 게시물 중 첫 번째이다.

------

<br>

### What is React.autoBind?

###### React.autoBind란 무엇인가?

<br>

- If you take a look at most of our current examples, you'll see us using `React.autoBind` for event handlers.
  - 현재 예제의 대부분을 살펴본다면, `React.autoBind`를 사용해 이벤트 핸들러를 다루는 것을 볼 수 있다.
- This is used in place of `Function.prototype.bind`.
  - 이것은 `Function.prototype.bind` 대신에 사용된다.
- Remember that in JS, [function calls are late-bound](https://bonsaiden.github.io/JavaScript-Garden/#function.this).
  - JS에서는 [함수 호출이 늦게 바인딩 되는 것](https://bonsaiden.github.io/JavaScript-Garden/#function.this)을 기억해라.
- That means that if you simply pass a function around, the `this` used inside won't necessarily be the `this` you expect.
  - 즉, 단순히 함수를 전달하면, 내부에서 사용되는 `this`가 반드시 예상한 `this`일 수는 없다.
- `Function.prototype.bind` creates a new, properly bound, function so that when called, `this` is exactly what you expect it to be.
  - `Function.prototype.bind`는 올바로 바인딩 된 함수를 생성하고, 호출될 때 예상하는 `this`가 된다.

<br>

- Before we launched React, we would write this:
  - React를 시작하기 전에, 다음과 같이 작성했다.

```react
React.createClass({
   onClick: function(event) {/* do something with this */},
   render: function() {
      return <button onClick={this.onClick.bind(this)} />;
   }
});
```

<br>

- We wrote `React.autoBind` as a way to cache the function creation and save on memory usage.
  - `React.autoBind`를 함수 생성 및 메모리 사용량을 절약하는 방법으로 작성했다.
- Since `render` can get called multiple times, if you used `this.onClick.bind(this)` you would actually create a new function on each pass.
  - `render`가 여러 번 호출될 수 있으므로, `this.onClick.bind(this)`를 사용한다면, 실제로 각 pass에서 새로운 함수가 생성된다.
- With React v0.3 you were able to write this instead:
  - React v0.3을 사용하면 다음과 같이 작성할 수 있었다.

```react
React.createClass({
   onClick: React.autoBind(function(event) {/* do something with this */}),
   render: function() {
      return <button onClick={this.onClick} />;
   }
});
```

------

<br>

### What's Changing in v0.4?

###### v0.4에서 변한 것은 무언인가?

<br>

- After using `React.autoBind` for a few weeks, we realized that there were very few times that we didn't want that behavior.
  - 몇 주 동안 `React.autoBind`를 사용한 후, 그 동작을 원치 않는 횟수가 거의 없다는 것을 깨달았다.
- So we made it the default!
  - 그래서 그것을 기본값으로 만들었다.
- Now all methods defined within `React.createClass` will already be bound to the correct instance.
  - 이제 `React.createClass`에 정의된 모든 메소드가 이미 올바른 인스턴스에 바인드된다.

<br>

- Starting with v0.4 you can just write this:
  - v0.4부터 다음과 같이 작성할 수 있다.

```react
React.createClass({
   onClick: function(event) {/* do something with this */},
   render: function() {
      return <button onClick={this.onClick} />;
   }
});
```

<br>

- For v0.4 we will simply be making `React.autoBind` a no-op - it will just return the function you pass to it.
  - v0.4에서는 `React.autoBind`를 no-op(조종 불능)으로 간단하게 만들 것이다.
  - 그러면 전달된 함수가 그냥 반환될 것이다.
- Most likely you won't have to change your code to account for this change, though we encourage you to update.
  - 대부분의 경우 변경 사항을 반영하도록 코드를 변경할 필요는 없지만, 업데이트하는 것이 좋다.
- We'll publish a migration guide documenting this and other changes that come along with React v0.4.
  - React v0.4와 함께 나온 변경 사항들과 이것을 설명하는 마이그레이션 가이드를 배포할 것이다.

<br>