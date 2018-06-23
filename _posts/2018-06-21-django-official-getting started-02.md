---
layout: post
title: "공식 장고 문서 번역 - 02. Quick install guide (Getting started)"
categories: dev
tags: django
---

[공식 장고 문서 링크](https://docs.djangoproject.com/en/2.0/intro/install/)

<br>

## Quick install guide

###### 빠른 설치 가이드

<br>

- Before you can use Django, you'll need to get it installed.
  - Django를 사용하기 전에, 설치가 필요하다.
- We have a complete installation guide that covers all the possibilities; this guide will guide you to a simple, minimal installation that'll work while you walk through the introduction.
  - 모든 가능성을 다루는 완벽한 설치 가이드가 있다.
  - intro를 진행하는 동안 작동할 수 있는 간단하고 최소한의 설치를 가이드 할 것이다.

------

<br>

### Install Python

###### Python 설치

<br>

- Being a Python Web framework, Django requires Python.
  - Django는 Python 웹 프레임워크이므로, Python이 필요하다.
- See [What Python version can I use with Django?](https://docs.djangoproject.com/en/2.0/faq/install/#faq-python-version-support) for details.
  - 자세한 내용은 [Django에서 어떤 Python 버전을 사용할 수 있을까?](https://docs.djangoproject.com/en/2.0/faq/install/#faq-python-version-support)를 보자.
- Python includes a lightweight database called [SQLite](https://sqlite.org/index.html) so you won't need to set up a database just yet.
  - Python은 [SQLite](https://sqlite.org/index.html)라는 경량의 데이터베이스를 포함하므로, 아직 데이터베이스를 설정할 필요가 없다.

<br>

- Get the latest version of Python at https://www.python.org/downloads/ or with your operating system's package manager.
  - https://www.python.org/downloads/ 또는 운영체제의 패키지 매니저에서 Python의 최신 버전을 다운로드해라.

<br>

- You can verify that Python is installed by typing **python** from your shell; you should see something like:
  - shell에서 **python**을 입력해서 Python이 설치되었는지 확인할 수 있다.
  - 다음과 같이 보일 것이다.

```python
Python 3.4.x
[GCC 4.x] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>>
```

------

<br>

### Set up a database

###### 데이터베이스 설정

<br>

- This step is only necessary if you'd like to work with a "large" database engine like PostgreSQL, MySQL, or Oracle.
  - 이 단계는 PostgreSQL, MySQL, Oracle과 같은 "대규모" 데이터베이스 엔진을 사용하려는 경우에만 필요하다.
- To install such a database, consult the [database installation information](https://docs.djangoproject.com/en/2.0/topics/install/#database-installation).
  - 이러한 데이터베이스를 설치하려면, [데이터베이스 설치 정보](https://docs.djangoproject.com/en/2.0/topics/install/#database-installation)를 참조해라.

------

<br>

### Remove any old versions of Django

###### Django의 이전 버전을 제거해라

<br>

- If you are upgrading your installation of Django from a previous version, you will need to [uninstall the old Django version before installing the new version](https://docs.djangoproject.com/en/2.0/topics/install/#removing-old-versions-of-django).
  - 이전 버전에서 Django의 설치를 업그레이드 하는 경우, 새 버전을 설치하기 전에 이전의 Django 버전을 제거해야 한다.

------

<br>

### Install Django

###### Django 설치

<br>

- You've got three easy options to install Django.
  - Django를 설치하는 세 가지의 쉬운 옵션이 있다.

<br>

1. [Install an official release](https://docs.djangoproject.com/en/2.0/topics/install/#installing-official-release). This is the best approach for most users.
   - [공식 릴리즈를 설치](https://docs.djangoproject.com/en/2.0/topics/install/#installing-official-release)해라. 대부분의 사용자에게 가장 좋은 접근 방법이다.
2. Install a version of Django [provided by your operating system distribution](https://docs.djangoproject.com/en/2.0/topics/install/#installing-distribution-package).
   - [운영체제 배포판에서 제공](https://docs.djangoproject.com/en/2.0/topics/install/#installing-distribution-package)하는 Django 버전을 설치해라.
3. [Install the latest development version](https://docs.djangoproject.com/en/2.0/topics/install/#installing-development-version). This option is for enthusiasts who want the latest-and-greatest features and aren't afraid of running brand new code. You might encounter new bugs in the development version, but reporting them helps the development of Django. Also, releases of third-party packages are less likely to be compatible with the development version than with the latest stable release.
   - [최신 개발 버전을 설치](https://docs.djangoproject.com/en/2.0/topics/install/#installing-development-version)해라. 이 옵션은 최신 기능을 원하고, 완전 새로운 코드를 실행하는 것을 두려워하지 않는 애호가에게 적합하다. 개발 버전에서 새로운 버그가 발생할 수 있지만, report 하면 Django를 개발하는 데 도움이 된다. 또한, 타사 패키지의 릴리즈는 최신의 안정적인 릴리즈보다 개발 버전과 호환될 가능성이 적다.

<br>

> **Always refer to the documentation that corresponds to the version of Django you're using!**
>
> **항상 사용 중인 Django 버전에 해당하는 문서를 참조해라.**

> If you do either of the first two steps, keep an eye out for parts of the documentation marked **new in development version**.
>
> 처음 두 단계 중 하나를 수행하는 경우, 문서에서 **new in development version**라고 표시된 부분을 주의해서 봐라.
>
> That phrase flags features that are only available in development versions of Django, and they likely won't work with an official release.
>
> 이 구문 flag는 Django의 개발 버전에서만 사용할 수 있는 기능을 제공하며, 공식 릴리즈에서는 작동하지 않을 수 있다.

------

<br>

### Verifying

###### 확인

<br>

- To verify that Django can be seen by Python, type **python** from your shell.
  - Django가 Python에서 볼 수 있는지 확인하려면, shell에서 **python**을 입력해라.
- Then at the Python prompt, try to import Django.
  - 그런 다음, Python prompt에서 Django를 import 해라.

```python
>>> import django
>>> print(django.get_version())
2.0
```

<br>

- You may have another version of Django installed.
  - 다른 버전의 Django가 설치되어 있을 수 있다.

------

<br>

### That's it!

- That's it - you can now [move onto the tutorial](https://docs.djangoproject.com/en/2.0/intro/tutorial01/).
  - 이제 튜토리얼로 이동할 수 있다.

<br>