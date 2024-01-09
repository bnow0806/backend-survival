# 5주차 DI & Spring Test

1.  Dependency Injection

    * Factory Pattern
    * Singleton Pattern : 생성자가 여러 차례 호출되더라도 실제로 생성되는 객체는 하나이고 최초 생성 이후에 호출된 생성자는 최초의 생성자가 생성한 객체를 리턴한다.
    * IoC : 제어 반전이 적용된 구조에서는 외부 라이브러리의 코드가 프로그래머가 작성한 코드를 호출한다. \
      스프링이 개발자 대신 객체를 제어하기 위해서는 객체들이 빈(Bean)으로 등록되어있어야 한다.
    * DI (의존성 주입) : IoC에서 관리하고 있는 Bean들 중에서 필요한 것을 객체에 주입하는 것\
      @Autowired 사용
      * 필드 주입
      * 수정자 주입
      * 생성자 주입
    * beanFactory.getBean
    * Test Code 작성 시 given, when, then Template 사용
    * @Bean : 메소드 레벨에서 선언하며, 반환되는 객체(인스턴스)를 개발자가 수동으로 빈으로 등록하는 애노테이션이다.
    * @Component : 클래스 레벨에서 선언함으로써 스프링이 런타임시에 컴포넌트스캔을 하여 자동으로 빈을 찾고(detect) 등록하는 애노테이션
    * @Configuration : 외부라이브러리 또는 내장 클래스를 Bean으로 등록하고자 할 경우 사용
    * spring core 에 관련된 내용


2.  Unit Test

    * V 모델은 개발 생명 주기의 각 단계와 그에 상응하는 소프트웨어 시험의 각 단계의 관계를 보여준다.&#x20;
    * 내적 품질
    * 외적 품질
    * Test Matrix
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

