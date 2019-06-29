---
layout: post
title: "(공식 리액트 Docs) AJAX and APIs"
categories: dev
tags: react
---

###### [공식 리액트 Docs](https://reactjs.org/docs/faq-ajax.html#how-can-i-make-an-ajax-call) 번역

<br>

#### How can I make an AJAX call?

###### AJAX 호출을 하려면 어떻게 해야 하는가?

<br>

- You can use any AJAX library you like with React.
  - React를 사용하면 원하는 AJAX 라이브러리를 사용할 수 있다.
- Some popular ones are [Axios](https://github.com/axios/axios), [jQuery AJAX](https://api.jquery.com/jQuery.ajax/), and the browser built-in [window.fetch](https://developer.mozilla.org/en-US/docs/Web/API/Fetch_API).
  - 인기 있는 것들은 [Axios](https://github.com/axios/axios), [jQuery AJAX](https://api.jquery.com/jQuery.ajax/), 브라우저 내장 [window.fetch](https://developer.mozilla.org/en-US/docs/Web/API/Fetch_API)이다.

------

<br>

#### Where in the component lifecycle should I make an AJAX call?

###### 컴포넌트 라이프사이클의 어디에서 AJAX 호출을 해야 하는가?

<br>

- You should populate data with AJAX calls in the [componentDidMount](https://reactjs.org/docs/react-component.html#mounting) lifecycle method.
  - [componentDidMount](https://reactjs.org/docs/react-component.html#mounting) 라이프사이클 메소드에서 AJAX 호출로 데이터를 채워야 한다.
- This is so you can use `setState` to update your component when the data is retrieved.
  - 데이터가 검색될 때, `setState`를 사용해서 컴포넌트를 업데이트할 수 있다.

------

<br>

#### Example: Using AJAX results to set local state

###### 예제: AJAX 결과를 사용해서 local state 설정하기

<br>

- The component below demonstrates how to make an AJAX call in `componentDidMount` to populate local component state.
  - 아래 컴포넌트는 `componentDidMount`에서 AJAX 호출을 생성해서 local 컴포넌트 state를 어떻게 채우는지 보여준다.

<br>

- The example API returns a JSON object like this:
  - 예제 API는 다음과 같이 JSON 객체를 반환한다.

```json
{
  "items": [
    { "id": 1, "name": "Apples", "price": "$2" },
    { "id": 2, "name": "Peaches", "price": "$5" }
  ]
}
```

<br>

```react
class MyComponent extends React.Component {
  constructor(props) {
    super(props);
    this.state = {
      error: null,
      isLoaded: false,
      items: []
    };
  }
  
  componentDidMount() {
    fetch("https://api.example.com/items")
    	.then(res => res.json())
    	.then(
      	(result) => {
      		this.setState({
          	isLoaded: true,
          	items: result.items
        	});
    		},
        (error) => {
          this.setState({
            isLoaded: true,
            error
          });
        }
     )
  }
  
  render() {
    const { error, isLoaded, items } = this.state;
    
    if (error) {
      return <div>Error: {error.message}</div>;
    } else if (!isLoaded) {
      return <div>Loading...</div>;
    } else {
      return (
        <ul>
          {items.map(item => (
            <li key={item.name}>
              {item.name} {item.price}
            </li>
          ))}
        </ul>
      );
    }
  }
}
```

------

<br>

<br>