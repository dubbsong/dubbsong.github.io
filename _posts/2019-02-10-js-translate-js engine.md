---
layout: post
title: "(번역) JavaScript 엔진"
categories: js
---

###### [Jen Looper](http://www.softwaremag.com/javascript-engines/) 포스팅 번역

<br>

## JavaScript Engines

###### JS 엔진

<br>

- Writing code for the Web sometimes feels a little magical in that developers write a sequence of characters and like magic, those characters turn into concrete images, words, and actions within a browser.
  - 웹을 위한 코드를 작성하는 것은, 가끔 아주 멋진 기분이 들게 한다.
  - 일련의 문자는 브라우저에서 구체적인 이미지, 단어, 동작이 된다.
- Understanding the technology can help developers better tune their craft as programmers.
  - 기술을 이해하는 것은, 개발자가 프로그래머로서 자신의 기술을 더 잘 사용할 수 있게 한다.

<br>

- JavaScript engines are a complex technology, and knowing why different platforms use different engines is essential for developers trying to produce optimized code in the shortest time possible.
  - JS 엔진은 복잡한 기술이다.
  - 다른 플랫폼이 다른 엔진을 사용하는 이유를 아는 것은, 개발자가 가능한 가장 짧은 시간에 최적화된 코드를 작성하려고 노력할 때 필수적이다.

<br>

#### Virtual Machines

###### 가상 머신

<br>

- A JavaScript engine is often defined as a type of virtual machine or software-driven emulation of a given computer system.
  - JS 엔진은 종종 주어진 컴퓨터 시스템의 가상 머신 또는 소프트웨어 기반 에뮬레이션 타입으로 정의된다.
- There are many types of virtual machines and they are classified by how precisely they are able to emulate or substitute for actual physical machines.
  - 가상 머신에는 다양한 타입이 있다.
  - 실제 물리적 머신을 에뮬레이트 또는 대체할 수 있는 방법에 따라 분류된다.

<br>

- A system virtual machine, for example, provides a complete emulation of a platform on which an operating system can be executed.
  - 예를 들어, 시스템 가상 머신은 운영 체제가 실행될 수 있는 플랫폼의 완전한 에뮬레이션을 제공한다.
- Mac users are familiar with Parallels, a system virtual machine that allows Windows to be run on a Mac.
  - Mac 사용자는 Windows를 Mac에서 실행할 수 있는 시스템 가상 머신인 Parallels에 익숙하다.

<br>

- A process virtual machine, on the other hand, is less fully functional and can run only one program or process.
  - 반면에, 프로세스 가상 머신은 덜 기능적이다.
  - 하나의 프로그램이나 프로세스만 실행할 수 있다.
- Wine is a process virtual machine that allows Windows applications to be run on a Linux machine, but does not provide an entire Windows OS on a Linux box.
  - Wine은 Windows 애플리케이션을 Linux 머신에서 실행할 수 있게 해주는 프로세스 가상 머신이다.
  - 하지만 전체 Windows OS를 Linux box에 제공하지는 않는다.

<br>

- A JavaScript engine is a kind of process virtual machine that is designed specifically to interpret and execute JavaScript code.
  - JS 엔진은 프로세스 가상 머신의 일종이다.
  - JS 코드를 해석하고 실행하도록 특별히 설계되었다.
- It's important to differentiate between the layout engines that power a browser by structuring a Web page, versus the lower level JavaScript engines that interpret and execute code.
  - 웹 페이지 구성에 따라 브라우저의 성능을 향상시키는 레이아웃 엔진과, 코드를 해석하고 실행하는 lower level의 JS 엔진을 구별하는 것이 중요하다.

<br>

#### What is a JavaScript Engine?

###### JS 엔진이란 무엇인가?

<br>

- The basic job of a JavaScript engine is to take the JavaScript code that a developer writes and convert it to fast, optimized code that can be interpreted by a browser or even embedded into an application.
  - JS 엔진의 기본적인 작업은, 개발자가 작성한 JS 코드를 브라우저로 해석하거나 애플리케이션에 임베디드 할 수 있는 빠르고 최적화된 코드로 변환하는 것이다.

