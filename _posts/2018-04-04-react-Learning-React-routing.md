---
layout: post
title: "러닝 리액트(Learning React) - 라우팅"
categories: react
tags: react routing
---

###### Learning React - Alex Banks, Eve Porcello

<br>

## CHAPTER 11 리액트 라우터

- 단일 페이지 앱에서는 한 페이지 안에서 모든 일이 벌어진다.
- 브라우저 방문 기록, 책갈피, 이전 페이지, 다음 페이지 등의 기능은 적절한 라우팅 솔루션이 없으면 제대로 작동하지 않을 것이다.
- **라우팅(routing)**은 클라이언트의 요청을 처리할 종말점(endpoint)을 찾는 과정이다.
- JS는 식별한 컨텐트를 가져와서 적절히 사용자 인터페이스를 렌더링할 수 있다.
- 앵귤러(Angular), 엠머(Ember), 백본(Backbone)과 달리 리액트는 표준 라우터가 없다.
- 리액트 라우터는 리액트 앱을 위한 라우팅 솔루션으로 리액트 커뮤니티에 널리 받아들여졌다.

<br>

### 11.1 라우터 사용하기

- 라우터를 사용하면 웹사이트의 각 섹션에 대한 경로를 설정할 수 있다.
- 각 **경로(route)**는 브라우저의 주소창에 넣을 수 있는 종말점을 뜻한다.
- 해시라우터 (HashRouter)
  - react-router-dom은 단일 페이지 앱의 내비게이션 이력을 관리할 수 있는 다양한 방법을 제공한다.
  - HashRouter는 클라이언트를 위해 설계된 라우터다.
  - 주소창의 현재 페이지 경로 뒤에 # 식별자를 입력하면 브라우저는 서버 요청을 보내지 않고 현재 페이지에서 식별자에 해당하는 id 애트리뷰트가 있는 엘리먼트를 찾아서 그 엘리먼트의 위치를 화면에 보여준다.
  - HashRouter를 사용하면 모든 경로 앞에 #을 붙여야 한다.
  - HashRouter는 백엔드가 필요 없는 작은 클라이언트 사이트를 만들 때 유용한 도구다.
  - BrowserRouter는 대부분의 상용 애플리케이션에 적합한 라우터다.
- 하나의 파일 안에 컴포넌트를 한꺼번에 정의해서 export할 수 있다.

```react
export const Home = () =>
	<section className="home">
		<h1>[홈페이지]</h1>
	</section>

export const About = () =>
	<section className="about">
		<h1>[회사소개]</h1>
	</section>

export const Events = () =>
	<section className="events">
		<h1>[이벤트]</h1>
	</section>

export const Products = () =>
	<section className="products">
		<h1>[제품]</h1>
	</section>

export const Contact = () =>
	<section className="contact">
		<h1>[고객지원]</h1>
	</section>
```

```react
import React from 'react'
import { render } from 'react-dom'
import { HashRouter, Route } from 'react-router-dom'
import { Home, About, Events, Products, Contact } from './pages'

window.React = React

render(
	<HashRouter>
   	<div className="main">
      	<Route exact path="/" component={Home} />
         <Route path="/about" component={About} />
         <Route path="/events" component={Events} />
         <Route path="/products" component={Products} />
         <Route path="/contact" component={Contact} />
      </div>
   </HashRouter>,
   document.getElementById('react-container')
)
```

- HashRouter 컴포넌트는 애플리케이션의 경로 컴포넌트로 렌더링된다.
- 각 경로는 HashRouter 내부에 Route 컴포넌트로 정의된다.
- 각 Route 컴포넌트에는 path와 component 프로퍼티가 있다. 주소와 path가 일치하면 component가 표시된다.
- 위치가 /면 라우터는 Home 컴포넌트를 렌더링한다.
- exact라는 프로퍼티는 주소가 경로 주소인 /와 정확히 일치할 때만 Home 컴포넌트를 표시한다는 뜻이다.
- 사용자는 직접 주소를 타이핑해가면서 사이트를 내비게이션하고 싶지는 않다. react-router-dom은 브라우저 링크를 만들어주는 Link라는 컴포넌트를 제공한다.

```react
import { Link } from 'react-router-dom'

export const Home = () =>
	<div className="home">
		<h1>[홈페이지]</h1>
   	<nav>
   		<Link to="about">[회사소개]</Link>
         <Link to="events">[이벤트]</Link>
         <Link to="products">[제품]</Link>
         <Link to="contact">[고객지원]</Link>
   	</nav>
	</div>
```

- 사용자는 링크를 클릭해서 홈페이지 내부 페이지에 접근할 수 있다.
- 이전 버튼을 클릭하면 다시 홈페이지로 이동한다.

<br>

#### 11.1.1 라우터 프로퍼티

- 리액트 라우터는 렌더링하는 컴포넌트에 프로퍼티를 넘긴다.
- 404 Not Found 오류를 처리하기 위해 현재 위치 정보를 사용하자.

```react
export const Whoops404 = ({ location }) =>
	<div className="whoops-404">
		<h1>'{location.pathname}' 경로의 자원을 찾을 수 없습니다.</h1>
	</div>
```

- Whoos404 컴포넌트는 정의되지 않은 경로에 해당하는 주소를 주소창에 입력한 경우에 렌더링된다.
- 일단 렌더링되면 라우터는 경로 객체를 이 컴포넌트에 프로퍼티로 넘긴다.
- Whoops404 컴포넌트를 Route를 사용하는 애플리케이션에 추가하자.

