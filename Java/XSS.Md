# XSS(크로스사이트스크립팅) 방어
> 웹 화면 내에서 Input box가 있는 곳에 Script를 악의적으로 사용하여 정보를 추출할 수 있다.

- 악성 스크립트
`"><script>alert(document.cookie)</script>)`
> 외부인이 쿠키정보를 손쉽게 얻을 수 있다.  
<>태그나 ()등의 특수문자를 문자 그대로 인식하지 않도록 처리하여 악의적인 사용을 막을 수 있다.

- Tomcat web.xml

```
XSS
util.filter.XSSFilter

XSS
/*
```
**filter-class** : 특수문자를 필터하는 로직이 담긴 내용을 입력
**url-pattern** : 특정 경로로 유입되는 경우에 필터를 적용

```java
import java.io.IOException;
import javax.servlet.Filter;
import javax.servlet.FilterChain;
import javax.servlet.FilterConfig;
import javax.servlet.ServletException;
import javax.servlet.ServletRequest;
import javax.servlet.ServletResponse;
import javax.servlet.http.HttpServletRequest;

public class XSSFilter implements Filter {

 @SuppressWarnings("unused")
 private Object filterConfig;

 @Override
 public void init(FilterConfig filterConfig) throws ServletException {
  this.filterConfig = filterConfig;
 }

 @Override
 public void destroy() {
  this.filterConfig = null;
 }

 @Override
 public void doFilter(ServletRequest request, ServletResponse response, FilterChain chain) throws IOException, ServletException {
  chain.doFilter(new RequestWrapper((HttpServletRequest) request), response);
 }

}

```

```java
package util.filter;
import javax.servlet.http.HttpServletRequest;
import javax.servlet.http.HttpServletRequestWrapper;

public class RequestWrapper extends HttpServletRequestWrapper {

 public RequestWrapper(HttpServletRequest servletRequest){
  super(servletRequest);
 }



 public String[] getParameterValues(String parameter){
  String[] values = super.getParameterValues(parameter);
  
  if(values == null){
   return null;
  }
  
  int count = values.length;
  String[] encodedValues = new String[count];
  for ( int i = 0; i<count; i++){
   encodedValues[i] = cleanXSS(values[i]);
  }
  
  return encodedValues;
 }
 
 public String getParameter(String parameter){
  String value = super.getParameter(parameter);
  if(value == null){
   return null;
  }
  return cleanXSS(value);
 }
 
 public String getHeader(String name){
  String value = super.getHeader(name);
  if(value==null){
   return null;
  }
  return cleanXSS(value);
 }
 
 
 /**
  * 크로스사이트 스크립팅 필터처리
  * @param value
  * @return
  */
 private String cleanXSS(String value){

  value = value.replaceAll("<"                                         , "<");
  value = value.replaceAll(">"                                         , ">");
  value = value.replaceAll("\\("                                       , "(");
  value = value.replaceAll("\\)"                                       , ")");
  value = value.replaceAll("'"                                         , "'");
  value = value.replaceAll("eval\\((.*)\\)"                            , "");
  value = value.replaceAll("[\\\"\\\'][\\s]*javascript:(.*)[\\\"\\\']" , "\"\"");
  value = value.replaceAll("[\\\"\\\'][\\s]*vbscript:(.*)[\\\"\\\']"   , "\"\"");
  value = value.replaceAll("script"                                    , "");
  value = value.replaceAll("onload"                                    , "no_onload");
  value = value.replaceAll("expression"                                , "no_expression");
  value = value.replaceAll("onmouseover"                               , "no_onmouseover");
  value = value.replaceAll("onmouseout"                                , "no_onmouseout");
  value = value.replaceAll("onclick"                                   , "no_onclick");
  value = value.replaceAll("<iframe"                                   , "<iframe");
  value = value.replaceAll("<object"                                   , "<object");
  value = value.replaceAll("<embed"                                    , "<embed");
  value = value.replaceAll("document.cookie"                           , "document.cookie");
  
  
  return value;
 }
 
}
```

