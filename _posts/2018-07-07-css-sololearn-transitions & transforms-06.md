---
layout: post
title: "(Transitions & Transforms 06) animation 속성"
categories: css
---

###### [SoloLearn](https://www.sololearn.com/) CSS 번역

<br>

# CSS animation Properties

###### animation 속성

------

<br>

<br>

## The animation-name Property

###### animation-name 속성

<br>

- `animation-name` property defines which animation to use.
  - `animation-name` 속성은 사용할 애니메이션을 정의한다.
- In this example, the name of the animation is set to `colorchange`, which matches the defined keyframes.
  - 이 예제에서 애니메이션의 이름은 정의된 keyframes와 일치하는 `colorchange`로 설정된다.

<br>

- CSS:

```css
div {
   animation-name: colorchange;
   animation-duration: 5s;
}

@keyframes colorchange {
   from {
      width: 0px;
   }
   
   to {
      width: 100px;
   }
}
```

[코드 실행 확인](https://code.sololearn.com/631/#css)

<br>

- The `animation-duration` property specifies the duration of the selected animation in seconds.
  - `animation-duration` 속성은 선택된 애니메이션의 지속 시간을 초 단위로 지정한다.

<br>

> If the animation name does not match any keyframe rule, the animation `will not execute`.
>
> 애니메이션 이름이 keyframe 규칙과 일치하지 않으면, 애니메이션이 `실행되지 않는다`.

------

<br>

## Animation Properties

###### animation 속성

<br>

- The `animation-timing-function` specifies the speed curve of an animation.
  - `animation-timing-function`은 애니메이션의 속도 곡선을 지정한다.
- It can have the following values:
  - 다음 값을 가질 수 있다.

<br>

- `ease`: specifies an animation with a slow start, then fast, then end slowly (this is default)
  - 천천히 시작한 다음 빠른 애니메이션을 지정하고, 천천히 끝낸다(기본값).
- `linear`: specifies an animation with the same speed from start to end
  - 처음부터 끝까지 동일한 속도로 애니메이션을 지정한다.
- `ease-in`: specifies an animation with a slow start
  - 느린 시작을 가진 애니메이션을 지정한다.
- `ease-out`: specifies an animation with a slow end
  - 느린 끝을 가진 애니메이션을 지정한다.
- `ease-in-out`: specifies an animation with a slow start and end
  - 느린 시작과 끝을 가진 애니메이션을 지정한다.
- `cubic-bezier(n,n,n,n)`: lets you define your own values in a cubic-bezier function
  - cubic-bezier 함수로 자신만의 값을 정의할 수 있다.

<br>

- CSS:

```css
animation-timing-function: linear;
```

[코드 실행 확인](https://code.sololearn.com/637/#css)

<br>

- `animation-delay`: defines the delay before an animation starts.
  - 애니메이션이 시작되기 전의 delay를 정의한다.

```css
animation-delay: 2s;
```

[코드 실행 확인](https://code.sololearn.com/632/#css)

<br>

> The animation-delay and animation-duration values can be defined in `seconds (s)` or `milliseconds (ms)`.
>
> animation-delay와 animation-duration rkqtdms `초` 또는 `밀리초`로 정의할 수 있다.

------

<br>

## More Animation Properties

###### 더 많은 animation 속성들

<br>

- The `animation-iteration-count` property determines the number of times an animation repeats.
  - `animation-iteration-count` 속성은 애니메이션이 반복되는 횟수를 결정한다.
- For example, you can set the animation to run `5 times`:
  - 예를 들어, 애니메이션을 `5번` 실행하도록 설정할 수 있다.

```css
animation-iteration-count: 5;
```

[코드 실행 확인](https://code.sololearn.com/633/#css)

<br>

- To make the animation repeat `forever`, just use the `infinite` value:
  - 애니메이션을 `영원히` 반복하려면, `infinite` 값을 사용해라.

```css
animation-iteration-count: infinite;
```

[코드 실행 확인](https://code.sololearn.com/634/#css)

<br>

- The `animation-direction` indicates how the keyframe should be applied.
  - `animation-direction`은 keyframe 적용 방법을 나타낸다.

<br>

- `normal`: the default value, which means it plays forward from 0% to 100%
  - 기본값은 0%에서 100%까지 재생된다.
- `reverse`: plays the keyframe in an opposite direction from 100% to 0%
  - 반대 방향인 100%에서 0%로 keyframe을 재생한다.
- `alternate`: the animation first runs forward, then backward, then forward.
  - 애니메이션은 먼저 앞으로, 뒤로, 그리고 앞으로 실행된다.
- `alternate reverse`: the animation first runs backward, then forward, then backward.
  - 애니메이션은 먼저 뒤로, 앞으로, 그리고 뒤로 실행된다.

<br>

> If you use 0 or a negative number for the `animation-iteration-count`, the animation will never start.
>
> 0 또는 음수를 `animation-iteration-count`에 사용하면, 애니메이션이 시작되지 않는다.

------

<br>

## animation Property

###### animation 속성

<br>

- Consider the following example:
  - 다음 예제를 살펴보자.

```css
div {
   animation-name: colorchange;
   animation-duration: 3s;
   animation-timing-function: ease-in;
   animation-delay: 1s;
   animation-iteration-count: infinite;
   animation-direction: reverse;
}
```

[코드 실행 확인](https://code.sololearn.com/635/#css)

<br>

- A single `animation` property can be used to achieve the same result as the above code:
  - 하나의 `animation` 속성을 사용해서, 위 코드와 동일한 결과를 얻을 수 있다.

```css
div {
   animation: colorchange 3s ease-in 1s infinite reverse;
}
```

[코드 실행 확인](https://code.sololearn.com/636/#css)

<br>

> The order in which each property is declared in the shorthand declaration is important and cannot be altered, or the animation will not work properly.
>
> 속기 선언에서 각 속성이 선언된 순서는 중요하다.
>
> 변경할 수 없거나, 애니메이션이 제대로 작동하지 않는다.

------

<br>

## QUIZ

- Fill in the blanks to make the animation complete in 5 seconds:
  - 애니메이션을 5초 내에 완료해라.

```css
-webkit- animation-duration: 5s;
```

<br>

- Fill in the blank to specify a 2-second delay before the animation begins:
  - 애니메이션이 시작되기 전에 2초 delay를 지정해라.

```css
animation-delay: 2s;
```

<br>

- Which property value is used to have the animation repeat forever?
  - 어떤 속성 값을 사용해서 애니메이션을 영원히 반복할 수 있는가?

> `infinite`

<br>

- Add an animation named sizechange, which starts after 2 seconds, runs for 5 seconds, uses the ease function, and loops forever.
  - sizechange라는 애니메이션을 추가해라.
  - 이 애니메이션은 2초 후에 시작되고, 5초 동안 실행되며, ease 함수를 사용하고, 영원히 반복된다.

```css
.test {
   animation-name: sizechange;
   animation-duration: 5s;
   animation-timing-function: ease;
   animation-delay: 2s;
   animation-iteration-count: infinite;
}
```

<br>