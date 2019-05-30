---
layout: post
title: "단축키로 쉽게 경로 이동하기 on 터미널"
categories: dev
tags: etc
---

# 단축키로 쉽게 경로 이동하기 on 터미널

1. 터미널 실행
   - `cmd` + `space bar` (Spotlight 검색창 열기)
   - `terminal` 입력
2. 명령어 입력
   - `$ nano .bash_profile`
3. 상단에 경로 설정
   - alias `단축키`='cd /Users/`관리자`/Desktop'
   - `alias dk='cd /Users/song/Desktop'` (바탕화면 경로의 단축키를 `dk`로 지정)
4. 설정 저장
   - `control` + `X`
   - `Y` (Yes)
   - `Enter` (저장 완료)

------

<br>

- 이제 터미널 어느 경로에서든 `dk`를 입력하면 바탕화면으로 이동한다.

<br>