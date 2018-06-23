---
layout: post
title: "공식 장고 문서 번역 - 01. Django at a glance (Getting started)"
categories: dev
tags: django
---

[공식 장고 문서 링크](https://docs.djangoproject.com/en/2.0/intro/overview/)

<br>

## Django at a glance

###### Django 훑어보기

<br>

- Because Django was developed in a fast-paced newsroom environment, it was designed to make common Web-development tasks fast and easy.
  - Django는 급변하는 뉴스룸 환경에서 개발되었기 때문에, 일반적인 웹 개발 작업을 빠르고 쉽게 할 수 있도록 설계되었다.
- Here's an informal overview of how to write a database-driven Web app with Django.
  - Django로 데이터베이스 기반 웹 애플리케이션을 작성하는 방법에 대한 약식의 개요가 있다.

<br>

- The goal of this document is to give you enough technical specifics to understand how Django works, but this isn't intended to be a tutorial or reference - but we've got both!
  - 이 문서의 목표는 Django가 어떻게 작동하는지를 이해할 수 있게 기술적 사항들을 충분히 제공하는 것이다.
  - 하지만 튜토리얼이나 참조의 역할을 의도하지는 않는다.
  - 하지만 두 가지 모두 있다.
- When you're ready to start a project, you can [start with the tutorial](https://docs.djangoproject.com/en/2.0/intro/tutorial01/) or [dive right into more detailed documentation](https://docs.djangoproject.com/en/2.0/topics/).
  - 프로젝트를 시작할 준비가 되면, [튜토리얼로 시작](https://docs.djangoproject.com/en/2.0/intro/tutorial01/)하거나 [더 상세한 문서로 뛰어들어라](https://docs.djangoproject.com/en/2.0/topics/).

------

<br>

### Design your model

###### model 설계

<br>

- Although you can use Django without a database, it comes with an [object-relational mapper](https://en.wikipedia.org/wiki/Object-relational_mapping) in which you describe your database layout in Python code.
  - 데이터베이스 없이 Django를 사용할 수 있지만, Python 코드로 데이터베이스 레이아웃을 설명하는 [객체 관계 매핑(ORM)](https://en.wikipedia.org/wiki/Object-relational_mapping)이 포함되어 있다.
- The data-model syntax offers many rich ways of representing your models - so far, it's been solving many years' worth of database-schema problems.
  - 데이터-model 구문은 model을 표현하는 다양한 방법을 제공한다.
  - 지금까지, 수년 동안 데이터베이스-스키마 문제를 해결해왔다.
- Here's a quick example:
  - 다음은 간단한 예제이다.

```python
# mysite/news/models.py

from django.db import models

class Reporter(models.Model):
   full_name = models.CharField(max_length=70)
   
   def __str__(self):
      return self.full_name
   
class Article(models.Model):
   pub_date = models.DateField()
   headline = models.CharField(max_length=200)
   content = models.TextField()
   reporter = models.ForeignKey(Reporter, on_delete=models.CASCADE)
   
   def __str__(self):
      return self.headline
```

------

<br>

### Install it

###### 설치

<br>

- Next, run the Django command-line utility to create the database tables automatically:
  - Django 커맨드-라인 유틸리티를 실행해서 데이터베이스 테이블을 자동으로 만든다.

<br>

> `$ python manage.py migrate`

<br>

- The [migrate](https://docs.djangoproject.com/en/2.0/ref/django-admin/#django-admin-migrate) command looks at all your available models and creates tables in your database for whichever tables don't already exist, as well as optionally providing [much richer schema control](https://docs.djangoproject.com/en/2.0/topics/migrations/).
  - [migrate](https://docs.djangoproject.com/en/2.0/ref/django-admin/#django-admin-migrate) 명령은 사용 가능한 모든 model을 보고 데이터베이스에 아직 존재하지 않는 테이블을 만든다.
  - 뿐만 아니라 [더 많은 스키마 제어](https://docs.djangoproject.com/en/2.0/topics/migrations/)를 옵션으로 제공한다.

------

<br>

### Enjoy the free API

###### 자유로운 API를 즐겨라

<br>

- With that, you've got a free, and rich, [Python API](https://docs.djangoproject.com/en/2.0/topics/db/queries/) to access your data.
  - 이를 통해, 자유롭고 다양한 [Python API](https://docs.djangoproject.com/en/2.0/topics/db/queries/)를 사용해서 데이터에 액세스 할 수 있다.
- The API is created on the fly, no code generation necessary:
  - API는 즉시 생성되며, 코드 생성은 필요하지 않다.

```python
# Import the models we created from our "news" app
>>> from news.models import Article, Reporter

# No reporters are in the system yet.
>>> Reporter.objects.all()
<QuerySet []>

# Create a new Reporter.
>>> r = Reporter(full_name='John Smith')

# Save the object into the database. You have to call save() explicitly.
>>> r.save()

# Now it has an ID.
>>> r.id
1

# Now the new reporter is in the database.
>>> Reporter.objects.all()
<QuerySet [<Reporter: John Smith>]>

# Fields are represented as attributes on the Python object.
>>> r.full_name
'John Smith'

# Django provides a rich database lookup API.
>>> Reporter.objects.get(id=1)
<Reporter: John Smith>
>>> Reporter.objects.get(full_name__startswith='John')
<Reporter: John Smith>
>>> Reporter.objects.get(full_name__contains='mith')
<Reporter: John Smith>
>>> Reporter.objects.get(id=2)
Traceback (most recent call last):
   ...
DoesNotExist: Reporter matching query does not exist.

# Create an article.
>>> from datetime import date
>>> a = Article(pub_date=date.today(), headline='Django is cool',
...	content='Yeah.', reporter=r)
>>> a.save()

# Now the article is in the database.
>>> Article.objects.all()
<QuerySet [<Article: Django is cool>]>

# Article objects get API access to related Reporter objects.
>>> r = a.reporter
>>> r.full_name
'John Smith'

# And vice versa: Reporter objects get API access to Article objects.
>>> r.article_set.all()
<QuerySet [<Article: Django is cool>]>

# The API follows relationships as far as you need, performing efficient
# JOINs for you behind the scenes.
# This finds all articles by a reporter whose name starts with "John".
>>> Article.objects.filter(reporter__full_name__startswith='John')
<QuerySet [<Article: Django is cool>]>

# Change an object by altering its attributes and calling save().
>>> r.full_name = 'Billy Goat'
>>> r.save()

# Delete an object with delete().
>>> r.delete()
```

------

<br>

### A dynamic admin interface: it's not just scaffolding - it's the whole house

###### 동적 관리자 인터페이스: 단순한 발판이 아니다. 집 전체이다.

<br>

- Once your models are defined, Django can automatically create a professional, production ready [administrative interface](https://docs.djangoproject.com/en/2.0/ref/contrib/admin/) - a website that lets authenticated users add, change and delete objects.
  - model이 정의되면, Django는 전문적이고, 생산 준비가 된 [관리자 인터페이스](https://docs.djangoproject.com/en/2.0/ref/contrib/admin/)(인증된 사용자가 객체를 추가, 변경, 삭제할 수 있게 해주는 웹사이트)를 자동으로 생성할 수 있다.
- It's as easy as registering your model in the admin site:
  - 관리자 사이트에서 model을 등록하는 것만큼 쉽다.

```python
# mysite/news/models.py

from django.db import models

class Article(models.Model):
   pub_date = models.DateField()
   headline = models.CharField(max_length=200)
   content = models.TextField()
   reporter = models.ForeignKey(Reporter, on_delete=models.CASCADE)
```

<br>

```python
# mysite/news/admin.py

from django.contrib import admin

from . import models

admin.site.register(models.Article)
```

<br>

- The philosophy here is that your site is edited by a staff, or a client, or maybe just you - and you don't want to have to deal with creating backend interfaces just to manage content.
  - 운영자나 고객에 의해 편집되는 사이트는 다음과 같은 철학을 가지고 있다.
  - 컨텐츠를 관리하기 위해 백엔드 인터페이스를 만드는 데 힘 쏟을 필요가 없다.

<br>

- One typical workflow in creating Django apps is to create models and get the admin sites up and running as fast as possible, so your staff(or clients) can start populating data.
  - Django 앱을 생성하는 전형적인 작업 흐름 중 하나는, model을 생성하고, 관리자 사이트를 가능한 한 빨리 작동시켜 운영자(또는 고객)가 데이터를 입력을 시작할 수 있게 하는 것이다.
- Then, develop the way data is presented to the public.
  - 그런 다음, 데이터가 대중에게 표현되는 방법을 개발해라.

------

<br>

### Design your URLs

###### URL 설계

<br>

- A clean, elegant URL schema is an important detail in a high-quality Web application.
  - 고품질의 웹 애플리케이션에서 깨끗하고 우아한 URL 스키마는 중요한 세부 사항이다.
- Django encourages beautiful URL design and doesn't put any cruft in URLs, like **.php** or **.asp**.
  - Django는 아름다운 URL 설계를 장려하고, **.php**나 **.asp**와 같은 좋지 않은 것을 URL에 넣지 않는다.

<br>

- To design URLs for an app, you create a Python module called a [URLconf](https://docs.djangoproject.com/en/2.0/topics/http/urls/).
  - 앱을 위한 URL을 설계하려면, [URLconf](https://docs.djangoproject.com/en/2.0/topics/http/urls/)라는 Python 모듈을 생성한다.
- A table of contents for you app, it contains a simple mapping between URL patterns and Python callback functions.
  - 앱의 컨텐츠 테이블은 URL 패턴과 Python 콜백 함수 사이의 간단한 매핑을 포함한다.
- URLconfs also serve to decouple URLs from Python code.
  - URLconf는 Python 코드에서 URL을 분리하는 역할도 한다.

<br>

- Here's what a URLconf might look like for the **Reporter/Article** example above:
  - 위의 예제 **Reporter/Article**에 대한 URLconf의 모습은 다음과 같다.

```python
# mysite/news/urls.py

from django.urls import path

from . import views

urlpatterns = [
   path('articles/<int:year>/', views.year_archive),
   path('articles/<int:year>/<int:month>/', views.month_archive),
   path('articles/<int:year>/<int:month>/<int:pk>/', views.article_detail),
]
```

<br>

- The code above maps URL paths to Python callback functions ("views").
  - 위의 코드는 URL 경로를 Python 콜백 함수("views")에 매핑한다.
- The path strings use parameter tags to "capture" values from the URLs.
  - 경로 문자열은 매개변수 태그를 사용해서 URL로부터 값을 "capture"한다.
- When a user requests a page, Django runs through each path, in order, and stops at the first one that matches the requested URL. (If none of them matches, Django calls a special-case 404 view.)
  - 사용자가 페이지를 요청하면, Django는 각 경로를 순서대로 실행하고, 요청된 URL과 일치하는 첫 번째 경로에서 중단한다.
  - (일치하는 것이 없으면, Django는 특별한 경우의 404 view를 호출한다.)
- This is blazingly fast, because the paths are compiled into regular expressions at load time.
  - 경로들은 로드할 때 정규 표현식으로 컴파일되어 있기 때문에 굉장히 빠르다.

<br>

- Once one of the URL patterns matches, Django calls the given view, which is a Python function.
  - URL 패턴 중 하나가 일치하면, Django는 Python 함수인 주어진 view를 호출한다.
- Each view gets passed a request object - which contains request metadata - and the values captured in the pattern.
  - 각 view는 요청 메타 데이터를 포함하는 요청 객체와 패턴에 capture된 값을 전달받는다.

<br>

- For example, if a user requested the URL "/articles/2005/05/39323/", Django would call the function **news.views.article_detail(request, year=2005, month=5, pk=39323)**.
  - 예를 들어, 사용자가 URL "/articles/2005/05/39323/"을 요청하면, Django는 **news.views.article_detail(request, year=2005, month=5, pk=39323)** 함수를 호출한다.

------

<br>

### Write your views

###### view 작성

<br>

- Each view is responsible for doing one of two things: Returning an [HttpResponse](https://docs.djangoproject.com/en/2.0/ref/request-response/#django.http.HttpResponse) object containing the content for the requested page, or raising an exception such as [Http404](https://docs.djangoproject.com/en/2.0/topics/http/views/#django.http.Http404).
  - 각 view는 다음의 두 가지 중 하나를 수행해야 할 책임이 있다.
  - 요청된 페이지의 내용을 포함하는 [HttpResponse](https://docs.djangoproject.com/en/2.0/ref/request-response/#django.http.HttpResponse) 객체를 반환하거나, [Http404](https://docs.djangoproject.com/en/2.0/topics/http/views/#django.http.Http404)와 같은 예외를 발생시킨다.
- The rest is up to you.
  - 나머지는 당신의 몫이다.

<br>

- Generally, a view retrieves data according to the parameters, loads a template and renders the template with the retrieved data.
  - 일반적으로, view는 매개변수에 따라 데이터를 검색하고, template를 로드한 다음, 검색된 데이터로 template를 렌더링 한다.
- Here's an example view for **year_archive** from above:
  - 다음은 위의 **year_archive**에 대한 예제 view다.

```python
# mysite/news/views.py

from django.shortcuts import render

from .models import Article

def year_archive(request, year):
   a_list = Article.objects.filter(pub_date__year=year)
   context = {'year': year, 'article_list': a_list}
   return render(request, 'news/year_archive.html', context)
```

<br>

- This example uses Django's [template system](https://docs.djangoproject.com/en/2.0/topics/templates/), which has several powerful features but strives to stay simple enough for non-programmers to use.
  - 이 예제는 Django의 [template system](https://docs.djangoproject.com/en/2.0/topics/templates/)을 사용한다.
  - 이 template system은 몇 가지 강력한 기능을 가지고 있지만, 프로그래머가 아닌 사람도 사용할 수 있을 만큼 충분히 단순하게 유지하려고 노력한다.

------

<br>

### Design your templates

###### template 설계

<br>

- The code above loads the **news/year_archive.html** template.
  - 위의 코드는 **news/year_archive.html** template을 로딩한다.

<br>

- Django has a template search path, which allows you to minimize redundancy among templates.
  - Django에는 template 검색 경로가 있어서, template 간의 중복성을 최소화할 수 있다.
- In your Django settings, you specify a list of directories to check for templates with [DIRS](https://docs.djangoproject.com/en/2.0/ref/settings/#std:setting-TEMPLATES-DIRS).
  - Django 설정에서, [DIRS](https://docs.djangoproject.com/en/2.0/ref/settings/#std:setting-TEMPLATES-DIRS)가 있는 template을 확인하기 위한 디렉토리 목록을 명시한다.
- If a template doesn't exist in the first directory, it checks the second, and so on.
  - template이 첫 번째 디렉토리에 존재하지 않으면, 두 번째 디렉토리, 그 외 디렉토리를 확인한다.

<br>

- Let's say the **news/year_archive.html** template was found.
  - **news/year_archive.html** template을 찾았다고 가정해보자.
- Here's what that might look like:
  - 그 모양은 다음과 같다.

```python
# mysite/news/templates/news/year_archive.html

{% extends "base.html" %}

{% block title %}Articles for {{ year }}{% endblock %}

{% block content %}
<h1>Articles for {{ year }}</h1>

{% for article in article_list %}
	<p>{{ article.headline }}</p>
   <p>By {{ article.reporter.full_name }}</p>
   <p>Published {{ article.pub_date|date:"F j, Y" }}</p>
{% endfor %}
{% endblock %}
```

<br>

- Variables are surrounded by double-curly braces.
  - 변수는 이중 중괄호로 묶는다.
- **{{ article.headline }}** means "Output the value of the article's headline attribute."
  - **{{ article.headline }}**은 "article의 headline 속성의 값을 출력"을 의미한다.
- But dots aren't used only for attribute lookup.
  - 하지만 점(.)은 속성을 찾는 것에만 사용되는 것은 아니다.
- They also can do dictionary-key lookup, index lookup and function calls.
  - dictionary-key 조회, 인덱스 조회, 함수 호출도 할 수 있다.

<br>

- Note **{{ article.pub_date|date:"F j, Y" }}** uses a Unix-style "pipe" (the "|" character).
  - **{{ article.pub_date|date:"F j, Y" }}**는 Unix-style의 "pipe" ("|" 문자)를 사용한다.
- This is called a template filter, and it's a way to filter the value of a variable.
  - 이 pipe(|)는 template 필터라고 하며, 변수의 값을 필터링하는 방법이다.
- In this case, the date filter formats a Python datetime object in the given format (as found in PHP's date function).
  - 이 경우에는, date 필터는 Python datetime 객체를 주어진 포맷으로 구성한다.
  - (PHP의 date 함수처럼)

<br>

- You can chain together as many filters as you'd like.
  - 원하는 대로 많은 필터를 함께 연결할 수 있다.
- You can write [custom template filters](https://docs.djangoproject.com/en/2.0/howto/custom-template-tags/#howto-writing-custom-template-filters).
  - [사용자 정의 template 필터](https://docs.djangoproject.com/en/2.0/howto/custom-template-tags/#howto-writing-custom-template-filters)를 작성할 수 있다.
- You can write [custom template tags](https://docs.djangoproject.com/en/2.0/howto/custom-template-tags/), which run custom Python code behind the scenes.
  - 사용자 정의 Python 코드를 이면에서 실행하는 [사용자 정의 template 태그](https://docs.djangoproject.com/en/2.0/howto/custom-template-tags/)를 작성할 수 있다.

<br>

- Finally, Django uses the concept of "template inheritance".
  - 마지막으로, Django는 "template 상속"이라는 개념을 사용한다.
- That's what the **{% extends "base.html" %}** does.
  - 그것이 **{% extends "base.html" %}**가 하는 일이다.
- It means "First load the template called 'base', which has defined a bunch of blocks, and fill the blocks with the following blocks."
  - "블록들을 묶어서 정의한 'base'라는 template을 먼저 로딩하고, 다음 블록으로 블록을 채운다"를 의미한다.
- In short, that lets you dramatically cut down on redundancy in template: each template has to define only what's unique to that template.
  - 간단히 말해서, template의 중복성을 극적으로 줄일 수 있다.
  - 각 template은 해당 template에 고유한 것을 정의해야 한다.

<br>

- Here's what the "base.html" template, including the use of [static files](https://docs.djangoproject.com/en/2.0/howto/static-files/), might look like:
  - [정적 파일](https://docs.djangoproject.com/en/2.0/howto/static-files/)의 사용을 포함해서, "base.html" template은 다음과 같다.

```html
# mysite/templates/base.html

{% load static %}
<html>
   <head>
      <title>{% block title %}{% endblock %}</title>
   </head>
   <body>
      <img src="{% static "images/sitelogo.png" %}" alt="Logo" />
      {% block content %}{% endblock %}
   </body>
</html>
```

<br>

- Simplistically, it defines the look-and-feel of the site (with the site's logo), and provides "holes" for child templates to fill.
  - 극단적으로 단순화해서, 사이트의 로고를 사용해서 사이트의 모양과 느낌을 정의하고, 자식 template에 채울 "holes"를 제공한다.
- This makes a site redesign as easy as changing a single file - the base template.
  - 이렇게 하면, 기본 template인 단일 파일을 변경하는 것처럼 사이트를 쉽게 재설계할 수 있다.

<br>

- It also lets you create multiple versions of a site, with different base templates, while reusing child templates.
  - 또한 자식 template을 재사용해서, 다른 기본 template으로, 여러 버전의 사이트를 만들 수 있다.
- Django's creators have used this technique to create strikingly different mobile versions of sites - simply by creating a new base template.
  - Django의 제작자는 이 기술을 사용해서, 간단히 새로운 기본 template을 만드는 것처럼 완전히 다른 모바일 버전의 사이트를 만들었다.

<br>

- Note that you don't have to use Django's template system if you prefer another system.
  - 다른 시스템을 선호한다면, Django의 template 시스템을 사용할 필요가 없다.
- While Django's template system is particularly well-integrated with Django's model layer, nothing forces you to use it.
  - Django의 template 시스템은 Django의 model 레이어와 특히 잘 통합되어 있지만, 어떤 것도 그것을 사용하도록 강요하는 것은 아니다.
- For that matter, you don't have to use Django's database API, either.
  - 그렇다면, Django의 데이터베이스 API 역시 반드시 사용할 필요가 없다.
- You can use another database abstraction layer, you can read XML files, you can read files off disk, or anything you want.
  - 다른 데이터베이스 추상화 레이어를 사용할 수 있고, XML 파일을 읽을 수 있고, 디스크 파일을 읽을 수 있고, 원하는 어떤 것이든 읽을 수 있다.
- Each piece of Django - models, views, templates - is decoupled from the next.
  - Django의 각 조각(model, view, template)은 다음부터 분리된다.

------

<br>

### This is just the surface

###### 이것은 단지 맛보기일 뿐이다

<br>

- This has been only a quick overview of Django's functionality.
  - 이것은 Django의 기능에 대한 간략한 개요이다.
- Some more useful features:
  - 몇 가지 유용한 기능:

<br>

1. A [caching framework](https://docs.djangoproject.com/en/2.0/topics/cache/) that integrates with memcached or other backends.
   - memcached 또는 다른 백엔드와 통합되는 [캐싱 프레임워크](https://docs.djangoproject.com/en/2.0/topics/cache/)
2. A [syndication framework](https://docs.djangoproject.com/en/2.0/ref/contrib/syndication/) that makes creating RSS and Atom feeds as easy as writing a small Python class.
   - 작은 Python 클래스를 작성하는 것처럼 RSS와 Atom 피드를 쉽게 만들 수 있는 [신디케이션 프레임워크](https://docs.djangoproject.com/en/2.0/ref/contrib/syndication/).
3. More sexy automatically-generated admin features - this overview barely scratched the surface.
   - 보다 섹시한 자동 생성 관리자 기능 - 이 개요는 맛보기일 뿐이다.

<br>

- The next obvious steps are for you to [download Django](https://www.djangoproject.com/download/), read [the tutorial](https://docs.djangoproject.com/en/2.0/intro/tutorial01/) and join the community.
  - 다음 단계는 [Django를 다운로드](https://www.djangoproject.com/download/)하고, [튜토리얼](https://docs.djangoproject.com/en/2.0/intro/tutorial01/)을 읽고, [커뮤니티](https://www.djangoproject.com/community/)에 참가하는 것이다.
- Thanks for your interest!
  - 관심에 감사한다.

<br>