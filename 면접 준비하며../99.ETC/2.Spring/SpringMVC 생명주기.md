### SpringMVC의 생명 주기

1. Request
2. DispatcherServlet
3. HadlerAdapter
4. Controller
5. ViewResolver
6. View

---

###1. Request

브라우저로 부터 요청(Request)이 들어오면, Filter를 거쳐서 DispatcherServlet으로 보낸다.

> Filter는 Servlet에서 처리 전&후를 다룬다
>
> Filter에선 주로 인코딩등을 다룬다.  
>
> Filter는 WebApplication에 등록하고, Interceptor는 Spring Context에 등록한다.

### 2. DispatcherServlet

컨트롤러에 요청을 전달하기 전에, 가로채 HandlerMapping을 한 컨트롤러를 찾는다. 그리고 DispatcherServlet에게 전달한다.



### 3. HandlerAdapter

DispatcherServle이 모든 웹 요청이 담긴 HttpServletRequest 오브젝트를 HandlerAdapter가 컨트롤러의 메서드가 받을 수 있도록 파라미터 변경 등을 해 컨트롤러에 전달해 준다.



### 4. Controller

HandlerAdapter가 호출한 컨트롤러의 메서드를 실행한다.

이 부분에서, 개발자의 일반적인 비즈니스로직의 작성이 시작된다.

요청을 처리 후 Model객체에 담고, View를 생성해 반환한다.



### 5. ViewResolver

전달받은 View의 이름을 가지고 매핑된 View를 찾아서 반환한다.



### 6. View

DispatcherServlet은 매핑된 View를 Response한다. response시 필터의 영향을 받는다.



참조: https://all-record.tistory.com/164

