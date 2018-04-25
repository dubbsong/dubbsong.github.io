---
layout: post
title: "songDecoder.js"
categories: dev
tags: algo
---

#### 메소드(method) 활용 알고리즘 문제

<br>

## problem

Input

The input consists of a single non-empty string,

consisting only of uppercase English letters,

the string's length doesn't exceed 200 characters.

<br>

Ouput

Return the words of the initial song.

Separate the words with a space.

<br>

```javascript
// Examples

songDecoder('WUBWEWUBAREWUBWUBTHEWUBCHAMPIONSWUB');	// WE ARE THE CHAMPIONS
```

<br>

## solution

```javascript
function songDecoder(song) {
   return song.split('WUB').filter(function(item) {
      return item !== '';
   })
   .join(' ');
}


songDecoder('WUBWUBSSUPWUBWUBBRO?WUBWUB');	// SSUP BRO?
```