<br>

- More precisely, each JavaScript engine implements a version of ECMAScript, of which JavaScript is a dialect.
  - 더 정확히 말하자면, 각 JS 엔진은 ECMAScript의 버전을 실행한다.
- As ECMAScript evolves, so do JavaScript engines.
  - ECMAScript가 발전하면, JS 엔진도 발전한다.
- There are so many different engines because each one is designed to work with a different Web browser, headless browser, or runtime like Node.js.
  - 각각 다른 웹 브라우저, headless 브라우저(GUI가 없는 웹 브라우저) 또는 Node.js와 같은 런타임에서 작동하도록 설계되었으므로, 매우 다양한 엔진들이 있다.
- Headless browsers are Web browsers without a graphic user interface that are useful for running automated tests against Web products.
  - headless 브라우저는 GUI가 없는 웹 브라우저이다.
  - 웹 결과물에 대한 자동 테스트를 실행하는 데 유용하다.
- A good example is PhantomJS.
  - PhantomJS가 좋은 예이다.
- Node.js is an asynchronous, event-driven framework that allows JavaScript to be used on the server side.
  - Node.js는 JS를 서버 사이드에서 사용할 수 있게 하는 비동기식 이벤트 구동형(event-driven) 프레임워크이다.
- Since these are JavaScript-driven tools, they are powered by JavaScript engines.
  - 이것들은 JS에 의해 작동되는 툴이므로, JS 엔진에 의해 작동된다.

<br>

- A variety of JavaScript engines are available to analyze, parse, and execute client-side code.
  - 다양한 JS 엔진을 사용해서 클라이언트 사이드 코드를 분석, 파싱, 실행할 수 있다.
- With every browser version release, the JavaScript engine might be changed or optimized to keep up with the state-of-the-art JavaScript code execution.
  - 모든 브라우저 버전이 출시되면, JS 엔진이 최신 JS 코드 실행을 따라갈 수 있도록 변경되거나 최적화될 수 있다.

<br>

#### How Does a JavaScript Engine work?

###### JS 엔진은 어떻게 작동하는가?

<br>

- Given the definition of a virtual machine, it makes sense to term a JavaScript engine as a process virtual machine, since its sole purpose is to read and compile JavaScript code.
  - JS 엔진을 프로세스 가상 머신으로 사용하는 것이 타당하다.
  - JS 코드를 읽고, 컴파일하는 것이 유일한 목적이기 때문이다.
- This doesn't mean that it's a simple engine.
  - 이는 단순히 엔진이라는 것을 의미하지 않는다.
- JavaScriptCore, for example, has six building blocks that analyze, interpret, optimize, and garbage collect JavaScript code.
  - 예를 들어, JSCore에는 JS 코드를 분석, 해석, 최적화, 쓰레기 수집(garbage collection)하는 6개의 빌딩 블록이 있다.

<br>

- So how does this work?
  - 그러면 어떻게 작동하는가?
- This depends, of course, on the engine.
  - 물론 엔진에 달려 있다.
- The two main engines of interest are Webkit's JavaScriptCore and Google's V8 engine because they are leveraged by NativeScript.
  - NativeScript에 의해 활용되므로, 두 가지 주요한 엔진은 Webkit의 JSCore와 Google의 V8 엔진이다.
- These two engines handle processing code differently.
  - 이 두 엔진은 프로세싱 코드를 다르게 처리한다.

<br>

- JavaScriptCore performs a series of steps to interpret and optimize a script.
  - JSCore는 스크립트를 해석하고 최적화하는 일련의 단계를 수행한다.
- It performs a lexical analysis, breaking down the source into a series of tokens or strings with an identified meaning.
  - 어휘 분석을 수행해서, 소스를 일련의 토큰 또는 확인된 의미의 문자열로 나눈다.
- The tokens are then analyzed by the parser for syntax and built into a syntax tree.
  - 구문 분석기에서 토큰을 분석하고, 구문 트리로 작성한다.
