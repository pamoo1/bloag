---
title: springboot dto,di,ioc 개념정리
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

(의존성 주입이란: 하나의 객체가 다른 객체의 의존성을 제공하는 것)

@Autowired 어노테이션을 이용하여 주입한다.

(어노테이션이란?:Annotation은 사전적 의미로는 주석이라는 뜻으로,

Annotation은 코드 사이에 주석처럼 쓰이며 특별한 의미, 기능을 수행하도록 하는 기술)

스프링에서는 IOC(Inversion Of Control) 컨테이너를 이용하여, 외부에서 객체를 생성하여, 외부에서 객체를 생성하여 의존성을 주입하는 방식을 이용한다.

객체 사이의 의존 관계를 스프링 설정 파일에 등록 된 정보를 바탕으로 컨테이너가 자동으로 처리해주어 편리하다는 장점이있다.

@Autowired 어노테이션은 Spring에게 의존성을 주입하라는 지시자 역할로 쓰이는데 
생성자, 필드, 세터에 붙일 수 있다.


첫번째,
```java
@Component
public class SampleController {
    private SampleRepository sampleRepository;
 
    @Autowired
    public SampleController(SampleRepository sampleRepository) {
        this.sampleRepository = sampleRepository;
    }
}
```
->생성자 주입 방법

생성자에 @Autowired 어노테이션을 붙여 의존성을 주입받을 수 있다.

두번째,

```java
@Component
public class SampleController {
    @Autowired
    private SampleRepository sampleRepository;
}

```
->필드 주입 방법

변수 선언부에 @Autowired 어노테이션을 붙여 의존성을 주입받을 수 있다.

```java
@Component
public class SampleController {
    private SampleRepository sampleRepository;
 
    @Autowired
    public void setSampleRepository(SampleRepository sampleRepository) {
        this.sampleRepository = sampleRepository;
    }
}

```
Setter 메소드에 @Autowired 어노테이션을 붙여서 의존성을 주입받을 수 있다.

이 중 가장 많이 사용되는 방법은 생성자를 통한 의존성 주입이다.

이 방법이 많이 사용되는 이유는 필수적으로 사용해야하는 

의존성 없이는 인스턴스를 만들지 못하도록할 수 있기때문이다.

(인스턴스(instance)란?: 템플릿이 실제로 구현된 것
(템플릿의 예로는 클래스 객체와 컴퓨터 프로세스 등을 들 수 있다.))

3.IOC(Inversion Of Control)
--------------

IOC를 직역하면 '제어의 역전'이라는 뜻이 된다.

이는 제어권이 컨테이너로 넘어가게 되어서 제어권의 흐름이 바뀌는 것,

즉,내가 사용할 의존성은 이미 만들어져 있는 것에 연결한다는 것을 의미한다.

따라서 IOC가 없다면 @Autowired를 이용한 의존성 주입 또한 할 수 없다.

IoC 컨테이너는 스프링에서 쓰이는 여러 객체들을 생성, 관리하는 객체로 사용된다.

의존 객체를 생성하는 방법에는 크게 세가지가 있는데,
```java
public class ExampleService {
    private ExampleRepository exampleRepository = new ExampleRepository();
}
```
첫번째 방법은 ExampleService 에서 new를 통해 의존 객체를 직접 생성하는 것이다.

```java
@RequiredArgsConstructor
@Service
// @Service라는 어노테이션을 이용해 Spring이 Component Scan을 통해 Bean에 등록해줌, IoC 
// ExampleService가 직접 의존성을 관리하는 것이 아닌, 스프링이 관리
public class ExampleService {
    // DI
    private final ExampleRepository exampleRepository;		
}
```

두번째 방법은 의존 객체를 외부에서 주입하는 방법이다.

세번째 방법은 Bean을 통해서 의존 객체를 생성하는 것이다.

(Bean이란?:Spring IoC 컨테이너가 관리하는 자바 객체)



참고:

https://bestpractice80.tistory.com/51,

https://velog.io/@ayoung0073/springboot-IoC%EC%A0%9C%EC%96%B4%EC%9D%98-%EC%97%AD%EC%A0%84%EC%99%80-DI%EC%9D%98%EC%A1%B4%EC%84%B1-%EC%A3%BC%EC%9E%85,

https://jgrammer.tistory.com/entry/springboot-%EC%9D%98%EC%A1%B4%EC%84%B1-%EC%A3%BC%EC%9E%85-%EB%B0%A9%EC%8B%9D-%EA%B2%B0%EC%A0%95,

https://atoz-develop.tistory.com/entry/Spring-%EC%9D%98%EC%A1%B4%EC%84%B1-%EC%A3%BC%EC%9E%85DI-Dependency-Injection%EC%9D%98-%EC%84%B8%EA%B0%80%EC%A7%80-%EB%B0%A9%EB%B2%95
