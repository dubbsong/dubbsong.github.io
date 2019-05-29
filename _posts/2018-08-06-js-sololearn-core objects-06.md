---
layout: post
title: "(Core Objects 06) Date 객체"
categories: js
---

###### [SoloLearn](https://www.sololearn.com/) JS 번역

<br>

## setInterval

###### setInterval 메소드

<br>

- The `setInterval()` method calls a function or evaluates an expression at specified intervals (in milliseconds).
  - `setInterval()` 메소드는 지정된 간격(밀리초)으로 함수를 호출하거나 표현식을 평가한다.
- It will continue calling the function until `clearInterval()` is called or the window is closed.
  - `clearInterval()`이 호출되거나 window가 닫힐 때까지 함수를 계속 호출한다.

<br>

- For example:

```js
function myAlert() {
   alert('Hi');
}

setInterval(myAlert, 3000);
```

[코드 실행 확인](https://code.sololearn.com/704/#js)

<br>

- This will call the myAlert function every 3 seconds (1000 ms = 1 second).
  - 위 코드는 myAlert 함수를 3초마다 호출한다.
  - (1000 밀리초 = 1초)

<br>

> Write the `name` of the function without parentheses when passing it into the `setInterval` method.
>
> `setInterval` 메소드에 함수를 전달할 때는, 괄호 없이 함수의 `이름`만 작성한다.

------

<br>

## The Date Object

###### Date 객체

<br>

- The `Date object` enables us to work with dates.
  - `Date 객체`는 날짜를 사용해서 작업할 수 있다.
- A date consists of a year, a month, a day, an hour, a minute, a second, and milliseconds.
  - 날짜는 년, 월, 일, 시, 분, 초, 밀리초로 구성된다.

<br>

- Using `new Date()`, create a new Date object with the `current date and time`.
  - `new Date()`를 사용해서 `현재 날짜와 시간`으로 새로운 Date 객체를 생성한다.

```js
var d = new Date();	// d는 현재 날짜와 시간을 저장한다.
```

<br>

- The other ways to initialize dates allow for the creation of new Date objects from the `specified date and time`.
  - 날짜를 초기화하는 다른 방법을 사용하면, `지정된 날짜와 시간`으로 새로운 Date 객체를 생성할 수 있다.

```js
new Date(milliseconds)
new Date(dateString)
new Date(year, month, day, hours, minutes, seconds, milliseconds)
```

<br>

> JavaScript dates are calculated in milliseconds from 01 January, 1970 00:00:00 Universal Time (UTC).
>
> JavaScript 날짜는 협정 세계 표준시(UTC) 1970 1월 1일 00:00:00부터 밀리초 단위로 계산된다.

> One day contains 86,400,000 millisecond.
>
> 하루는 86,400,000 밀리초를 포함한다.

<br>

- For example:

```js
// 1970년 1월 2일 금요일 00:00:00
var d1 = new Date(86400000);

// 2015년 1월 2일 금요일 10:42:00
var d2 = new Date('January 2, 2015 10:42:00');

// 1988년 5월 11일 토요일 11:42:00
var d3 = new Date(88,5,11,11,42,0,0);
```

<br>

> JavaScript counts months from 0 to 11.
>
> JavaScript는 0에서 11 사이의 달(month)을 계산한다.

> January is 0, and December is 11.
>
> 1월은 0이고, 12월은 11이다.

> Date objects are static, rather than dynamic.
>
> Date 객체는 동적이 아닌 정적이다.

> The computer time is ticking, but Date objects don't change, once created.
>
> 컴퓨터 시계는 똑딱거리지만, Date 객체는 한 번 생성되면 변경되지 않는다.

------

<br>

## Date Methods

###### Date 메소드

<br>

- When a Date object is created, a number of `methods` make it possible to perform operations on it.
  - Date 객체가 생성되면, 여러 `메소드`를 사용해서 작업을 수행할 수 있다.

<br>

- `getFullYear()`: gets the year
  - 년(year)을 가져온다.
- `getMonth()`: gets the month
  - 달(month)을 가져온다.
- `getDate()`: gets day of the month
  - 달(month)의 일(day)을 가져온다.
- `getDay()`: gets the day of the week
  - 주(week)의 일(day)를 가져온다.
- `getHours()`: gets the hour
  - 시(hour)를 가져온다.
- `getMinutes()`: gets the minutes
  - 분(minutes)을 가져온다.
- `getSeconds()` gets the seconds
  - 초(seconds)를 가져온다.
- `getMilliseconds()`: gets the milliseconds
  - 밀리초(milliseconds)를 가져온다.

<br>

- For example:

```js
var d = new Date();
var hours = d.getHours();

document.write(hours);	// hours는 현재 시간과 같다.
```

[코드 실행 확인](https://code.sololearn.com/705/#js)

<br>

- Let's create a program that prints the current time to the browser once every second.
  - 매초 브라우저에 현재 시간을 출력하는 프로그램을 생성해보자.

```js
function printTime() {
   var d = new Date();
   var hours = d.getHours();
   var mins = d.getMinutes();
   var secs = d.getSeconds();
   document.body.innerHTML = hours + ':' + mins + ':' + secs;
}

setInterval(printTime, 1000);	// 매초 현재 시간을 출력한다.
```

[코드 실행 확인](https://code.sololearn.com/706/#js)

<br>

- We declared a function `printTime()`, which gets the current time from the Date object, and prints it to the screen.
  - Date 객체로부터 현재 시간을 가져와 화면에 출력하는 `printTime()` 함수를 선언했다.
- We then called the function once every second, using the `setInterval` method.
  - 그런 다음 `setInterval` 메소드를 사용해서 매초 한 번씩 함수를 호출했다.

<br>

> The `innerHTML` property sets or returns the HTML content of an element.
>
> `innerHTML` 속성은 element의 HTML 내용을 설정하거나 반환한다.

> In our case, we are changing the HTML content of our document's body.
>
> 여기서는, document body의 HTML 내용을 변경한다.

> This overwrites the content every second, instead of printing it repeatedly to the screen.
>
> 이는 반복적으로 화면에 출력하는 대신, 매초 내용을 덮어쓴다.

------

<br>

## QUIZ

- Fill in the blanks to call the function "calc()" every 2 seconds:
  - 2초마다 "calc()" 함수를 호출해라.

```js
setInterval(calc, 2000);
```

<br>

- What information results from creating a Date Object?
  - Date 객체를 생성하면 어떤 정보가 출력되는가?

> `The current date and time`
>
> 현재 날짜와 시간

<br>

- Fill in the blanks to initialize a Date object representing the current date and time:
  - 현재 날짜와 시간을 나타내는 Date 객체를 초기화해라.

```js
var date = new Date();
```

<br>