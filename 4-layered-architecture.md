# 4주차 Layered Architecture

1\. Layered Architecture

* 관심사 분리
* 기능, 웹
  * 웹 : UI, Controller 로 구현
  * 기능 : BL
* UUID
* ULID - 시간을  같이 넣어둔 ID
* TSID
* Controller 안에서Service 불러옴
* Refactoring 기법
* Business Service
* 관심사 분리에 따른 코드 분리

2.Data Access

* dao,dto 분리 이유?
* 데이터를 관리하는 방법 : List, Map
* postDtoMap 으로 처리하면 더 빠름
* interface로 List, Map을 사용하여 CRUD 각각 구현



3\. Domain Model

* Domain model 이란?
* ERD - DAO, DTO 만드는 순으로 개발
* @Test - test code 개발
* assertEquals
* repository를 사용하여, 코드를 짧게 만들 수 있음
  * 타고 들어가서 처리
* repository 에서는 list나 map을 remove,add 등 처리



