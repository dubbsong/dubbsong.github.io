---
layout: post
title: "(MDN 번역) 자바스크립트 객체"
categories: js
---

###### [MDN](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Objects/Basics) 번역

<br>

## JavaScript Object basics

###### JS 객체

<br>

- In this article, we'll look at fundamental JavaScript object syntax, and revisit some JavaScript features that we've already seen earlier in the course, reiterating the fact that many of the features you've already dealt with are objects.
  - 이 문서에서는 기본적인 JS 객체 구문을 살펴보고, 이미 알고 있는 일부 JS 기능을 다시 살펴본다.
  - 이미 다루었던 많은 기능들이 객체라는 사실을 다시 한 번 강조한다.

<br>

> **Objective:** To understand the basic theory behind object-oriented programming, how this relates to JavaScript ("most things are objects"), and how to start working with JavaScript objects.
>
> **목표:** 객체 지향 프로그래밍의 기본 이론 이해, JS에서 객체가 처리되는 방법 ("JS의 대부분이 객체이다"), JS 객체를 실제로 이용하는 방법

------

<br>

<br>

### Object basic

###### 객체 기본

<br>

- An object is a collection of related data and/or functionality (which usually consists of several variables and functions - which are called properties and methods when they are inside objects.)
  - 객체는 관련 데이터와 함수의 집합이다.
  - (함수는 일반적으로 여러 변수와 함수로 구성되며, 객체 내에 있을 때에는 속성 및 메소드라고 한다)
- Let's work through an example to understand what they look like.
  - 예제를 통해 객체가 무엇인지 살펴보자.

<br>

