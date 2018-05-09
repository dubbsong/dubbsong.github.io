---
layout: post
title: "counterEffect.js (7kyu)"
categories: codewars
tags: Algorithm Codewars
---

#### 반복문(for loop) + 메소드(method) 활용 알고리즘 문제

<br>

## problem

You have decided to create a function

that will produce a multi-dimensional array

out of the hit count value.

<br>

Each inner dimension of the array

represents an individual digit in the hit count,

and will include all numbers that come before it,

going back to 0.

<br>

> Rules

> The function will take one argument
>
> which will be a four character 'string' representing hit count.

> The function must return a multi-dimensional array
>
> containing four inner arrays.

> The final value in each inner array
>
> must be the actual value to be displayed.

> Values returned in the array must be of the type 'number'.

<br>

## solution

```javascript
function counterEffect(hitCount) {
   let result = [];
   
   for (let i = 0; i < hitCount.length; i++) {
      let temp = [];
      
      for (let j = 0; j <= hitCount[i]; j++) {
         temp.push(j);
      }
      result.push(temp);
   }
   return result;
}


counterEffect('0000');	// [[0], [0], [0], [0]]
counterEffect('0020');	// [[0], [0], [0, 1, 2], [0]]
```

> `.push()` 메소드
>
> 배열의 끝에 새 요소를 추가하고, 새 길이를 반환한다.

<br>