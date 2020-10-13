 # BCI (Byte Code Instrumentation)
 Java의 Byte Code를 직접 수정을 가해서, 소스 파일의 수정없이 원하는 기능을 부여하는 방법
 BCI는 AOP의 Load Time Weaving의 핵심 기술이다.
 
 ## JAVA Byte Code
  * JAVA Byte Code 기계어로 되어있고, OS/HW에 의존하지 않고, JVM에만 의존적이기 때문에 서로 다른 환경에서도 하나의 Byte Code로 구동이 가능하다.
  * Byte Code를 직접 읽고 쓰는것이 가능하지만 매우 복잡하다. 하지만 다양한 라이브러리를 통해 Byte Code 수정이 가능하다.
  * ex) ASM, BCEL, Javaasist, SERP
  
  
## Javassist
  * java 바이트 코드를 처리하기 위한 라이브러리
  * java 바이트 코드는 클래스 파일이라는 이진파일에 저장하고 각 클래스 파일에는 JAVA 클래스 또는 인터페이스가 포함된다.
  
  ### Javassist.CtClass
  * 클래스 파일의 추상 표현
  * 클래스 파일 처리의 대한 핸들러
