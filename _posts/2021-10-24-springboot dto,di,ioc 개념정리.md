---
title:springboot dto,di,ioc 개념정리
categories: [dev]
comments: true
---
springboot dto,di,ioc 개념정리
=============


1.DTO(Data transfer object)
---------------
DTO란 데이터 전송객체,즉, 웹서비스의 클라이언트와 서버를 관리하고,데이터의 전송을 담당하는 클래스를 의미한다.

주로 웹서비스의 백엔드 구축에 많이 사용됩니다.

(백엔드란?:웹사이트나 웹 애플리케이션 또는 모바일 솔루션의 프로세스와 관련된 서버 측(Server-side)과 데이터베이스를 관리)

```java
@Getter
@NoArgsConstructor
public class PostSaveRequestDto {
    private String title;
    private String content;
    private String author;
}
```
 DTO 클래스는 클라이언트의 Request_body에 있는 Entity의 필드들을 담아 
 
 다음 요청을 처리하는 곳으로 데이터를 넘겨준다.
 
 반대로 서버에서 클라이언트로 응답을 보내때도 이 방법을 사용한다.

2.DI(Dependency Injection)
-------------
DI란 의존성 주입을 의미한다.

@Autowired를 이용하여 주입한다.

(의존성 주입이란: 하나의 객체가 다른 객체의 의존성을 제공하는 것)

스프링에서는 IOC(Inversion Of Control) 컨테이너를 이용하여, 외부에서 객체를 생성하여, 외부에서 객체를 생성하여 의존성을 주입하는 방식을 이용한다.

객체 사이의 의존 관계를 스프링 설정 파일에 등록 된 정보를 바탕으로 컨테이너가 자동으로 처리해주어 편리하다는 장점이있다.


```java
@RequiredArgsConstructor
@Service
public class ExampleService {
    private final PracticeService practiceService;
}

```
->생성자 주입 방법(RequiredArgsConstructor를 이용)

3.IOC(Inversion Of Control)
--------------

IOC를 직역하면 '제어의 역전'이라는 뜻이 된다.

이는 제어권이 컨테이너로 넘어가게 되어서 제어권의 흐름이 바뀌는 것,

즉,내가 사용할 의존성은 이미 만들어져 있는 것에 연결한다는 것을 의미한다.

따라서 IOC가 없다면 @Autowired를 이용한 의존성 주입 또한 할 수 없다.

IoC 컨테이너는 스프링에서 쓰이는 여러 객체들을 생성, 관리하는 객체로 사용된다.

```java
public class ExampleService {
    private ExampleRepository exampleRepository = new ExampleRepository();
}
```
위 코드는 ExampleService 에서 new를 통해 의존 객체를 직접 생성하는 것이다.





참고:https://gardeny.tistory.com,

https://bestpractice80.tistory.com/51,

https://velog.io/@ayoung0073/springboot-IoC%EC%A0%9C%EC%96%B4%EC%9D%98-%EC%97%AD%EC%A0%84%EC%99%80-DI%EC%9D%98%EC%A1%B4%EC%84%B1-%EC%A3%BC%EC%9E%85
