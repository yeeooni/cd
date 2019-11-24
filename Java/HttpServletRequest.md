# 세션(Session) HttpServletRequest

스프링 MVC 세션은 HttpServletRequest, HttpSession을 사용하여 구현할 수 있다.

```java
@RequestMapping(value="/modify", method = RequestMethod.POST)
public ModelAndView modify(Member member, HttpServletRequest request){
    HttpSession session = request.getSession();
    
    Member mem = service.memeberModify(member);
    session.setAttribute("member", mem);
    
    ModelAndView mav = new ModelAndView();
    mav.addObject("memAft", mem);
    
    mav.setViewName("/member/modifyOk");
    
    return mav;
}
```

_사용자 정보를 변경하는 요청인 /modify로 요청이 들어오면  HttpServletRequest 객체인 request가 인자로 들어오면서 modify 메소드가 실행_

_이 때 세션에 setAttribute 메소드를 통해 세션의 속성값을 설정, 이 속성값은 세션에 의해 유지되며 getAttribute 메소드를 통해 다른 요청을 처리하는 컨트롤러 메소드에서 이 값을 얻을 수 있다._



```html
<body>
    <input type="text" value="${member}"/>
</body>
```



```java
@RequestMapping(value="/getModify")
public ModelAndView getModify(HttpServletRequest request)throws Exception{
    ModelAndView mav = new ModelAndView();
    
    HttpSession session = request.getSession();
    String name = (String) session.getAtrribute("member");
    
    System.out.println("세션에 저장 되있는 이름" + name);
    return mav;
}
```



session.invalidate();

_세션 초기화_





