---
title: controller와 service에 관련된 정리
categories: [dev]
comments: true
---
controller와 service에 관련된 정리
=============

controller의 역할:요청을 어떻게 처리하는지 정하는 역할,

service의 역할:요청에 대해 어떤 처리를 할지 정하는 역할,

repository의 역할:Entity에 의해 생성된 DB에 접근하는 메서드들을 사용하기 위한 인터페이스,
 
@Restcontroller:@Controller에 @ResponseBody가 결합된 어노테이션으로 

컨트롤러 클래스에 @RestController를 붙이면, 컨트롤러 클래스 하위 메서드에 @ResponseBody 어노테이션을 붙이지 않아도 문자열 등을 전송할 수 있다.

@Getter,@Setter:필드를 선언할 시,그와 대응하는 메소드를 자동으로 생성해줌(?),

@Data:@Getter,@Setter,@Tostring,@RequiredArgsConstructor 등을 한꺼번에 설정해줌,

@RequiredArgsConstructor:초기화 되지않은 final 필드나, @NonNull 이 붙은 필드에 대해 생성자를 생성해 줌,

@AllArgsConstructor:모든 필드값을 파라미터로 받는 생성자를 생성해줌,

@Service: respository layer 호출하는 함수에 사용됨

@Repository: data repository를 나타내는 역할
