---
layout:     post
title:      "Template Method Pattern / Factory Method Pattern "
subtitle:   "Design Pattern"
date:       2017-01-13 08:00:00
author:     "Juntaek Lee"
header-img: "img/post-bg-06.jpg"
---

<h2 class="section-heading">Template Method Pattern</h2>

<p>1. 정의 </p>
<p>- 변하지 않는 기능은 슈퍼클래스가 구현하고 상속하여 사용한다.<br>- 자주 변경되는 기능이나 확장될 기능은 Abstract로 선언하여 하위 클래스가 각자 구현한다.</p>

![](http://ljt629.github.io/img/factory-method-pattern.png)
<br>
<p> 출처 : https://byulmuri.wordpress.com/tag/design-pattern-2/ </p>

<p>2. 왜 쓸까 </p>
<p>
- 로직의 공통화 (공통된 기능 수정 시 편함)<br>
</p>

<p>3. 주의할 점 </p>
<p>
- 상속을 이용하므로 추상메소드가 필요한 클래스들마다 상속받아야 한다. 
</p>

<h2 class="section-heading">Factory Method Pattern</h2>

<p>1. 정의 </p>
<p>
- 인스턴스 생성하는 것을 템플릿메소드 패턴으로 구성하는 것과 같음.<br>
- 객체를 생성하는 인터페이스 정의하고 실제로 어떤 클래스의 인스턴스를 만들지는 서브클래스가 결정하도록 하는 것.
</p>

![](http://ljt629.github.io/img/template-method-pattern.png)
<br>
<p> 출처 : http://kimsunzun.tistory.com/entry/Template-Method-패턴-1 </p>

<p>2. 왜 쓸까 </p>
<p>
- 어떤 객체를 생성할지와 무관하게 동일한 형태로 코딩가능<br>
- 직접 생성자를 호출하여 객체 생성하는 것보다 확장성이 좋다.
</p>

