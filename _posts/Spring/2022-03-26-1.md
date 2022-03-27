---
    title : "[Spring] Spring 내부 동작과정"
    excerpt: "[Spring] Spring 내부 동작과정 정리"
    toc : true
    toc_sticky : true
    toc_label : "목차"
    categories :
     - Backend
    tag :
     - Spring
---

# 스프링 내부 동작과정
사용자 Request가 들어왔을 때 스프링 서버 내부의 동작 과정을 정리

![image](https://user-images.githubusercontent.com/10546369/160226844-9527118d-317c-4707-a512-8129ad7e6208.png){: .align-center}

1. 사용자의 HTTP request가 들어오면 **Dispatcher Servlet**에서 핸들러 **HandlerMapping**에 컨트롤러 검색 요청

2. **HandlerMapping** 에서 request에 매핑이 된 Handler 검색 후 Controller Bean 객체를 **DispatcherServlet**에 전달

3. **handler**(Method)를 실행할 수 있는 handlerAdapter Bean에 request 처리를 위임

4. **handlerAdapter**는 컨트롤러에 알맞은 controller를 호출하여 처리 결과를 DispatcherServelet에 반환  


---


![image](https://user-images.githubusercontent.com/10546369/160227500-5cf36f3f-0c44-41f6-b2e5-cab5067568bc.jpg){: .align-center}


# Controller와 Handeler의 역할

- 클라이언트의 요청을 실제로 처리하는 것은 **Controller**
- **DispatherServelet**는 클라이언트의 요청을 전달받는 창구
- **HandlerMapping**는 Handler를 찾아주는 역할
- **HandlerAdapter**는 처리결과를 반환해서 DispatcherServelet에 전달


참고 : https://owin2828.github.io/devlog/2019/12/30/spring-10.html
