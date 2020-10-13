# Aspectj
  * 자바 프로그래밍 언어용 관점지향 프로그래밍(AOP) 확인 기능이다.
  * 순수 Spring AOP API에서 제공하지 않는 필드의 대한 Advisor 지원
  * CTW, LTW 과 같은 다양한 위빙 기능 제공
  
  > Aspectj 란
  > 객체지향 언어의 클래스와 비슷한 개념이라 생각하면 쉽다. 많은 오브젝트에 걸쳐서 필요한 부가기능을 추상화 해놓은 것.
  > 구조적으로 Aspect = Pointcut + Advisor
  
  
## 위빙
Aspect 클래스에 정의한 Advice 로직을 타겟(Target)에 적용하는 것을 의미한다.
위빙 방법으로는 LTW, RTW, CTW 3가지가 존재

### RTW (Runtime Weaving)
  * Spring AOP에서 사용하는 방식, Proxy를 생성하여 실제 타겟(Target) 오브젝트에 변형없이 위빙을 수행한다.
  * Method 호출 시에 위빙이 이루어지는 방식
  * 소스 파일, 클래스 파일에 대한 변형이 없다는 장점
  * Advisor가 늘어날 경우 성능이 떨어짐
  * 매소드 호출에 대해서만 Advice를 적용할 수 있다.
  
  
### CTW (Compile Time Weaving)
  * AspectJ에 AJC(AspectJ Compiler) 라는 컴파일러가 존재 (Java Compiler의 확장한 형태의 컴파일러)
  * AJC를 통해 java 파일을 컴파일 하며, 컴파일 조작을 통해 Advisor 코드를 직접 삽입하여 위빙을 수행한다.
  * 속도 면에서는 가장 빠름 (컴파일 시 바이트 코드를 직접 삽입하기 때문에)
  * 롬복과 같은 컴파일 과정에서 코드를 조작하는 플러그인과 충돌할 가능성이 매우 높음
  * intellij에서 컴파일러는 AJC로 바꿔 손쉽게 CTW 사용 가능 (aspects-maven-plugin 사용)
  
### LTW (Load Time Weaving)
   * ClassLoader를 이용하여 클래스가 JVM에 로드 될 때 바이트코드 조작을 통해 위빙되는 방식
   * CTM 처럼 소스 파일과 클래스 파일에 직접 조작하지 않아서 컴파일 시간은 비교적 CTW보다 짫다
   * 오브젝트가 메모리에 올라갈 때 위빙이 일어남
   * Application Context에 객체가 로드될 때, aspectj weaver와 spring-instrument에 의한 객체 Handing이 발생하기 때문에 Performance가 떨어짐
