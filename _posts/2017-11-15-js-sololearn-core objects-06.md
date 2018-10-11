---
layout: post
title: "(Core Objects 06) Date 객체"
categories: js
---

###### [SoloLearn](https://www.sololearn.com/) JS 번역

<br>

# JavaScript Date Object

###### Date 객체

------

<br>

<br>

## setInterval

###### setInterval 메소드

<br>

- The `setInterval()` method calls a function or evaluates an expression at specified intervals (in milliseconds).
  - `setInterval()` 메소드는 지정된 간격(밀리초)으로 함수를 호출하거나, 표현식을 평가한다.
- It will continue calling the function until `clearInterval()` is called or the window is closed.
  - `clearInterval()`이 호출되거나, window가 닫힐 때까지 함수를 계속 호출한다.

<br>

- For example:

```js
function myAlert() {
   alert("Hi");
}

setInterval(myAlert, 3000);
```

[코드 실행 확인](https://code.sololearn.com/704/#js)

<br>

- This will call the myAlert function every 3 seconds (1000 ms = 1 second).
  - myAlert 함수가 3초마다 호출된다.
  - (1000밀리초 = 1초)

<br>

> Write the `name` of the function without parentheses when passing it into the `setInterval` method.
>
> `setInterval` 메소드에 전달할 때는 괄호 없이 함수의 `이름`을 쓴다.

------

<br>

## The Date Object

###### Date 객체

<br>

- The `Date object` enables to work with dates.
  - `Date 객체`를 사용하면 날짜를 사용해서 작업할 수 있다.
- A date consists of a year, a month, a day, an hour, a minute, a second, and milliseconds.
  - 날짜는 년, 월, 일, 시, 분, 초, 밀리초로 구성된다.

<br>

- Using `new Date()`, create a new date object with the `current date and time`.
  - `new Date()`를 사용해서 `현재 날짜와 시간`으로 새 date 객체를 생성한다.

```js
var d = new Date();	// d는 현재 날짜와 시간을 저장한다
```

<br>

- The other ways to initialize dates allow for the creation of new date objects from the `specified data and time`.
  - 날짜를 초기화하는 다른 방법을 사용하면, `지정된 날짜와 시간`에서 새 date 객체를 생성할 수 있다.

```js
new Date(milliseconds)
new Date(dateString)
new Date(year, month, day, hours, minutes, seconds, milliseconds)
```

<br>

> JavaScript dates are calculated in milliseconds from 01 January, 1970 00:00:00 Universal Time (UTC).
>
> JavaScript 날짜는 1970년 1월 1일 00:00:00부터 세계 표준시(UTC)의 밀리초 단위로 계산된다.

> One day contains 86,400,000 millisecond.
>
> 하루는 86,400,000 밀리초를 포함한다.

<br>

- For example:

```js
// 1970년 1월 2일 금요일 00:00:00
var d1 = new Date(86400000);

// 2015sus 1월 2일 금요일 10:42:00
var d2 = new Date("January 2, 2015 10:42:00");

// 1988년 6월 11일 토요일 11:42:00
var d3 = new Date(88, 5, 11, 11, 42, 0, 0);
```

<br>

> JavaScript counts months from 0 to 11.
>
> JavaScript는 0에서 11까지의 월을 계산한다.

> January is 0, and December is 11.
>
> 1월은 0이고, 12월은 11이다.

> Date objects are static, rather than dynamic.
>
> Date 객체는 동적이 아니라, 정적이다.

> The computer time is ticking, but date objects don't change, once created.
>
> 컴퓨터 시간은 똑딱거리지만, date 객체는 일단 생성되면 변경되지 않는다.

------

<br>

## Date Methods

###### Date 메소드

<br>

- When a `Date object` is created, a number of `methods` make it possible to perform operations on it.
  - `Date 객체`가 생성되면, 여러 `메소드`를 사용해서 작업을 수행할 수 있다.

![img](/assets/img/js-sololearn-core objects-06-01.png)

<br>

- For example:

```js
var d = new Date();
var hours = d.getHours();

document.write(hours);	// 시간은 현재 시간과 같다
```

[코드 실행 확인](https://code.sololearn.com/705/#js)

<br>

- Let's create a program that prints the current time to the browser once every second.
  - 매초마다 브라우저에 현재 시간을 출력하는 프로그램을 생성해보자.

```js
function printTime() {
   var d = new Date();
   var hours = d.getHours();
   var mins = d.getMinutes();
   var secs = d.getSeconds();
   document.body.innerHTML = hours + ":" + mins + ":" + secs;
}

setInterval(printTime, 1000);
```

[코드 실행 확인](https://code.sololearn.com/706/#js)

<br>

- We declared a function `printTime()`, which gets the current time from the date object, and prints it to the screen.
  - date 객체로부터 현재 시간을 가져와서 화면에 출력하는 `printTime()` 함수를 선언했다.
- We then called the function once every second, using the `setInterval` method.
  - 그런 다음 `setInterval` 메소드를 사용해서 매초마다 한 번씩 함수를 호출했다.

<br>

> The `innerHTML` property sets or returns the HTML content of an element.
>
> `innerHTML` 속성은 element의 HTML content를 설정하거나 반환한다.

> In our case, we are changing the HTML content of our document's body.
>
> 여기에서는, 문서 내 body의 HTML content를 변경하고 있다.

> This overwrites the content every second, instead of printing it repeatedly to the screen.
>
> 이렇게 하면 반복적으로 화면에 출력하는 대신, 매초 content를 덮어쓴다.

------

<br>

## QUIZ

- Fill in the blanks to call the function "calc()" every 2 seconds:
  - 2초마다 "calc()" 함수를 호출해라.

> `setInterval(calc, 2000);`

<br>

- What information results from creating a Date Object?
  - Date 객체를 생성하면 어떤 정보가 생성되는가?

> `The current date and time`
>
> 현재 날짜와 시간

<br>

- Fill in the blanks to initialize a date object representing the current date and time:
  - 현재 날짜와 시간을 나타내는 date 객체를 초기화해라.

> `var date = new Date();`

<br>
