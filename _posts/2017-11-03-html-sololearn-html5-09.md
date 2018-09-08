---
layout: post
title: "09. 웹 저장소 API (HTML5)"
categories: html
---

###### [SoloLearn](https://www.sololearn.com/) HTML 번역

<br>

# HTML Web Storage API

###### HTML 웹 저장소 API

------

<br>

<br>

## HTML5 Web Storage

###### HTML5 웹 저장소

<br>

- With HTML5 web storage, websites can store data on a user's local computer.
  - HTML5 웹 저장소를 사용하면, 웹사이트에서 사용자의 로컬 컴퓨터에 데이터를 저장할 수 있다.
- Before HTML5, we had to use `JavaScript cookies` to achieve this functionality.
  - HTML5 이전에는 `JavaScript cookies`를 사용해서 이 기능을 구현해야 했다.

<br>

#### The Advantages of Web Storage

###### 웹 저장소의 장점

<br>

- More secure
- Faster
- Stores a larger amount of data
- Stored data is not sent with every server request

<br>

> Local storage is per domain.
>
> 로컬 저장소는 도메인마다 있다.

> All pages from one domain can store and access the same data.
>
> 한 도메인의 모든 페이지는 동일한 데이터를 저장하고 액세스 할 수 있다.

------

<br>

## Types of Web Storage Objects

###### 웹 저장 객체 type

<br>

- There are two types of web storage objects:
  - 웹 저장 객체에는 두 가지 type이 있다.

<br>

1. `sessionStorage()`
2. `localStorage()`

<br>

#### Local vs. Session

###### 로컬 저장소 vs. 세션 저장소

<br>

- Session Storage is destroyed once the user closes the browser.
  - 사용자가 브라우저를 닫으면 Session Storage가 파괴된다.
- Local Storage stores data with no expiration date.
  - Local Storage는 만료 날짜가 없는 데이터를 저장한다.

<br>

> You need to be familiar with basic JavaScript in order to understand and use the API.
>
> API를 이해하고 사용하려면, 기본 JavaScript에 익숙해야 한다.

------

<br>

## Working with Values

###### 값을 사용한 작업

<br>

- The syntax for web storage for both local and session storage is very simple and similar.
  - 로컬 저장소와 세션 저장소 모두를 위한 웹 저장소의 구문은 매우 간단하고 비슷하다.
- The data is stored as key/value pairs.
  - 데이터는 키/값 쌍으로 저장된다.

<br>

- Storing a Value:
  - 값 저장

```html
localStorage.setItem("key1", "value1");
```

<br>

- Getting a Value:
  - 값 얻기

```html
// this will print the value

alert(localStorage.getItem("key1"));
```

<br>

- Removing a Value:
  - 값 제거

```html
localStorage.removeItem("key1");
```

<br>

- Removing All Values:
  - 모든 값 제거

```html
localStorage.clear();
```

<br>

> The same syntax applies to the session storage, with one difference: instead of localStorage, sessionStorage is used.
>
> 동일한 구문이 세션 저장소에 적용되지만, 단 하나의 차이점이 있다.
>
> localStorage 대신에 sessionStorage가 사용된다.

------

<br>

## QUIZ

- Before HTML5, application data was stored in:
  - HTML5 이전에는 애플리케이션 데이터가 다음 위치에 저장되었다.

> `cookies`

<br>

- What are the two types of HTML5 web storage?
  - HTML5 웹 저장소의 두 가지 type은 무엇인가?
  - Select all that apply

> [ ] htmlStorage
>
> [ ] userStorage
>
> [ ] `sessionStorage`
>
> [ ] `localStorage`

<br>

- Drag and drop from the options below to clear all values stored in the localStorage.
  - localStorage에 저장된 모든 값을 지우기 위해서, 아래 옵션에서 드래그 앤 드랍해라.
- Then store "a" using the key "b".
  - 그런 다음 "b" 키를 사용해서 "a"를 저장해라.

```html
localStorage.clear();
localStorage.setItem("b", "a");
```

<br>