```react
import React from 'react'
import { render } from 'react-dom'
import { HashRouter, Route, Switch } from 'react-router-dom'
import { Home, About, Events, Products, Contact } from './pages'

window.React = React

render(
	<HashRouter>
   	<div className="main">
         <Switch>
      		<Route exact path="/" component={Home} />
   	      <Route path="/about" component={About} />
	         <Route path="/events" component={Events} />
         	<Route path="/products" component={Products} />
         	<Route path="/contact" component={Contact} />
            <Route component={Whoops404} />
			</Switch>
      </div>
   </HashRouter>,
   document.getElementById('react-container')
)
```

- Route에 일치하는 경로가 없는 경우에만 Whoops404를 표시하기 때문에 Switch 컴포넌트를 사용해야 한다.
- 경로와 일치하는 Route가 하나도 없다면 path 프로퍼티가 없는 맨 마지막 Route가 표시된다.
- 모든 Route 컴포넌트를 라우터로 감싸야 한다. 위의 예제에서는 HashRouter를 사용했다.
- Link 컴포넌트를 사용하면 내비게이션을 지원할 수 있다.

<br>

### 11.2 경로 내포시키기

- Route 컴포넌트는 특정 URL과 일치할 때 표시해야 하는 컨텐트와 함께 쓰인다.
- 이 기능을 활용해서 웹앱을 명확한 구조로 로직하면 컨텐트 재사용을 촉진시킬 수 있다.

<br>

#### 11.2.1 페이지 템플릿 사용

- 사용자가 웹앱을 내비게이션하더라도 앱의 UI 중 일부가 계속 같은 위치에 남아 있기를 원하는 경우가 있다.
- children 프로퍼티를 사용하면 리액트 컴포넌트를 템플릿으로 자연스럽게 합성할 수 있다.
- 내부에 들어가면 각 섹션은 똑같은 주 메뉴를 표시해야 한다. 사용자가 내비게이션한 위치에 따라 화면 오른쪽의 컨텐트는 바뀌지만 화면 왼쪽의 컨텐트는 그대로 남아 있어야 한다.
- 내부 페이지에 쓰기 위해 재사용 가능한 PageTemplate 컴포넌트를 만들자.

```react
import HomeIcon from 'react-icons/lib/fa/home'
import { NavLink } from 'react-router-dom'
import './stylesheets/menus.scss'

const selectedStyle = {
   backgroundColor: "white",
   color: "slategray"
}

export const MainMenu = () =>
	<nav className="main-menu">
		<NavLink to="/">
   		<HomeIcon/>
   	</NavLink>
   	<NavLink to="/about" activeStyle={selectedStyle}>
   		[회사소개]
   	</NavLink>
   	<NavLink to="/events" activeStyle={selectedStyle}>
   		[이벤트]
   	</NavLink>
   	<NavLink to="/products" activeStyle={selectedStyle}>
   		[제품]
   	</NavLink>
   	<NavLink to="/contact" activeStyle={selectedStyle}>
   		[고객지원]
   	</NavLink>
	</nav>
```

- MainMenu 컴포넌트는 NavLink 컴포넌트를 사용한다. 이 컴포넌트는 링크가 활성화된 경우 다른 스타일로 표시되는 링크를 만들 때 사용할 수 있다.
- activeStyle 프로퍼티를 사용해 해당 링크가 현재 선택되었거나 활성화되었음을 표시할 때 사용할 CSS를 지정할 수 있다.
- MainMenu 컴포넌트는 PageTemplate 컴포넌트 안에 들어간다.

```react
import { MainMenu } from './ui/menus'

...

const PageTemplate = ({children}) =>
	<div className="page">
		<MainMenu />
   	{children}
	</div>
```

- PageTemplate 컴포넌트에 있는 children은 각 섹션이 렌더링될 부분이다.
- PageTemplate을 사용해 각 섹션을 합성할 수 있다.

```react
export const Events = () =>
	<PageTemplate>
		<section className="events">
			<h1>[이벤트]</h1>
		</section>
	</PageTemplate>
export const Products = () =>
	<PageTemplate>
		<section className="products">
			<h1>[제품]</h1>
		</section>
	</PageTemplate>
export const Contact = () =>
	<PageTemplate>
		<section className="contact">
			<h1>[고객지원]</h1>
		</section>
   </PageTemplate>
export const About = ({ match }) =>
	<PageTemplate>
   	<section className="about">
   		<h1>[회사소개]</h1>
   	</section>
   </PageTemplate>
```

- 이 웹사이트의 내부 페이지를 내비게이션하면 화면 오른쪽의 컨텐트가 바뀐다.

<br>

#### 11.2.2 하위 섹션과 하위 메뉴

- 전체 개요 및 계층 구조를 반영하는 새 경로
  - 홈페이지 `http://localhost:3000/`
    - 회사소개 `http://localhost:3000/#/about`
      - 회사 (디폴트) `http://localhost:3000/#/about`
      - 연혁 `http://localhost:3000/#/about/history`
      - 서비스 `http://localhost:3000/#/about/services`
      - 위치 `http://localhost:3000/#/about/lacation`
    - 이벤트 `http://localhost:3000/#/events`
    - 제품 `http://localhost:3000/#/products`
    - 고객지원 `http://localhost:3000/#/contact`
  - 404 오류 페이지 `http://localhost:3000/#/foo-bar`
- '회사소개' 섹션의 하위 메뉴를 만들자.

```react
358p
```


