---
layout: post
title: "thisKeyword.js (Algorithm)"
categories: dev
tags: algo
---

#### 객체(object) + this 키워드 + 메소드(method) 활용 알고리즘 문제

<br>

## problem

Example use:

```javascript
sport.playerNames();
// ['Sam plays basketball', 'Leo plays basketball']
```

<br>

## solution

```javascript
var sport = {
   name: 'basketball',
   players: [
      { name: 'Sam', age: 28 },
      { name: 'Leo', age: 25 }
   ],
   playerNames: function() {
      return this.players.map(player => {
         return `${player.name} plays ${this.name}`;
      })
   }
}


sport.playNames();
// ['Sam plays basketball', 'Leo plays basketball']
```

