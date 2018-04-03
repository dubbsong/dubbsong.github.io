---
layout: post
title: "rockPaperScissors.js (8kyu)"
categories: codewars
tags: Algorithm Codewars
---

#### 조건문(if) 알고리즘 문제

<br>

## problem

Let's Play!

You have to return which player won!

In case of a draw return Draw!

<br>

## solution 01

```javascript
function rockPaperScissors(p1, p2) {
  if (p1 === p2) {
    return `Draw!`;
  } else if (p1 === 'rock' && p2 === 'paper') {
    return `Player 2 won!`;
  } else if (p1 === 'rock' && p2 === 'scissors') {
    return `Player 1 won!`;
  } else if (p1 === 'paper' && p2 === 'rock') {
    return `Player 1 won!`;
  } else if (p1 === 'paper' && p2 === 'scissors') {
    return `Player 2 won!`;
  } else if (p1 === 'scissors' && p2 === 'rock') {
    return `Player 2 won!`;
  } else if (p1 === 'scissors' && p2 === 'paper') {
    return `Player 1 won!`;
  }
}


console.log(rockPaperScissors('rock', 'rock')); // Draw!
console.log(rockPaperScissors('rock', 'scissors')); // Player 1 won!
console.log(rockPaperScissors('paper', 'scissors')); // Player 2 won!
```

<br>

## solution 02

```javascript
function rockPaperScissors(p1, p2) {
  if (p1 === p2) {
    return `Draw!`;
  }

  if (p1 === 'rock' && p2 === 'scissors') {
    return `Player 1 won!`;
  } else if (p1 === 'paper' && p2 === 'rock') {
    return `Player 1 won!`;
  } else if (p1 === 'scissors' && p2 === 'paper') {
    return `Player 1 won!`;
  } else {
    return `Player 2 won!`;
  }
}


console.log(rockPaperScissors('rock', 'rock')); // Draw!
console.log(rockPaperScissors('rock', 'scissors')); // Player 1 won!
console.log(rockPaperScissors('paper', 'scissors')); // Player 2 won!
```

<br>

## solution 03

```javascript
function rockPaperScissors(p1, p2) {
   if (p1 === p2) return `Draw!`;
   
   let rules = {
      rock: 'scissors',
      paper: 'rock',
      scissors: 'paper'
   }
   
   if (rules[p1] === p2) {
      return `Player 1 won!`;
   } else {
      return `Player 2 won!`;
   }
}


console.log(rockPaperScissors('rock', 'rock')); // Draw!
console.log(rockPaperScissors('rock', 'scissors')); // Player 1 won!
console.log(rockPaperScissors('paper', 'scissors')); // Player 2 won!
```

<br>

## solution 04

```javascript
function rockPaperScissors(p1, p2) {
   if (p1 === p2) {
      return `Draw!`;
   }
   return `Player ${/rockscissors|scissorspaper|paperrock/.test(p1 + p2) ? 1 : 2} won!`;
}


console.log(rockPaperScissors('rock', 'rock')); // Draw!
console.log(rockPaperScissors('rock', 'scissors')); // Player 1 won!
console.log(rockPaperScissors('paper', 'scissors')); // Player 2 won!
```

