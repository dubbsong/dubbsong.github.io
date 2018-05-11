---
layout: post
title: "nicknameGenerator.js (7kyu)"
categories: codewars
tags: Algorithm Codewars
---

#### 조건문(if) + 메소드(method) 활용 알고리즘 문제

<br>

## problem

Write a function '`nicknameGenerator`'

that takes a string name as an argument

and returns the first 3 or 4 letters as a nickname.

<br>

If the 3rd letter is a consonant(`자음`),

return the first 3 letters.

<br>

If the 3rd letter is a vowel(`모음`),

return `"Error: Name too short"`.

<br>

- Notes:
  - Vowels are "`aeiou`", so discount the letter "`y`".
  - Input will always be a string.
  - Input will always have the first letter capitalised and the rest lowercase.
  - The input can be modified.

<br>

## solution 01

```javascript
function nicknameGenerator(name) {
   if (name.length < 4) {
      return "Error: Name too short";
   } else if ("aeiou".indexOf(name[2].toLowerCase()) !==-1) {
      return name.slice(0, 4);
   } else {
      return name.slice(0, 3);
   }
}


nicknameGenerator('Samuel');	// Sam
nicknameGenerator('Sam');	// Error: Name too short
nicknameGenerator('Gregory');	// Greg
```

> `.indexOf()` 메소드
>
> 일치하는 인덱스를 반환하고, 일치하는 값이 없으면 -1을 반환한다.

<br>

> `.toLowerCase()` 메소드
>
> 모든 영문자를 소문자로 변환한다.

<br>

> `.slice()` 메소드
>
> 문자열의 일부를 추출하면서 새로운 문자열을 반환한다.

<br>

## solution 02

```javascript
function nicknameGenerator(name) {
   if (name.length < 4) {
      return "Error: Name too short";
   } else if (/[aeiou]/.test(name[2])) {
      return name.slice(0, 4);
   } else {
      return name.slice(0, 3);
   }
}


nicknameGenerator('Samuel');	// Sam
nicknameGenerator('Sam');	// Error: Name too short
nicknameGenerator('Gregory');	// Greg
```

> 정규표현식 (RegExp)
>
> `test`: 일치하는 문자열을 검사하고, true나 false를 반환한다.

<br>

## solution 03

```javascript
function nicknameGenerator(name) {
   if (name.length < 4) {
      return "Error: Name too short";
   } else if ('aeiou'.includes(name[2])) {
      return name.substr(0, 4);
   } else {
      return name.substr(0, 3);
   }
}


nicknameGenerator('Samuel');	// Sam
nicknameGenerator('Sam');	// Error: Name too short
nicknameGenerator('Gregory');	// Greg
```

> `.includes()` 메소드
>
> 배열에 특정 요소가 있는지 확인하고, true 또는 false를 반환한다.

<br>

> `.substr()` 메소드
>
> 지정된 위치의 문자부터, 지정된 수만큼의 문자를 반환한다.

<br>