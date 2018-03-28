---
layout: post
title: "objectWithinObjects.js"
categories: dev
tags: algo
---

#### 객체(object) 알고리즘 문제

<br>

## problem

The values in an object can be objects themselves,

and in fact, this is a very common pattern.

<br>

Create another '`you`' object

which has a 'name' key,

the value of which is an object.

<br>

You should be able to access

your last name afterwards like so:

> you.name.last;	// YOUR LAST NAME

<br>

## solution

```javascript
var me = {
   email: 'dubbsong@gmail.com',
   github: 'github.com/dubbsong',
   blog: 'dubbsong.github.io',
   phone: '010-0000-0000',
   name: {
      first: 'Coco',
      last: 'Song'
   }
}


me.name.last;	// Song
```

