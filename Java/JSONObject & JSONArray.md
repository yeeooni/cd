### JSONObject & JSONArray

**정의**

_Javascript Object Notation 약자 데이터를 표시하는 방법_

- JSONObject

  ```json
  {String name : Value, String name2 : Value2... String nameN : ValueN}
  
  JSONObject jObj = new JSONObject;
  jObj.put("name" : "kim");
  jObj.put("age" : 31);	
  jObj.put("sex" : "male");
  
  String data = jObj.toString();
  System.out.println(data);
  ```

  - 비순서화 된 set

- JSONArray

  ```json
  [{String name : Value}, {String name2 : Value2}....{String nameN : ValueN}]
  ```

  