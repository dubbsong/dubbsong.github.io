---
layout: post
title: "accum.js (7kyu)"
categories: codewars
tags: Algorithm Codewars
---

#### 반복문(for loop) + 메소드(method) 활용 알고리즘 문제

<br>

## problem

This time no story, no theory.

<br>

The examples below show you

how to write function '`accum`':

> Examples
>
> accum('abcd');	// A-Bb-Ccc-Dddd
>
> accum('cwAt');	// C-Ww-Aaa-Tttt

<br>

## solution 01

```javascript
fuction accum(string) {
   let result = [];
   
   for (let i = 0; i < string.length; i++) {
      result.push(string.charAt(i).toUpperCase() + string.charAt(i).toLowerCase().repeat(i));
   }
   return result.join('-');
}


accum('ssup');	// S-Ss-Uuu-Pppp
accum('sSuP');	// S-Ss-Uuu-Pppp
```

> `.charAt(i)` 메소드
>
> 지정한 인덱스에서 문자를 반환한다.

<br>

## solution 02

```javascript
fuction accum(string) {
   return string.split('').map((element, index) => element.toUpperCase() + element.toLowerCase().repeat(index)).join('-');
}


accum('ssup');	// S-Ss-Uuu-Pppp
accum('sSuP');	// S-Ss-Uuu-Pppp
```

> `.map()` 메소드
>
> 배열 내 모든 요소 각각에 대하여
>
> 제공된 함수(callback)를 호출하고,
>
> 그 결과를 모아서 새로운 배열을 반환한다.

<br>

## solution 03

```javascript
fuction accum(string) {
   return [...string].map((element, index) => {
      return element.toUpperCase() + element.toLowerCase().repeat(index);
   }).join('-');
}


accum('ssup');	// S-Ss-Uuu-Pppp
accum('sSuP');	// S-Ss-Uuu-Pppp
```

<br>

## solution 04

```javascript
fuction accum(string) {
   let result = string[0].toUpperCase();
   
   for (let i = 1; i < string.length; i++) {
      result += '-';
      
      for (let j = 0; j <= i; j++) {
         result += j === 0
         	? string[i].toUpperCase()
         	: string[i].toLowerCase();
      }
   }
   return result;
}


accum('ssup');	// S-Ss-Uuu-Pppp
accum('sSuP');	// S-Ss-Uuu-Pppp
```

<br>