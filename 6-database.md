# 6주차 Database

6주차

1. DB

* DBMS : 데이터베이스 내 데이터를 접근할 수 있도록 해주는 소프트웨어 도구의 집합
* 데이터베이스 언어&#x20;
  * DDL(Data Definition Language) - Schema
  * DML(Data Manipulation Language) - Query, Command
  * DCL(Data Control Language) - Grant, Revoke, Commit, Rollback
* Data Model : 논리적 데이터 모델, 개념적 데이터 모델, 물리적 데이터 모델



2. Relational Model : 가장 인기 있는 논리적 데이터 모델

* 관계형 모델 : 컬럼, 로우를 이루는 하나 이상의 테이블로 정리\
  고유키가 각 로우를 식별한다. 로우는 튜플로 부른다.
* 관계형 모델에서 사용되는 개념
  * Attribute : 이름과 타입으로 구성
  * Tuple : (속성,값) 쌍의 집
  * Relation : 튜플의 집합
    * Body
    * Heading



3. Relational Algerbra

* 연산 : 하나 이상의 Relation으로 새로운 Relation을 만들 수 있다.
* Projection : SELECT ...  FROM ...
* Selection : SELECT ... FROM ... WHERE ...
* Cartesian Product : SELECT ... FROM r1, r2
*   이항 연산자

    * JOIN
    * SELECT items.name AS name, usage, people.gender FROM items JOIN people ON items.person\_name = people.name



4. Entity Relational Model : 가장 인기 있는 개념적 데이터 모델

* ERM : 엔터티 - 관계 모델은 특정 지식 영역에서 상호 관련된 관심 사항을 설명
*   ERD : ER 모델을 시각화하는 방법

    <figure><img src=".gitbook/assets/image (2).png" alt=""><figcaption></figcaption></figure>
* Cardinality(data modeling) : 한 테이블의 행과 다른 테이블 행간의 수치 관계. 일대일, 일대다, 다대다 등이 있음

5. JDBC

* Java에서 RDBMS를 사용할 수 있게 해주는 API
* Connection 방법 숙지

&#x20;  1\) application.properties

```
String url = "jdbc:postgresql://localhost:5432/postgres";

Properties properties = new Properties();
properties.put("user", "postgres");
properties.put("password", "password");

Connection connection = DriverManager.getConnection(url, properties);
```

&#x20;  2\) build.gradle

<pre><code><strong>implementation 'org.postgresql:postgresql:42.5.4'
</strong></code></pre>

&#x20;  3\) example

```

Statement statement = connection.createStatement();

String query = "SELECT * FROM people";

ResultSet resultSet = statement.executeQuery(query);

while (resultSet.next()) {
	String name = resultSet.getString("name");
	
	System.out.println(name);
}
```



6. JDBC Template : JDBC 코어 페키지의 중심 클래스

* Spring Initializer : spring dev tools, jdbc api, postgresql 의존성 선택
* Command Line Runner을 통해 JDBC 동작시험 가능

```
@Component
public class AppRunner implements CommandLineRunner {
	private final JdbcTemplate jdbcTemplate;

	public AppRunner(JdbcTemplate jdbcTemplate) {
		this.jdbcTemplate = jdbcTemplate;
	}

	@Override
	public void run(String... args) throws Exception {
		String sql = "SELECT name FROM people";
		
		jdbcTemplate.query(sql, resultSet -> {
			while (resultSet.next()) {
				String name = resultSet.getString("name");
				System.out.println(name);
			}
		});
	}
}
```

* TransactionTemplate  안에  jdbcTemplate 을 넣어서 트랜잭션을 관리할 수 있다.