- To begin with, make a local copy of our [oojs.html](https://github.com/mdn/learning-area/blob/master/javascript/oojs/introduction/oojs.html) file.
  - 먼저, [oojs.html](https://github.com/mdn/learning-area/blob/master/javascript/oojs/introduction/oojs.html) 파일의 복사본을 로컬에 생성한다.
- This contains very little - a `<script>` element for us to write our source code into.
  - 이 파일에는 소스 코드를 작성하기 위한 `<script>` element가 거의 포함되어 있지 않다.
- We'll use this as a basic for exploring basic object syntax.
  - 기본 객체 구문을 분석하기 위해 이 파일을 사용할 것이다.
- While working with this example you should have your [developer tools JavaScript console](https://developer.mozilla.org/en-US/docs/Learn/Common_questions/What_are_browser_developer_tools#The_JavaScript_console) open and ready to type in some commands.
  - 이 예제로 작업하는 동안, [개발자 도구 JS 콘솔](https://developer.mozilla.org/en-US/docs/Learn/Common_questions/What_are_browser_developer_tools#The_JavaScript_console)을 열어 일부 명령어를 입력할 준비가 필요하다.

<br>

- As with many things in JavaScript, creating an object often begins with defining and initializing a variable.
  - JS의 많은 것들과 마찬가지로, 객체를 생성하는 것은 변수를 정의하고 초기화하는 것으로 시작한다.
- Try entering the following line below the JavaScript code that's already in your file, then saving and refreshing:
  - 아래의 코드를 oojs.html 파일의 JS script에 입력한 다음, 저장하고 새로 고침한다.

```js
var person = {};
```

<br>

- Now open to your browser's [JavaScript console](https://developer.mozilla.org/en-US/docs/Learn/Common_questions/What_are_browser_developer_tools#The_JavaScript_console), enter `person` into it, and press `Enter`/`Return`.
  - 이제 브라우저의 [JS 콘솔](https://developer.mozilla.org/en-US/docs/Learn/Common_questions/What_are_browser_developer_tools#The_JavaScript_console)을 열고, `person`을 입력한 후, `Enter`/`Return`을 누른다.
- You should get a result similar to one of the below lines:
  - 다음과 같은 결과를 얻을 것이다.

```js
[object Object]
Object {}
{}
```

<br>

- Congratulations, you've just created your first object.
  - 객체를 처음 생성한 것을 축하한다.
- But this is an empty object, so we can't really do much with it.
  - 하지만 빈 객체이므로, 이것으로 많은 것을 할 수 없다.
- Let's update the JavaScript object in our file to look like this:
  - 다음과 같이 JS 객체를 업데이트해보자.

```js
var person = {
  name: ['Sam', 'Azor'],
  age: 28,
  gender: 'male',
  interests: ['dance', 'party'],
  bio: function() {
    alert(this.name[0] + ' ' + this.name[1] + ' is ' + this.age + ' years old. He likes ' + this.interests[0] + ' and ' + this.interests[1] + '.');
  },
  greeting: function() {
    alert('What\'s up? I\'m ' + this.name[0] + '.');
  }
};
```

<br>

- After saving and refreshing, try entering some of the following into the JavaScript console on your browser devtools:
  - 저장하고 새로 고침 후, 브라우저 개발자 도구의 JS 콘솔에 다음 중 일부를 입력해보자.

```js
person.name
person.name[0]
person.age
person.interests[1]
person.bio()
person.greeting()
```

<br>

- You have now got some data and functionality inside your object, and are now able to access them with some nice simple syntax.
  - 이제 객체 내에 데이터와 함수가 있으므로, 구문을 사용해서 액세스할 수 있다.

<br>

> **Note:** If you are having trouble getting this to work, try comparing your code against our version - see [oojs-finished.html](https://github.com/mdn/learning-area/blob/master/javascript/oojs/introduction/oojs-finished.html) (also [see it running live](https://mdn.github.io/learning-area/javascript/oojs/introduction/oojs-finished.html)).
>
> **주의:** 진행에 문제가 있다면, 이 파일과 비교해본다.
>
> [oojs-finished.html](https://github.com/mdn/learning-area/blob/master/javascript/oojs/introduction/oojs-finished.html) (실행되고 있는 [예제](https://mdn.github.io/learning-area/javascript/oojs/introduction/oojs-finished.html))

> The live version will give you a blank screen, but that's OK - again, open your devtools and try typing in the above commands to see the object structure.
>
> live 버전에서는 빈 화면이 표시되지만, 괜찮다.
>
> 개발자 도구를 열고, 위의 명령어들을 입력해서 객체 구조를 확인한다.

<br>

- So what is going on here?
  - 무슨 일이 일어나는 걸까?
- Well, an object is made up of multiple members, each of which has a name (e.g. `name` and `age` above), and a value (e.g. `['Sam', 'Azor']` and `28`).
  - 객체는 name(예: `name`, `age`)과 value(예: `['Sam', 'Azor']`)를 가진 여러 member로 구성된다.
- Each name/value pair must be separated by a comma, and the name and value in each case are separated by a colon.
  - 각 name/value 쌍은 쉼표(,)로 구분하고, 각 name과 value는 콜론(:)으로 구분한다.
- This syntax always follows this pattern:
  - 구문은 항상 다음과 같은 패턴이 된다.

```js
var objectName = {
  member1Name: member1Value,
  member2Name: member2Value,
  member3Name: member3Value
};
```

<br>

- The value of an object member can be pretty much anything - in our person object we've got a string, a number, two arrays, and two functions.
  - 객체 member의 값은 무엇이든 될 수 있다.
  - person 객체에는 문자열, 숫자, 두 개의 배열, 두 개의 함수가 있다.
- The first four items are data items, and are referred to as the object's `properties`.
  - 처음 네 개의 item은 데이터 item이다.
  - 객체의 `속성`이라고 한다.
- The last two items are functions that allows the object to do something with that data, and are referred to as the object's `methods`.
  - 마지막 두 개의 item은 함수이다.
  - 이 함수는 데이터를 통해 무엇인가 할 수 있게 한다.
  - 객체의 `메소드`라고 한다.

<br>

- An object like this is referred to as an `object literal` - we've literally written out the object contents as we've come to create it.
  - 이와 같은 객체를 `객체 리터럴`이라고 한다.
  - 객체를 생성할 때, 객체의 내용을 문자 그대로 작성한다.
- This is in contrast to objects instantiated from classes, which we'll look at later on.
  - 객체 리터럴은 class로부터 인스턴스화 한 객체와는 대조적이다.
- It is very common to create an object using an object literal when you want to transfer a series of structured, related data items in some manner, for example sending a request to the server to be put into a database.
  - 연속된 구조체 또는 관련 데이터를 어떤 방식으로 전송하려는 경우, 객체 리터럴을 사용해서 객체를 생성하는 것이 일반적이다.
  - 예를 들어, 데이터베이스에 저장해달라고 서버에 요청하는 경우이다.
- Sending a single object is much more efficient than sending several items individually, and it is easier to work with than an array, when you want to identify individual items by name.
  - 여러 item을 개별적으로 전송하는 것보다, 하나의 객체를 전송하는 것이 훨씬 효율적이다.
  - 그리고 각 item을 name으로 식별하려는 경우, 배열을 사용하는 것보다 훨씬 쉽다.

------

<br>

<br>

### Dot notation

###### 점 표기법

<br>

- Above, you accessed the object's properties and methods using `dot notation`.
  - 위에서, 객체의 속성과 메소드에 `점 표기법`을 사용해서 액세스했다.
- The object name (person) acts as the `name space` - it must be entered first to access anything `encapsulated` inside the object.
  - 객체 이름(person)은 `name space(명칭 공간)` 역할을 한다.
  - 객체 내 캡슐화된 것에 액세스하려면, 우선 객체 이름을 입력해야 한다.
- Next you write a dot, then the item you want to access - this can be the name of a simple property, an item of an array property, or a call to one of the object's methods.
  - 다음으로 점(\.)을 찍고, 액세스하고자 하는 item을 작성한다.
  - item은 속성의 이름, 배열 속성의 item, 객체의 메소드 중 하나에 대한 호출일 수 있다.
- For example:

```js
person.age
person.interests[1]
person.bio()
```

<br>

###### Sub-name spaces

###### name space 내의 name space (sub-name space)

<br>

- It is even possible to make the value of an object member another object.
  - 객체 member의 값을 다른 객체로 만들 수도 있다.
- For example, try changing the name member from
  - 예를 들어, 아래 name member를

```js
name: ['Sam', 'Azor'],
```

<br>

- to
  - 다음과 같이 변경해보자.

```js
name: { first: 'Sam', last: 'Azor'},
```

<br>

- Here we are effectively creating a `sub-name space`.
  - 우리는 유효한 `sub-name space`를 생성했다.
- This sounds complex, but really it's not to access these items you just need to chain the extra step onto the end with another dot.
  - 이는 복잡하게 들리지만, 실제로는 그렇지 않다.
  - 이러한 item에 액세스하기 위해, 그저 끝에 점을 하나 더 찍어주면 된다.
- Try these in the JS console:
  - JS 콘솔에 다음과 같이 입력해보자.

```js
person.name.first
person.name.last
```

<br>

- **Important:** At this point you'll also need to go through your method code and change any instances of
  - **중요:** 이제 다음 메소드 코드를

```js
name[0]
name[1]
```

<br>

- to
  - 다음과 같이 변경해야 한다.

```js
name.first
name.last
```

<br>

- Otherwise your methods will no longer work.
  - 그렇지 않으면, 메소드는 더 이상 작동하지 않는다.

------

<br>

<br>

### Bracket notation

###### 괄호 표기법

<br>

- There is another way to access object properties - using bracket notation.
  - 객체 속성에 액세스하는 다른 방법이 있다.
  - 괄호 표기법을 사용하는 것이다.
- Instead of using these:
  - 다음과 같이 사용하는 대신,

```js
person.age
person.name.first
```

<br>

- You can use:
  - 다음과 같이 사용할 수 있다.

```js
person['age']
person['name']['first']
```

<br>

- This looks very similar to how you access the items in an array, and it is basically the same thing - instead of using an index number to select an item, you are using the name associated with each member's value.
  - 이는 배열의 item에 액세스하는 방법과 매우 유사하게 보이는데, 기본적으로 동일한 방법이다.
  - index 번호를 사용해서 item을 선택하는 대신, 각 member의 값과 관련된 name을 사용한다.
- It is no wonder that objects are sometimes called `associative arrays` - they map strings to values in the same way that arrays map numbers to values.
  - 객체를 `연관 배열`이라고도 한다.
  - 배열에서 숫자를 값에 매핑(mapping)하는 것과 같은 방법으로, 문자열을 값에 매핑한다.

------

<br>

<br>

### Setting object members

###### 객체 member 설정하기

<br>

- So far we've only looked at retrieving (or `getting`) object members - you can also `set` (update) the value of object members by simply declaring the member you want to set (using dot or bracket notation).
  - 지금까지는 객체 member를 단순히 검색(또는 `가져오기`)하는 것만 살펴보았다.
  - 설정하려는 member를 간단히 선언해서, 객체 member의 값을 `설정`(업데이트)할 수도 있다.

```js
person.age = 45;
person['name']['last'] = 'Leo';
```

<br>

- Try entering the above lines, and then getting the members again to see how they've changed, like so:
  - 위의 코드를 입력한 다음, member가 변경되었는지 확인해보자.

```js
person.age	// 45
person['name']['last']	// Leo
```

<br>

- Setting members doesn't just stop at updating the values of existing properties and methods; you can also create completely new members.
  - member를 설정하는 것은, 기존 속성과 메소드의 값을 업데이트하는 것뿐만 아니라, 완전히 새로운 member를 생성할 수도 있다.
- Try these in the JS console:
  - JS 콘솔에 다음과 같이 입력해보자.

```js
person['eyes'] = 'yellow';
person.farewell = function() { alert('Have a good day!'); }
```

<br>

- You can now test out your new members:
  - 이제 새로운 member를 테스트해보자.

```js
person['eyes']	// yellow
person.farewell()	// Have a good day!
```

<br>

- One useful aspect of bracket notation is that it can be used to set not only member values dynamically, but member names too.
  - 괄호 표기법의 유용한 측면 중 하나는, member의 value를 동적으로 설정할 수 있을 뿐만 아니라, member의 name에도 사용할 수 있다는 것이다.
- Let's say we wanted users to be able to store custom value types in their people data, by typing the member name and value into two text inputs.
  - 사용자가 두 개의 텍스트 input을 통해, people 데이터에 사용자 정의 값을 저장하려는 경우를 생각해보자.
- We could get those values like this:
  - 그 값은 다음과 같이 얻어올 수 있다.

```js
var myDataName = nameInput.value;
var myDataValue = nameValue.value;
```

<br>

- We could then add this new member name and value to the `person` object like this:
  - 그런 다음, 이 새로운 member의 name과 value를 `person` 객체에 추가할 수 있다.

```js
person[myDataName] = myDataValue;
```

<br>

- To test this, try adding the following lines into your code, just below the closing curly brace of the `person` object:
  - 이를 테스트하기 위해, `person` 객체의 닫는 중괄호 바로 아래에 다음 코드를 추가해보자.

```js
var myDataName = 'height';
var myDataValue = '1.75m';
person[myDataName] = myDataValue;
```

<br>

- Now try saving and refreshing, and entering the following into your text input:
  - 이제 저장과 새로 고침하고, 텍스트 input에 다음을 입력해보자.

```js
person.height	// 1.75m
```

<br>

- Adding a property to an object using the method above isn't possible with dot notation, which can only accept a literal member name, not a variable value pointing to a name.
  - 위의 방법을 사용해서 객체에 속성을 추가하는 것은, 점 표기법으로는 불가능하다.
  - name을 가리키는 변수 값이 아닌, 리터럴 member name만 허용할 수 있다.

------

<br>

### What is "this"?

###### "this"는 무엇인가?

<br>

- You may have noticed something slightly strange in our methods.
  - 이전 메소드 중에서, 조금 이상한 것을 발견했을 수 있다.
- Look at this one for example:
  - 다음 예제를 살펴보자.

```js
greeting: function() {
  alert('What\s up? I\'m ' + this.name.first + '.');
}
```

<br>

- You are probably wondering what "this" is.
  - "this"가 무엇인지 궁금해할 것이다.
- The `this` keyword refers to the current object the code is being written inside - so in this case `this` is equivalent to `person`.
  - `this` 키워드는, 작성된 코드가 속해 있는 현재 객체를 나타낸다.
  - 위의 예제에서 `this`는 `person` 객체와 동일하다.
- So why not just write `person` instead?
  - 그렇다면 왜 직접 `person`을 작성하지 않은 걸까?
- As you'll see in the [Object-oriented JavaScript for beginners](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Objects/Object-oriented_JS) article, when we start creating constructors and so on, `this` is very useful - it will always ensure that the correct values are used when a member's context changes (e.g. two different `person` object instances may have different names, but will want to use their own name when saying their greeting).
  - [입문자를 위한 객체 지향 JS](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Objects/Object-oriented_JS) 문서에서 볼 수 있듯이, 생성자를 생성할 때 매우 유용하다.
  - member의 컨텍스트(상황 정보)가 변경되는 경우에도, 항상 올바른 값이 사용되도록 한다.
  - (예: 두 개의 다른 `person` 객체 인스턴스는 서로 다른 name을 가진다. 하지만 greeting을 출력할 때 각자의 name을 사용한다고 생각해보자.)

<br>

- Let's illustrate what we mean with a simplified pair of person objects:
  - 간소화한 두 person 객체로 이를 설명해본다.

```js
var person1 = {
  name: 'Sam',
  greeting: function() {
    alert('What\'s up? I\'m ' + this.name + '.');
  }
}

var person2 = {
  name: 'Leo',
  greeting: function() {
    alert('What\'s up? I\'m ' + this.name + '.');
  }
}
```

<br>

- In this case, `person1.greeting()` will output `"What's up? I'm Sam."`; `person2.greeting()` on the other hand will output `"What's up? I'm Leo."`, even though the method's code is exactly the same in each case.
  - `person1.greeting()`은 `"What's up? I'm Sam."`을 출력한다.
  - `person2.greeting()`은 `"What's up? I'm Leo."`를 출력한다.
- As we said earier, `this` is equal to the object the code is inside - this isn't hugely useful when you are writing out object literals by hand, but it really comes into its own when you are dynamically generating objects (for example using constructors).
  - 앞서 말했듯이, `this`는 코드가 속해 있는 객체와 동일하다.
  - 객체 리터럴을 직접 작성할 때에는 그리 유용하지 않지만, 객체를 동적으로 생성할 때에는 매우 유용하다.
  - (예: 생성자를 사용하는 경우)
- It will all become clearer later on.
  - 이는 나중에 더 확실히 이해될 것이다.

------

<br>

<br>

### You've been using objects all along

###### 객체를 쭉 사용해왔다

<br>

- As you've been going through these examples, you have probably been thinking that the dot notation you've been using is very familiar.
  - 여러 예제들을 살펴보았는데, 점 표기법을 사용하는 것이 꽤 자연스럽게 느껴질 것이다.
- That's because you've been using it throughout the course.
  - 코스 내내 사용했기 때문이다.
- Every time we've been working through an example that uses a built-in browser API or JavaScript object, we've been using objects, because such features are built using exactly the same kind of object  structures that we've been looking at here, albeit more complex ones than in our own basic custom examples.
  - 브라우저 내장 API 또는 JS 객체를 사용하는 예제를 통해 객체를 사용해왔다.
  - 그런 기능들은 여기서 보았던 객체 구조와 정확히 같은 종류의 객체를 사용해서 만들어졌기 때문이다.
  - 물론 우리의 예제보다 더 복잡하기는 하다.

<br>

- So when you used string methods like:
  - 문자열 메소드가 다음과 같이 사용되는 경우를 살펴보자.

```js
myString.split(',');
```

<br>

- You were using a method available on an instance of the [String](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String) class.
  - [String](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String) class의 인스턴스에서 사용할 수 있는 메소드를 사용하고 있다.
- Every time you create a string in your code, that string is automatically created as an instance of `String`, and therefore has several common methods and properties available on it.
  - 코드에서 문자열을 생성할 때마다, 해당 문자열은 `String`의 인스턴스로 자동 생성된다.
  - 그 때문에, 사용할 수 있는 여러 공통 메소드와 속성을 가진다.

<br>

- When you accessed the document object model using lines like this:
  - 다음과 같이 문서 객체 모델(DOM)에 액세스 하는 경우,

```js
var myDiv = document.createElement('div');
var myVideo = document.querySelector('video');
```

<br>

- You were using methods available on an instance of the [Document](https://developer.mozilla.org/en-US/docs/Web/API/Document) class.
  - [Document](https://developer.mozilla.org/en-US/docs/Web/API/Document) class의 인스턴스에서 사용할 수 있는 메소드를 사용하고 있는 것이다.
- For each web page loaded, an instance of `Document` is created, called `document`, which represents the entire page's structure, content, and other features such as its URL.
  - 각 웹 페이지가 로딩될 때, `document`라는 `Document`의 인스턴스가 생성된다.
  - `document`는 전체 페이지의 구조, 내용, URL 같은 다른 기능을 나타낸다.
- Again, this means that it has several common methods and properties available on it.
  - 다시 말하지만, 이는 여러 공통 메소드와 속성을 사용할 수 있다는 뜻이다.

<br>

- The same is true of pretty much any other built-in object/API you've been using - [Array](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array), [Math](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math), and so on.
  - 내내 사용해왔던 거의 모든 내장 객체/API ([Array](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array), [Math](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math) 등)도 마찬가지이다.

<br>

- Note that built in Objects/APIs don't always create object instances automatically.
  - 내장 객체/API가 항상 자동으로 객체 인스턴스를 생성하는 것은 아니다.
- As an example, the [Notifications API](https://developer.mozilla.org/en-US/docs/Web/API/Notifications_API) - which allows modern browsers to fire system notifications - requires you to instantiate a new object instance using the constructor for each notification you want to fire.
  - 예를 들어, [Notifications API](https://developer.mozilla.org/en-US/docs/Web/API/Notifications_API) (최신 브라우저에서 시스템 알림을 실행할 수 있는 기능)를 실행하려면, 시작하려는 각 알림의 생성자를 사용해서 새로운 객체 인스턴스를 인스턴스화해야 한다.
- Try entering the following into your JavaScript console:
  - JS 콘솔에 다음 코드를 입력해보자.

```js
var myNotification = new Notification('All good?');
```

<br>

- Again, we'll look at constructors in a later article.
  - 다음 문서에서 생성자에 대해 좀 더 자세히 알아보자.

<br>

> **Note:** It is useful to think about the way objects communicate as `message passing` - when  an object needs another object to perform some kind of action often it will send a message to another object via one of its methods, and wait for a response, which we know as a return value.
>
> **주의:** 객체 간 통신은 `메시지 전달` 방식을 사용한다고 생각하는 게 좋다.
>
> 객체가 어떤 종류의 동작을 수행하기 위해 다른 객체를 필요로 할 때, 그 객체는 메소드 중 하나를 통해 다른 객체에 메시지를 보내고, 반환 값으로 응답을 기다린다.

------

<br>

<br>

### Summary

###### 요약

<br>

- Congratulations, you've reached the end of our first JS objects article - you should now have a good idea of how to work with objects in JavaScript - including creating your own simple objects.
  - 축하한다. 첫 번째 JS 객체 문서의 끝에 다다랐다.
  - 이제는 JS 객체를 어떻게 활용하는지에 대해 잘 알고 있어야 한다.
  - 간단한 사용자 정의 객체를 생성하는 방법도 잘 알고 있어야 한다.
- You should also appreciate that objects are very useful as structures for storing related data and functionality - if you tried to keep track of all the properties and methods in our `person` object as separate variables and functions, it would be inefficient and frustrating, and we'd run the risk of clashing with other variables and functions that have the same names.
  - 객체가 관련 데이터와 함수를 저장하는 데 매우 유용한 구조라는 것도 알아야 한다.
  - `person` 객체의 모든 속성과 메소드를 별도의 변수와 함수로 구현하려고 한다면, 비효율적이고 끔찍한 일이 될 것이다.
  - 동일한 이름을 가진 다른 변수 및 함수와 충돌할 위험도 있을 것이다.
- Objects let us keep the information safely locked away in their own package, out of harm's way.
  - 객체는 위험이 없는 고유의 패키지에 정보를 안전하게 보관할 수 있도록 한다.

<br>

- In the next article we'll start to look at object-oriented programming (OOP) theory, and how such techniques can be used in JavaScript.
  - 다음 문서에서는 객체 지향 프로그래밍(OOP) 이론과, 그러한 기술을 JS에서 어떻게 사용할 수 있는지 살펴본다.

------

<br>

<br>
