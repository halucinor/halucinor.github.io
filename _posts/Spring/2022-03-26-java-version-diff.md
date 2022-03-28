---
    title : "[Java] Java 버전 별 차이점"
    excerpt: "Java 버전 별 차이점"
    toc : true
    toc_sticky : true
    toc_label : "목차"
    categories :
     - Backend
    tag :
     - Java
---


- **JAVA 8**
    - Lamda
        
        익명함수라는 이름이 없는 형태의 함수를 사용할 수 있음
        
        일급객체 : 다른 객체들에서 적용가능한 연산을 모두 지원(파라미터로 전달, 함수를 값으로 사용, 변수 대입)
        
    - Stream
    - Optional
        
        Nullptr error 을 방지할 수 있도록 돕는 자료형
        
    - LocalDateTime API
    - **Default method**  
        인터페이스 내에서 기본 메서드를 정의
        <details>
        <summary>code</summary>
        <div markdown = 1>
        ```java
        interface TestInterface {
        //기존 메서드들
        public void go();
        public void get();
            
        default void show() {
            // 구현 내용
            System.out.println("표시해줘요");
            }
        }

        class TestClass implements TestInterface {
            //그냥 사용한다면
        }

        class OverrideTestClass implements TestInterface {

            //만약 어떠한 클래스에서 수정이 필요하다면
            @Override
            public void show() {
                //새로운 구현 내용
                System.out.println("수정했어요");
            }
        }

        // 사용 부분
        class Main {
            TestClass testClass = new TestClass();
            OverrideTestClass overrideTestClass = new OverrideTestClass();
                
            testClass.show(); //"표시해줘요"
            overrideTestClass.show(); //"수정했어요"
        }
        ```

        </div>
        </details>

- **JAVA 11**
    - String class
    - **Nest-Based Access Control**
        <details>
        <summary>code</summary>
        <div markdown = 1>
            
        ```java
        class Test { 
        	static class One { 
        	private int one; 
        } 
        	
        	static class Two {
        	 private int two; 
        	} 
        }
        ```
        </div>
        </details>
            
    - Dynamic Class File Constants
    - New Garbage Collector
    - Local-Variable Syntax for Lambda Parameters

- **JAVA 12**
    - Switch문 확장
    - String method 추가
    - GC 개선