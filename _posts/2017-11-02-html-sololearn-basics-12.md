---
layout: post
title: "SoloLearn HTML 번역 - 12. Blog Project: My Schedule (Basics)"
categories: dev
tags: html
---

## My Schedule

- Use table tags to add a table to your blog that represents your daily learning schedule.
  - 테이블 태그를 사용해서 일일 학습 스케줄을 나타내는 테이블을 블로그에 추가해라.
- The `<th>` tags represent the table headers.
  - `<th>` 태그는 테이블 header를 나타낸다.
  - `<th>`: Defines a header cell in a table

```html
<h1><span>My Coding Schedule</span></h1>
<table>
<tr>
  <th>Day</th>
  <th>Mon</th>
  <th>Tue</th>
  <th>Wed</th>
  <th>Thu</th>
  <th>Fri</th>
</tr>
<tr>
  <td>8-8:30</td>
  <td class="selected">Learn</td>
  <td></td>
  <td></td>
  <td></td>
  <td></td>
</tr>
<tr>
  <td>9-10</td>
  <td></td>
  <td class="selected">Practice</td>
  <td></td>
  <td></td>
  <td></td>
</tr>
<tr>
  <td>1-1:30</td>
  <td></td>
  <td></td>
  <td class="selected">Play</td>
  <td></td>
  <td></td>
</tr>
<tr>
  <td>3:45-5</td>
  <td></td>
  <td></td>
  <td></td>
  <td class="selected">Code</td>
  <td></td>
</tr>
<tr>
  <td>6-6:15</td>
  <td></td>
  <td></td>
  <td></td>
  <td></td>
  <td class="selected">Discuss</td>
</tr>
</table>
```

[코드 및 결과 확인 링크](https://code.sololearn.com/1148/#html)

<br>

- The empty `<td>` tags represent empty table cells.
  - 빈 `<td>` 태그는 빈 테이블 cell을 나타낸다.
- They're necessary because they maintain the table's structure.
  - 테이블의 구조를 유지하기 때문에 필요하다.

------

<br>

# QUIZ

- Fill in the blanks to create a valid table:
  - 유효한 테이블을 만들기 위해서 빈칸을 채워라.

```html
<table>
   <tr>
   	<td>A</td>
      <td>B</td>
   </tr>
</table>
```

<br>