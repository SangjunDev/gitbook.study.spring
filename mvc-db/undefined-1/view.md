# View 환경설정

**resources/static/index.html**

```
<!DOCTYPE HTML>
  <html>
  <head>
      <title>Hello</title>
      <meta http-equiv="Content-Type" content="text/html; charset=UTF-8" />
  </head>
  <body>
  Hello
  <a href="/hello">hello</a>
  </body>
  </html>
```



**main/java/hello.hellospring/controller/HelloController.java**

```
package hello.hellospring.controller;
import org.springframework.stereotype.Controller;
import org.springframework.ui.Model;
import org.springframework.web.bind.annotation.GetMapping;

@Controller
public class HelloController {

    @GetMapping("hello")
    public String hello(Model model){

        model.addAttribute("data", "hello!!");
        return "hello";
    }
}

```



**resources/templates/hello.html**

```
<!DOCTYPE HTML>
<html xmlns:th="http://www.thymeleaf.org">
<head>
    <title>Hello</title>
    <meta http-equiv="Content-Type" content="text/html; charset=UTF-8" />
</head>
<body>
<p th:text="'안녕하세요. ' + ${data}" >안녕하세요. 손님</p>
</body>
</html>
```



**동작 환경 그림**

![ ](<../../.gitbook/assets/스크린샷 2022-05-10 오후 9.42.12.png>)

* 컨트롤러에서 리턴값으로 문자를 반환하면 뷰 리졸버(viewResolver)가 화면을 찾아서 처리한다.

&#x20;   \- 스프링 부트트 템플릿엔진 기본 viewName 맵핑

&#x20;   \- resources:templats/ {ViewName} + .html&#x20;
