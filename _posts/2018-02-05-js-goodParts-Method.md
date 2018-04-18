---
layout: post
title: "JS 핵심 가이드 - 메소드"
categories: javascript
tags: JavaScript
---

###### <자바스크립트 핵심 가이드>, 더글라스 크락포드 저 | 김명신 역

<br>

## CHAPTER 08 메소드

<br>

## 배열

<br>

### array.concat(item...)

- concat 메소드는 자신의 복사본에 인수로 넘어온 값들을 추가한 새로운 배열을 반환한다.
- 인수로 넘어온 값이 배열이면 각각의 요소를 개별적으로 새로운 배열에 추가한다.

```javascript
var a = ['a', 'b', 'c'];
var b = ['x', 'y', 'z'];

var c = a.concat(b, true);	// ['a', 'b', 'c', 'x', 'y', 'z', true]
```

<br>

### array.join(구분자)

- join 메소드는 배열로 문자열을 만든다.
- 기본 구분자는 `,`이다.
- 구분 없이 연결하고 싶은 경우에는 구분자로 빈 문자열을 넘기면 된다.

```javascript
var a = ['a', 'b', 'c'];
a.push('d');

var c = a.join('');	// 'abcd'
```

<br>

### array.pop()

- pop과 push 메소드는 배열을 스택처럼 동작하게 한다.
- pop 메소드는 배열에서 마지막 요소를 제거하고 제거한 요소를 반환한다.
- 만약 빈 배열일 경우 undefined를 반환한다.

```javascript
var a = ['a', 'b', 'c'];
var c = a.pop();

console.log(a);	// ['a', 'b']
console.log(c);	// 'c'
```

<br>

- pop 메소드 구현

```javascript
Array.method('pop', function() {
   return this.splice(this.length - 1, 1)[0];
});
```

<br>

### array.push(item...)

- push 메소드는 인수로 넘어온 항목을 배열의 끝에 추가한다.
- concat 메소드와 다르게 이 메소드는 배열 자체를 수정하여 넘어온 인수 전체를 배열에 추가한다.
- 반환값은 배열의 새로운 length 값이다.

```javascript
var a = ['a', 'b', 'c'];
var b = ['x', 'y', 'z'];

var c = a.push(b, true);

console.log(a);	// ['a', 'b', 'c', ['x', 'y', 'z'], true]
console.log(c);	// 5
```

- push 메소드 구현

```javascript
Array.method('push', function() {
   this.splice.apply(
   	this,
      [this.length, 0].concat(Array.prototype.slice.apply(arguments))
   );
   return this.length;
});
```

<br>

### array.reverse()

- reverse 메소드는 배열 요소의 순서를 반대로 변경한다.
- 반환값은 배열이다.

```javascript
var a = ['a', 'b', 'c'];
var b = a.reverse();

console.log(a);	// ['c', 'b', 'a']
console.log(b);	// ['c', 'b', 'a']
```

<br>

### array.shift()

- Shift 메소드는 배열에서 첫 번째 요소를 제거하고 제거한 요소를 반환한다.
- 빈 배열일 경우 undefined를 반환한다.
- shift는 보통 pop보다 많이 느리다.

```javascript
var a = ['a', 'b', 'c'];

var c = a.shift();

console.log(a);	// ['b', 'c']
console.log(c);	// 'a'
```

<br>

- shift 메소드 구현

```javascript
Array.method('shift', function() {
   return this.splice(0, 1)[0];
});
```

<br>

### array.slice(start, end)

- slice 메소드는 배열의 특정 부분에 대한 복사본을 만든다.
- 복사되는 첫 번째 요소는 매개변수 start에 해당하는 첨자를 갖는 배열 요소이다.
- 그리고 매개변수 end에 해당하는 첨자를 가진 요소 전까지 복사된다.
- end 매개변수는 옵션이며 지정하지 않을 경우 기본값은 배열의 length 속성값이다.
- 만약 시작값이 length 값보다 크거나 같을 경우 빈 배열을 반환한다.
- slice와 splice를 혼동해서는 안 된다. 그리고 문자열의 메소드인 `.slice`와도 구분해야 한다.

```javascript
var a = ['a', 'b', 'c'];
var b = a.slice(0, 1);	// ['a']
var c = a.slice(1);	// ['b', 'c']
var d = a.slice(1, 2);	// ['b']
```

<br>

### array.sort(비교 함수)

- sort 메소드는 배열의 내용을 적절하게 정렬한다.
- 이 메소드는 숫자들의 배열을 제대로 정렬하지 못하는 문제가 있다.

```javascript
var n = [4, 8, 15, 16, 23, 42];
n.sort();	// [15, 16, 23, 4, 42, 8]
```

- 이 메소드는 비교를 하기 전에 배열 요소의 타입을 확인할 정도로 똑똑하지 못하다.
- 그냥 숫자를 문자열로 변경한 후에 비교하기 때문에 원하지 않는 이상한 결과를 보이는 것이다.
- 다행인 것은 비교 함수를 바꿔서 사용할 수 있다는 것이다.

```javascript
n.sort(function(a, b) {
   return a - b;
});

// [4, 8, 15, 16, 23, 42]
```

- 이 비교 함수는 숫자값만을 비교할 수 있고, 문자열은 비교하지 못한다.
- 여러 종류의 기본 데이터 타입을 가진 배열을 정렬하고 싶다면 좀 더 많은 작업이 필요하다.

```javascript
var m = ['aa', 'bb', 'a', 4, 8, 15, 16, 23, 42];
m.sort(function(a, b) {
   if (a === b) {
      return 0;
   }
   if (typeof a === typeof b) {
      return a < b ? -1 : 1;
   }
   return typeof a < typeof b ? -1 : 1;
});

// [4, 8, 15, 16, 23, 42, 'a', 'aa', 'bb']
```

- 만약 대소문자를 구분하지 않는다면 비교 전에 피연산자를 소문자로 변환해야 한다.
- sort 메소드는 안정적이지 않다.

<br>

### array.splice(start, deleteCount, item...)

- splice 메소드는 기존의 배열 요소들을 제거하고 그 부분을 새로운 항목으로 대체한다.
- start 매개변수는 배열에서 위치를 나타내는 수이다.
- deleteCount 매개변수는 시작점부터 삭제할 요소의 수를 나타낸다.
- 이 메소드는 삭제된 요소들을 가진 배열을 반환한다.
- splice의 가장 일반적인 사용은 배열에서 요소들을 삭제할 때이다.
- splice와 slice를 혼동해서는 안 된다.

```javascript
var a = ['a', 'b', 'c'];

var r = a.splice(1, 1, 'ache', 'bug');

console.log(a);	// ['a', 'ache', 'bug', 'c']
console.log(r);	// 'b'
```

<br>

### array.unshift(item...)

- unshift 메소드는 항목들을 배열의 뒤가 아니라 앞에다가 추가한다는 점만 빼고 push 메소드와 같다.
- 이 메소드는 배열의 새로운 length 값을 반환한다.

```javascript
var a = ['a', 'b', 'c'];

var r = a.unshift('?', '@');

console.log(a);	// ['?', '@', 'a', 'b', 'c']
console.log(r);	// 5
```

<br>

- unshift 메소드 구현

```javascript
Array.method('unshift', function() {
   this.splice.apply(this, [0, 0].concat(Array.prototype.slice.apply(arguments)));
   return this.length;
});
```

<br>

## 함수

<br>

### function.apply(thisArg, argArray)

- ​