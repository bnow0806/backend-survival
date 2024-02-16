# 7주차 JPA

7주차

1. ORM

* SQL 문 자동 생성. 비지니스 로직에 집중 가능
* JPA - Relational Mapping, Aggregating Mapping 지원\
  \-> Object 와 Relational Mapping 함



2. Hibernate

* JPA Test : entityManager 활용
* entityManagerFactory, entityManager 생성
* entityManager.persist() : 저장
* transaction.begin , transaction commit
* update는 따로 entityManager 쓰지 않아도, transaction commit 시 반영됨
* jpql = “ … “ 쿼리 직접 실행



3. Embeddable

* @Embeddable 다른데서 쓸 수 있는 Type 선언
* Gender.male, Gender.female
* @Embedded 를 사용해서 받음
* equals and hashcode 의미?



4. Relationship Mapping

* CASCADEType.ALL, orphanRemoval=true
* @JoinColumn, @OrderBy
* 1대다 관계 연결, JpaTest 에서 추가 삭제 후 값 확인
* 문제점
  * persistence.xml 추가
  * EntityManager 불편
  * Transaction 관리 불편\


5. Spring Data JPA

* PersonRepository extends CRUDRepository\<T,ID>
* T는 Entity의 타입클래스이고 ID는 P.K 값의 Type이다.
*   @Transactional를 Test 에 넣으면, Test 후 Rollback 됨

    * save, delete

