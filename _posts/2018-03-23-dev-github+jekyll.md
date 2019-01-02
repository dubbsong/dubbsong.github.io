---
layout: post
title: "GitHub + Jekyll 블로그 만들기"
categories: dev
---

# Jekyll 설치 및 GitHub 온라인 저장소 만들기

<br>

<br>

## 1. Jekyll 설치

- `$ cd ~`


- `$ sudo gem install jekyll`

<br>

## 2. 로컬에서 블로그 생성

- `$ cd Desktop`
- `$ jekyll new dubbsong.github.io`
- `$ cd dubbsong.github.io`
- `$ jekyll serve —-watch` (로컬 서버 실행)
  - 브라우저에서 `http://localhost:4000`로 확인 가능

<br>

## 3. Github에 온라인 저장소 만들기

- 동일한 이름(dubbsong.github.io)으로 Github 온라인 저장소에 저장소 생성
  1. `Repositories` 클릭
  2. `New` 클릭
  3. `Repository name` 설정 후 `Create repository` 클릭
  4. `https://github.com/dubbsong/dubbsong.github.io.git` 복사 (**저장소 URL**)
- `$ cd Desktop`
- `$ cd dubbsong.github.io`
- `$ git init`
- `$ git remote add origin [저장소 URL]`
- `$ git add .`
- `$ git commit -m 'Initialize Blog'`
- `$ git push origin master`
  - 생성된 블로그는 `http://dubbsong.github.io`로 확인 가능 
  - 처음 생성하는 경우 몇 분의 시간이 걸림

<br>