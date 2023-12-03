# 3주차 DTO, JSON, CORS

### 1. DTO

* IPC 통신
  * 소캣
  * RPC, RMI 기술
* DTO
  * IoC Container and Beans
  * JAVA Bean
* Tier간 통신
  * FE <-> BE
  * DTO 객체를 직렬화 → XML, JSON
  * BE <-> DB
  * Value Object, DTO

### 2. 직렬화&#x20;

* 직렬화. 비직렬화
  * 생성 : DTO -> 변환기 -> JSON
  * 해석 : JSON -> 변환기 -> DTO

### 3. Jackson ObjectMapper

*   예시

    *   public PostDto create(@RequestBody String body){

        PostDto postDto = objectMapper.readValue(body, PostDto.class)

        return postDto;

        }

        // String이면, Jackson을 이용하여  json으로 변환해준다.
    *   public PostDto create(@RequestBody PostDto postDto){

        return postDto;

        }

    &#x20;      // Dto로 선언하면, Jackson이 알아서 json으로 변환해준다.

### 4. CORS

* CORS
* SAME ORIGIN POLICY
  * Host, Origin
* CROSS ORIGIN POLICY
  * @CrossOrigin(“http://localhost:3000”) 적용 후, 아래 코드 실행
  *   private List\<postDtos> postDtos = new ArrayList(List.of(

      new PostDto(“1”, “제목”, “테스트입니다.”);
  *   @DeleteMapping(“/{id}”) 에서

      postDtos.remove(postDto);
* WebMvcConfigurer
  * 전 영역에서 적용 시 .allowedOrigins();&#x20;
  * .allowedMethods();
