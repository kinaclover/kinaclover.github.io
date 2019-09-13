---
layout: post
title: "Spring Boot 시작하기 - 01"
date: 2019-09-13 20:20 +0900
categories: Vue.js
---

---  
2019.09.13.  
스프링부트를 제대로 사용해 보고 싶은 생각은 많았으나,  
이런저런 핑계로 계속 미뤄오다 이번에 시작해본다.

우선은 책의 예제를 쭉 따라가보며 작성을 해 보고, 하나하나 분석해볼 예정이다.  
_[(스프링부트 시작하기/프로그래밍인사이트)](https://github.com/insightbook/Spring-Boot)_  
_[(작성중인 실습소스)](https://github.com/kinaclover/SB_Board)_

이 곳은 아직 꾸준한 작성은 커녕 정리도 제대로 안되어있기에
일단 기록성으로 글을 남겨둔다.

---

### Spring Boot?
- 현재 (적어도 한국에서) 널리 쓰이는 Spring Framework 를 더 효율적으로 사용하기 위해 만들어 짐
- 직접 작성해야만 했던 여러 설정들을 미리 구성해 놓았으며, 라이브러리들 또한 미리 조합되어 있음
- 별도의 서버 설치 없이 바로 개발에 들어갈 수 있음

### IDE
- 무료인 Eclipse 를 이용할 예정
- Eclipse market 에서 제공하는 STS 플러그인 사용
- 기본적으로 Spring Boot 에는 Maven 이 내장되어있음
    - 하지만, 이 실습에서는 Gradle 을 활용할 예정
    - Maven 의 단점을 보완(종속성 관리, 라이브러리 추가시의 문제 등등)

### DTO/VO
- 책에서 DTO와 VO는 '다르다' 라고 설명하나, 자세한 설명은 생략함
- VO (**V**alue **O**bject)
    - **데이터 그 자체**
    - Read-Only

- DTO (**D**ata **T**ransfer **O**bject)
    - 전송되는 데이터의 **객체**
    - VO 와 같은 역할을 가지나, 추가적으로 다른 시스템으로의 전달 작업을 처리함

### Lombok
- 자바 클래스에서 흔히 사용하는 코드들을 어노테이션을 활용하여 자동으로 만들어주는 라이브러리
- getter/setter 를 만들어주는 데에 사용해봄(편리함!)

### Logback
- log4j 의 계승작 (개발자가 같음)
- log4j 를 기반으로 다시 작성된 라이브러리
- 보다 향상된 성능을 가졌으며, 서버의 재시작 없이 변경된 설정 적용 가능

### MyBatis 의 활용
- DAO 를 사용하는 것 보다 SqlSessionDaoSupport 나 SqlSessionTemplate 을 사용하는것을 권장함
    - 이를 통해 매퍼를 생성하여 사용하면 일일이 DAO를 만들지 않고, Interface 만을 이용하여 좀 더 편하게 개발할 수 있음
- @Mapper 어노테이션을 이용하여 매퍼 인터페이스 생성
    - 해당 매퍼를 namespace 로 지정하여 xml 작성
    - 메서드의 이름과 sql ID 를 일치시키면 사용 가능