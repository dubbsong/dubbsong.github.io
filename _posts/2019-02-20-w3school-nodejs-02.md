---
layout: post
title: "(Node.js 02) intro"
categories: dev
tags: nodejs
---

###### [w3schools Node.js](https://www.w3schools.com/nodejs/) 번역

<br>

## What is Node.js?

###### Node.js는 무엇인가?

- Node.js is an open source server environment.
  - Node.js는 오픈 소스 서버 환경이다.
- Node.js is free.
  - Node.js는 무료이다.
- Node.js runs on various platforms (Windows, Linux, Unix, Mac OS X, etc.).
  - Node.js는 다양한 플랫폼(Windows, Linux, Unix, Mac OS X 등)에서 실행된다.
- Node.js uses JavaScript on the server.
  - Node.js는 서버에서 JS를 사용한다.

<br>

<br>

## Why Node.js?

###### 왜 Node.js인가?

> **Node.js uses asynchronous programming!**
>
> **Node.js는 비동기 프로그래밍을 사용한다!**

<br>

- A common task for a web server can be to open a file on the server and return the content to the client.
  - 웹 서버의 일반적인 작업은, 서버에서 파일을 열고 내용을 클라이언트로 반환하는 것이다.

<br>

- Here is how PHP or ASP handles a file request:

  - PHP 또는 ASP가 파일 요청을 처리하는 방법은 다음과 같다.

  <br>

  1. Sends the task to the computer's file system.
     - 작업을 컴퓨터의 파일 시스템으로 보낸다.
  2. Waits while the file system opens and reads the file.
     - 파일 시스템이 열리고 파일을 읽는 동안 기다린다.
  3. Returns the content to the client.
     - 내용을 클라이언트로 반환한다.
  4. Ready to handle the next request.
     - 다음 요청을 처리할 준비를 한다.

<br>

- Here is how Node.js handles a file request:

  - Node.js가 파일 요청을 처리하는 방법은 다음과 같다.

  <br>

  1. Sends the task to the computer's file system.
     - 작업을 컴퓨터의 파일 시스템으로 보낸다.
  2. Ready to handle the next request.
     - 다음 요청을 처리할 준비를 한다.
  3. When the file system has opened and read the file, the server returns the content to the client.
     - 파일 시스템이 파일을 열고 읽었을 때, 서버는 내용을 클라이언트로 반환한다.

<br>

- Node.js eliminates the waiting, and simply continues with the next request.
  - Node.js는 대기(waiting)를 없애고, 다음 요청을 처리할 준비를 계속한다.

<br>

<br>

## What Can Node.js Do?

###### Node.js는 무엇을 할 수 있는가?

- Node.js can generate dynamic page content.
  - Node.js는 동적 페이지 내용을 생성할 수 있다.
- Node.js can create, open, read, write, delete, and close files on the server.
  - Node.js는 서버에서 파일을 생성하고, 열고, 읽고, 작성하고, 제거하고, 닫을 수 있다.
- Node.js can collect form data.
  - Node.js는 form data를 수집할 수 있다.
- Node.js can add, delete, modify data in your database.
  - Node.js는 데이터베이스에서 데이터를 추가, 제거, 수정할 수 있다.

<br>

<br>

## What is a Node.js File?

###### Node.js 파일은 무엇인가?

- Node.js files contain tasks that will be executed on certain events.
  - Node.js 파일에는 특정 이벤트에서 실행될 작업이 포함되어 있다.
- A typical event is someone trying to access a port on the server.
  - 이벤트는 보통 서버의 port에 액세스하려는 것이다.
- Node.js files must be initiated on the server before having any effect.
  - Node.js 파일은 서버에서 실행되어야 한다.
- Node.js files have extension ".js".
  - Node.js 파일은 ".js" 확장자를 가진다.

<br>

<br>