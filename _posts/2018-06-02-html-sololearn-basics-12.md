---
layout: post
title: "(Basics 12) 블로그 프로젝트: My Schedule"
categories: html
---

###### [SoloLearn](https://www.sololearn.com/) HTML 번역

<br>

# Blog Project: My Schedule

###### 블로그 프로젝트: My Schedule

<br>

- Use table tags to add a table to your blog that represents your daily learning schedule.
  - 테이블 태그를 사용해서 일일 학습 스케줄을 나타내는 테이블을 블로그에 추가해라.
- The \<th> tags represent the table headers.
  - \<th> 태그는 table header를 나타낸다.

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

[코드 실행 확인](https://code.sololearn.com/1148/#html)

<br>

- The empty \<td> tags represent empty table cells.
  - 빈 \<td> 태그는 빈 테이블 cell을 나타낸다.
- They're necessary because they maintain the table's structure.
  - 빈 테이블은 테이블의 구조를 유지하기 때문에 필요하다.

<br>