- Four just-in-time processes then kick in, analyzing and executing the bytecode produced by the parser.
  - 4개의 프로세스가 파서에 의해 생성된 바이트코드를 분석, 실행한다.
- In simple terms, this JavaScript engine takes the source code, breaks it up into strings - a.k.a lexes it, takes those strings and converts them into bytecode that a compiler can understand, and then executes it.
  - 간단히 말해, JS 엔진은 소스 코드를 가져와서 문자열로 분해한다.
  - 그 문자열을 가져와서 컴파일러가 이해할 수 있는 바이트코드로 변환한 다음 실행한다.

<br>

- Google's V8 engine, written in C++, also compiles and executes JavaScript source code, handles memory allocation, and garbage collects leftovers.
  - C++로 작성된 Google의 V8 엔진은 JS 소스 코드를 컴파일 및 실행하고, 메모리 할당을 처리하며, 쓰레기 수집(garbage collection)을 한다.
- Its design consists of two compilers that assemble source code directly into machine code.
  - 그 설계는 소스 코드를 직접 기계어 코드로 어셈블하는 두 개의 컴파일러로 구성된다.

<br>

- These compilers are Full-codegen, a fast compiler that produces un-optimized code and Crankshaf, a slower compiler that produces fast, optimized code.
  - 이러한 컴파일러는 최적화되지 않은 코드를 생성하는 고속 컴파일러 Full-codegen과, 최적화된 코드를 빠르게 생성하는 느린 컴파일러 Crankshaf이다.

<br>

- If Crankshaft determines that the un-optimized code generated by Full-codegen is in need of optimization, it replaces it - a process known as 'crankshafting'.
  - Crankshaft가 Full-codegen에 의해 생성된 최적화되지 않은 코드가 최적화가 필요한 것으로 판단하면, 이를 'crankshafting'이라는 프로세스로 대체한다.

<br>

- Once machine code is produced by the compilation process, the engine exposes all the data types, operators, objects, and functions specified in the ECMA standard to the browser or any runtime that needs to use them, like NativeScript.
  - 컴파일 과정에서 기계어 코드가 생성되면, 엔진은 ECMA 표준에 지정된 모든 데이터 타입, 연산자, 객체, 함수를 사용해야 하는 브라우저 또는 런타임에 노출시킨다.

<br>

#### What Does this Mean for Developers?

###### 이것은 개발자에게 무엇을 의미하는가?

<br>

- The goal of a JavaScript engine's code parsing and execution process is to generate the most optimized code in the shortest possible time.
  - JS 엔진의 코드 파싱과 실행 프로세스의 목표는, 최대한 짧은 시간 내에 최적화된 코드를 생성하는 것이다.

<br>

- The bottom line is that the evolution of these engine parallels the quest to evolve the Web and mobile spheres to make them perform as well as possible.
  - 결론은, 이러한 엔진의 발전이 웹과 모바일 분야를 발전시키기 위한 탐구와 유사하다는 것이다.
- To track this evolution, benchmarking graphs produced on sites such as arewefastyet.com show how various engines perform in comparison to each other.
  - arewefastyet.com과 같은 사이트에서 생성된 벤치마킹 그래프는 다양한 엔진을 서로 비교했을 때 어떻게 작동하는지를 보여준다.

<br>

- Any Web developer needs to be aware of the differences inherent in the browsers that display the code that is produced, debugged, and maintained.
  - 모든 웹 개발자는 생성, 디버깅, 유지 관리되는 코드를 보여주는 브라우저의 고유한 차이점을 알아야 한다.
- More specifically, it's important to understand why certain scripts may work slowly on one browser faster on another.
  - 더 구체적으로, 특정 스크립트가 한 브라우저에서 다른 스크립트보다 느리게 작동하는 이유를 이해하는 것이 중요하다.
- Keeping up with the changes in JavaScript engines will really pay off for those looking to evolve as a Web, mobile, or application developer.
  - JS 엔진의 변화를 따라가는 것은 웹, 모바일, 애플리케이션 개발자로 발전하려는 사람들에게 정말로 도움이 될 것이다.

<br>