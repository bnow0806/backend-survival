# 5주차 DI & Spring Test

1.  Dependency Injection

    * Factory 생성 이유?
    * IoC DI 차이
    * beanFactory.getBean
    * when, then
    * constructorArgs
    * 생성자 의존성
    * @Component 사용 이유
    * @ComponentScan
    * @Configuration&#x20;
    * springcore


2.  Unit Test

    * V model
    * 내적 품질, 외적 품질
    * Test Matrix. Test 영역이 넓다.
    * JUnit5
    * NewtonMethod Test 방법?
    * @Test, @DisplayName(“ ”)
    * Test Pyramid


3.  Spring Test(IntegrationTest)

    * restTemplate.postForLocation(url, postDto); //서버를 실행시켜 테스트하는 방법
    * String body = restTemplate.getForObject(url, String.class);
    * MockMvc를 써서 Http 요청을 흉내낼 수 있다.
    * MockMvc 시 DB 연동이 되는가?
    * @SpyBeanmock
    * Mvc.perform & verify
    * @Mockbean
    * UnitTest vs IntegrationTest : UnitTest가 더 중요.


4. TDD
   * ref 강의 듣기

