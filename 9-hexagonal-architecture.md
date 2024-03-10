# 9주차 Hexagonal Architecture

1. SOLID

* SRP (Single Responsibility Principle, 단일 책임 원칙)
* OCP (Open-Closed Principle, 개방-폐쇄 원칙)
* LSP (Liskov Substitution Principle, 리스코프 치환 원칙)
* ISP (Interface Segregation Principle, 인터페이스 분리 원칙)
* DIP (Dependency Inversion Principle, 의존관계 역전 원칙)



2. Hexagonal Architecture -  [조영호님의 “우아한객체지향” 세미나](https://youtu.be/dJ5C4qRqAgA) 정리

* 연관 관계, 의존 관계, 상속 관계, 실체화 관계
* 주문 플로우
* Domain Objects\
  ![](<.gitbook/assets/Option Group (1).png>)
* 객체 참조를 이용한 연관 관계 구현 시 순환 참조 발생 -> 설계 개선 필요\
  1\) 중간 객체를 이용한 의존서 사이클 끊기\
  ![](<.gitbook/assets/image (4).png>)\
  \
  2\) 인터페이스를 이용한 의존성 역전(전/후)\
  ![](<.gitbook/assets/의존성 사이클 전.png>)  ![](<.gitbook/assets/의존성 사이클 후.png>)\
  \
  3\) 패키지 분리\
  ![](<.gitbook/assets/패키지 의존성.png>)

