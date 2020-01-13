### :contains()

- 특정 문자열을 포함한 요소를 선택하는 선택자

  ```javascript
  $(":contains(text)")
  
  $("p:contains("ab")");
  //ab 문자열을 포함한 p 요소를 선택
  
  $("p:contains("ab").css("color", "red")");
  //ab 문자열을 포함한 p요소를 선택하여 글자를 빨간색으로 만든다.
  ```

  