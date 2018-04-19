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

- apply 메소드는 this에 연결된 객체(thisArg)와 옵션인 인수 배열(argArray)을 넘기면서 함수를 호출한다.
- apply 메소드는 apply 호출 패턴에서 사용한다.

```javascript
Function.method('bind', function(that) {
   // 특정 함수를 that 객체의 메소드처럼 호출하는 함수 반환
   var method = this,
       slice = Array.prototype.slice,
       args = slice.apply(arguments, [i]);
   return function() {
      return method.apply(that, args.concat(slice.apply(arguments, [0])));
   };
});

var x = function() {
   return this.value;
}.bind({value: 666});
alert(x());	/// 666
```

<br>

## 숫자

<br>

### number.toExponential(fractionDigits)

- toExponential 메소드는 숫자를 지수 형태의 문자열로 반환한다.
- 옵션인 fractionDigits 매개변수는 소수점 아래 몇 째 자리까지 표시할 것인지를 지정한다.
- 이 값은 0에서 20 사이의 값이어야 한다.

```javascript
document.writeln(Math.PI.toExponential(0));	// 3e+0
document.writeln(Math.PI.toExponential(2));	// 3.14e+0
document.writeln(Math.PI.toExponential(7));	// 3.1415927e+0
document.writeln(Math.PI.toExponential(16));	// 3.1415926535897930e+0
document.writeln(Math.PI.toExponential());	// 3.141592653589793e+0
```

<br>

### number.toFixed(fractionDigits)

- toFixed 메소드는 숫자를 고정 소수점 형태로 반환한다.
- 옵션인 fractionDigits 매개변수는 소수점 아래 몇 째 자리까지 표시할 것인지를 지정한다.
- 이 값은 0에서 20 사이의 값이어야 하며 기본값은 0이다.

```javascript
document.writeln(Math.PI.toFixed(0));	// 3
document.writeln(Math.PI.toFixed(2));	// 3.14
document.writeln(Math.PI.toFixed(7));	// 3.1415927
document.writeln(Math.PI.toFixed(16));	// 3.1415926535897930
document.writeln(Math.PI.toFixed());	// 3
```

<br>

### number.toPrecision(precision)

- toPrecision 메소드는 숫자를 10진수 형태의 문자열로 반환한다.
- 옵션인 precision 매개변수는 반환되는 문자열에 포함된 숫자의 개수이다.
- 이 값은 1에서 21 사이이다.

```javascript
document.writeln(Math.PI.toPrecision(2));	// 3.1
document.writeln(Math.PI.toPrecision(7));	// 3.141593
document.writeln(Math.PI.toPrecision(16));	// 3.141592653589793
document.writeln(Math.PI.toPrecision());	// 3.141592653589793
```

<br>

### number.toString(radix)

- toString 메소드는 숫자를 문자열로 변환한다.
- 옵션인 radix 매개변수는 기수(또는 진법)를 지정한다.
- 이 값은 2에서 36 사이의 값이어야 한다.
- radix의 기본값은 10이다.

```javascript
document.writeln(Math.PI.toString(2));	// 11.001001000011111101101010100010001000010110100011
document.writeln(Math.PI.toString(8));	// 3.1103755242102643
document.writeln(Math.PI.toString(16));	// 3.243f6a8885a3
document.writeln(Math.PI.toString());	// 3.141592653589793
```

<br>

## 객체

<br>

### object.hasOwnProperty(name)

- hasOwnProperty 메소드는 객체가 매개변수 name과 같은 이름의 속성이 있으면 true를 반환하고, 그렇지 않으면 false를 반환한다.
- 해당 이름이 프로토타입 체인 상에 있는지는 확인하지 않는다.
- 이 메소드는 name의 값이 hasOwnProperty일 경우에는 무용지물이다.

```javascript
var a = {member: true};
var b = Object.create(a);
var t = a.hasOwnProperty('member');	// true
var u = b.hasOwnProperty('member');	// false
var v = b.member;			// true
```

<br>

## 정규표현식 객체 (RegExp)

<br>

### regexp.exec(string)

- exec 메소드는 정규표현식을 사용하는 메소드들 중에서 가장 강력한(가장 느리기도 한) 메소드이다.
- 이 메소드는 regexp를 string에 적용해서 일치하는 경우 배열을 반환한다.

<br>

### regexp.test(string)

- test 메소드는 정규표현식을 사용하는 메소드 가운데 가장 간단하고 가장 빠르다.
- regexp가 문자열에 일치하면 true를 반환하고, 그렇지 않으면 false를 반환한다.
- 이 메소드와 g 플래그는 같이 사용해서는 안 된다.

```javascript
var b = /&.+;/.test('frank &amp; beans');	// true
```

<br>

## 문자열

<br>

### string.charAt(pos)

- charAt 메소드는 문자열에서 pos 위치에 있는 문자를 반환한다.
- pos 값이 0보다 작거나 문자열의 .length 값보다 크거나 같으면 빈 문자열을 반환한다.
- JS는 문자 데이터 타입이 없다. 그러므로 이 메소드의 결과는 문자 하나지만 문자열이다.

```javascript
var name = 'Curly';
var initial = name.charAt(0);	// C
```

<br>

### string.charCodeAt(pos)

- charCodeAt 메소드는 charAt과 같은데, 다만 문자열 대신 해당 위치 문자의 코드를 반환하는 것이 다르다.
- pos의 값이 0보다 작거나 문자열의 .length 값보다 크거나 같으면 NaN을 반환한다.

```javascript
var name = 'Curly';
var initial = name.charCodeAt(0);	// 67
```

<br>

### string.concat(string...)

- ​

























