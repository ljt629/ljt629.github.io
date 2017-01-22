---
layout:     post
title:      "MyBatis Dynamic Query "
subtitle:   "SQL"
date:       2017-01-20 08:00:00
author:     "Juntaek Lee"
header-img: "img/post-bg-06.jpg"
---

<h2 class="section-heading">if</h2>



<p>
 기본적인 문법구조는 if태그로 감싸주고 조건으로 넣기 위해 "test"라는 속성을 이용한다.
city_zone_id_arr가 null이 아닌경우에만 <if> 태그 안에 작성된 내용이 쿼리에 포함되게 된다.
</p>
<br>

<h2 class="section-heading">choose, when</h2>

<br>
<p>
 MyBatis에서는 choose - when이 switch - case 기능을 대신할 수 있다. 기본적인 문법구조는 choose 태그 안에 when 태그를 조건으로 넣는 구조이다. when은 원하는 조건만큼 넣을 수 있다. <br>
위의 예제를 보면 trip_ratio_type이 'Man'일 경우와 'Woman'일 경우 2가지로 분기하여 동적으로 SQL문을 처리할 수 있다.
</p>


<h2 class="section-heading">foreach</h2>


<p>
 foreach는 SQL문 IN에 들어갈 데이터를 List로 넘겨주고 싶을 때 사용할 수 있다. (굳이 IN이 아니더라도 List를 넘겨주고 싶을 때 사용할 수 있다.) 기본적인 문법구조는 foreach 태그와 속성을 이용한다. <br>
collection : list 혹은 arr 이름 <br>
item : foreach 태그안에서 list의 요소 <br>
index : list의 인덱스 <br>
separtor : 위의 예제에선 IN (1, 2, 3, 4) 처럼 각 요소를 구분하는 ','를 표현한다. <br>
open, close : foreach 문 시작과 끝에 문자열을 넣어준다. <br>
위의 예제는 넘겨준 city_zone_id_arr 배열의 요소값들이 IN (city_zone_id_arr[0], city_zone_id_arr[1], city_zone_id_arr[2], ...... , city_zone_id_arr[n])과 같이 SQL문으로 변환되어 처리된다.
</p>
<br>

<h2 class="section-heading">번외 MyBatis CDATA</h2>
![](http://ljt629.github.io/img/cdata.PNG)
<p>
MyBatis를 사용하다보면 위의 그림처럼 CDATA라는 태그를 볼수가 있다. MyBatis 사용시 < , > , <= , >= , & 와 같은 비교연산자 혹은 부등호를 사용하게 되면 오류가 발생하는데, 이를 처리하기 위해 CDATA를 사용한다. <br>
CDATA로 감싸주면 안에 들어가는 문장을 모두 단순 문자열로 인식하게 된다. <br>

<p>
당연한 이야기인데 CDATA 안에 위에서 설명한 동적 SQL을 포함 시키면 안된다. CDATA 안에 들어가면 단순 문자열로 인식하기 때문에 MyBatis에서 동적 SQL 태그를 인식할 수 없다. 
</P
</p>