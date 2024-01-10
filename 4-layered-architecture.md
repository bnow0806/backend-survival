# 4주차 Layered Architecture

1\. Layered Architecture

* 관심사 분리 :  관심사 분리(separation of concerns, SoC)는 [컴퓨터 프로그램](https://ko.wikipedia.org/wiki/%EC%BB%B4%ED%93%A8%ED%84%B0\_%ED%94%84%EB%A1%9C%EA%B7%B8%EB%9E%A8)을 구별된 부분으로 분리시키는 디자인 원칙으로, 각 부문은 개개의 [관심사](https://ko.wikipedia.org/wiki/%EA%B4%80%EC%8B%AC%EC%82%AC)를 해결한다.
*   다층 구조

    1. Presentation
    2. Domain
    3. Data

    : presentation (UI), domain logic (aka business logic), and data access.
* 기능, 웹 분리
  * 웹 : UI, Controller 로 구현
  * 기능 : Business Logic
  * Controller 안 에서 Service 불러옴
* ID
  * UUID - Random ID
  * ULID - 시간을  같이 넣어둔 ID
  * TSID - ULID 개선 ID
*   Service

    * 각 기능을 개별 메서드로 분리하고, 이를 모아서 PostService 클래스로 모아준다.
    * Refactoring 기법
    * 관심사 분리에 따른 코드 분리



2. Data Access

* Entity : DB 테이블과 매핑되는 클래스
* DTO : 계층 간의 데이터 교환을 위한 객체
* DAO : DB를 사용해 데이터를 조회하거나 조작하기 위한 객체

<figure><img src=".gitbook/assets/image (1).png" alt=""><figcaption></figcaption></figure>

*   DAO, DTO 분리 이유

    * DB 컬럼명과 웹브라우저에서 보이는 필드명이 같으면&#x20;

    &#x20;      SQL Injection 공격에 취약하므로 DB컬럼명과 웹에서 보여지는 필드명을 다르게 한다.
* 데이터를 관리하는 방법 : List, Map
  * PostDAO라는 인터페이스를 만들고, PostListDAO와 PostMapDAO로 구현한다.
  * postMapDAO (HashMap)으로 처리하면 더 빠름



3\. Domain Model

* Domain\
  : 소프트웨어로 해결하고자 하는 영역
*   Domain model

    : 특정 도메인을 개념적으로 표현한 것
*   데이터베이스 주도 개발

    : ERD - DAO, DTO 만드는 순으로 개발
* DDD(Domain Driven Design) 개발\
  : 도메인 모델을 먼저 만들고, JPA Entity를 따로 만들어서 도메인 모델과 매핑한다.
* Unit Test - @Test, assertEquals 사용
* repository 를 사용하여, 보여주는 코드를 짧게 만들 수 있음
  * repository 에서 list나 map을 remove, add 하는 행위를 처리



