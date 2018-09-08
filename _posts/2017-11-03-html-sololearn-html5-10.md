---
layout: post
title: "10. Geolocation API (HTML5)"
categories: html
---

###### [SoloLearn](https://www.sololearn.com/) HTML 번역

<br>

# HTML Geolocation API

###### HTML Geolocation API

------

<br>

<br>

## What is the Geolocation API?

###### Geolocation API가 무엇인가?

<br>

- In HTML5, the Geolocation API is used to obtain the user's geographical location.
  - HTML5에서 Geolocation API는 사용자의 지리적 위치를 가져오는 데 사용된다.

<br>

- Since this can compromise user privacy, the option is not available unless the user approves it.
  - 이로 인해 사용자 개인 정보가 손상될 수 있으므로, 사용자가 승인하지 않으면 옵션을 사용할 수 없다.

<br>

> Geolocation is much more accurate for devices with GPS, like smartphones and the like.
>
> Geolocation은 스마트폰과 같은 GPS가 있는 기기에서 더 정확하다.

------

<br>

## Using HTML Geolocation

###### HTML Geolocation 사용

<br>

- The Geolocation API's main method is getCurrentPosition, which retrieves the current geographic location of the user's device.
  - Geolocation API의 주요 메소드는 getCurrentPosition이고, 이는 사용자 기기의 현재 지리적 위치를 검색한다.

```html
navigator.geolocation.getCurrentPosition();
```

<br>

#### Parameters:

###### 매개변수

<br>

- `showLocation (mandatory)`: Defines the callback method that retrieves location information.
  - 위치 정보를 검색하는 콜백 메소드를 정의한다.
- `ErrorHandler (optional)`: Defines the callback method that is invoked when an error occurs in processing the asynchronous call.
  - 비동기 호출 처리 중 에러가 발생할 때 호출되는 콜백 메소드를 정의한다.
- `Options (optional)`: Defines a set of options for retrieving the location information.
  - 위치 정보를 검색하기 위한 옵션 세트를 정의한다.

<br>

> You need to be familiar with basic JavaScript in order to understand and use the API.
>
> API를 이해하고 사용하려면 기본 JavaScript에 익숙해야 한다.

------

<br>

## Presenting Data

###### 데이터 제출

<br>

- User location can be presented in two ways: `Geodetic` and `Civic`.
  - 사용자 위치는 두 가지 방법으로 표현될 수 있다: `Geodetic`과 `Civic`.

<br>

1. The geodetic way to describe position refers directly to latitude and longitude.
   - 위치를 나타내는 geodetic 방법은 위도와 경도를 직접 참조한다.
2. The civic representation of location data is presented in a format that is more easily read and understood by the average person.
   - 위치 데이터의 civic 표현은 일반인이 보다 쉽게 읽고 이해할 수 있는 format으로 제공된다.

<br>

- Each parameter has both a geodetic and a civic representation:
  - 각 매개변수에는 geodetic과 civic 표현이 있다.

![sololearn img](/assets/img/sololearn-html-html5-10-01.png)

<br>

> The getCurrentPosition() method returns an object if it is successful.
>
> 성공하면, getCurrentPosition() 메소드가 객체를 리턴한다.

> The latitude, longitude, and accuracy properties are always returned.
>
> 위도, 경도, 정확도 property는 항상 반환된다.

------

<br>

## QUIZ

- With the Geolocation API, you can obtain...
  - Geolocation API를 사용하면 ...을 얻을 수 있다.

> [ ] ...browser version
>
> [ ] ...a map of the world
>
> [ ] ...local storage
>
> [ ] `...user location`

<br>

- Which choice is the mandatory parameter of the getCurrentPosition() method?
  - getCurrentPosition() 메소드의 필수 매개변수는 어떤 것인가?

> [ ] `showLocation`
>
> [ ] options
>
> [ ] errorHandler

<br>

- What are the two known ways to present location specific data?
  - 위치 특정 데이터를 표시하는 두 가지 알려진 방법은 무엇인가?

> [ ] Yahoo
>
> [ ] `Geodetic`
>
> [ ] Bing
>
> [ ] `Civic`

<br>