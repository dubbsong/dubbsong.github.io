---
layout: post
title: "flipNumber.js (7kyu)"
categories: codewars
tags: Algorithm Codewars
---

#### 반복문(while) + 메소드(method) 활용 알고리즘 문제

<br>

## problem

Your job is to return that string in a certain order

that I will explain below:

<br>

> Let's say you start with this: `012345`
>
> The first thing you do is reverse it: `543210`
>
> Then you will take the string from the 1st position and reverse it again: `501234`
>
> Then you will take the string from the 2nd position and reverse it again: `504321`
>
> Then you will take the string from the 3rd position and reverse it again: `504123`

<br>

Continue this pattern until you have done every single position,

and then you will return the string you have created.

<br>

## solution 01

```javascript
function flipNumber(string) {
   string = string.split('');
   let result = [];
   
   while (string.length) {
      result.push(string.reverse().shift());
   }
   return result.join('');
}


flipNumber('012345');		// '504132'
flipNumber('0123456789');	// '9081726354
```

> `.split()` 메소드
>
> 문자열을 부분 문자열로 분할해서, 배열로 반환한다.

<br>

> `.push()` 메소드
>
> 배열의 끝에 새 요소를 추가하고, 새 길이를 반환한다.

<br>

> `.reverse()` 메소드
>
> 배열의 요소 순서를 반전시킨다.

<br>

> `.shift()` 메소드
>
> 배열에서 첫 번째 요소를 제거하고, 제거된 요소를 반환한다.

<br>

## solution 02

```javascript
function flipNumber(string) {
   string = [...string];
   let result = '';
   
   while (string.length > 1) {
      result += string.pop() + string.shift();
   }
   return result + string.join('');
}


flipNumber('012345');		// '504132'
flipNumber('0123456789');	// '9081726354
```

> `.pop()` 메소드
>
> 배열에서 마지막 요소를 제거하고, 제거된 요소를 반환한다.

<br>