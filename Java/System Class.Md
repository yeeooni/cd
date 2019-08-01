# System Class

> 운영체제와의 상호작용에 필요한 여러기능들을 모아놓은 Class

- 표준 입출력 : 키보드로부터의 입력과 모니터로 출력 기능
- 환경변수 읽기 : 운영체제에 설정되어 이쓴ㄴ 환경변수를 읽어오는 기능
- 시스템프로퍼티 읽기 : 프로그램의 환경모드를 프로퍼티 형태로 읽고 쓰는 기능
- 현재 시각 측정 : 시스템 시계로부터 현재 시각을 읽어오는 기능
- 프로그램 실행 관련 기능 : 프로그램을 끝내는 기능과 가비지 컬렉터 관련 기능
- 보안 설정 가능 : 자바 프로그램의 보안 관리자 설정 기능
- 그 밖의 유용한 기능 : 배열을 효율적으로 복사하는 기능

**사용방법** : System.in 필드는 표준입력처리, System.out 필드는 표준출력에 사용된다.
> 입력 `System.in InputStreamReader` 객체 생성

`InputStreamReader reader = new InputStreamReader(System.in);`
`Char char = (Char) reader.read();`

`InputStreamReader reader = new InputStreamReader(System.in);`  
`BufferedReader reader2 = new BufferedReader(reader);`  
`BufferedReader reader = new BufferedReader(new InputStreamReader(System.in));`  
`String str = reader.readLine();`

> 출력 System.out

```java
System.out.println("Hello, java");
System.out.print("12.5");
System.out.printf("%d", 27);
```

> 에러 출력 System.err
`System.err.println("잘못된 포맷입니다.");`

> 환경변수를 읽는 Method
`String str = System.getenv("path");`

> 시스템 프로퍼티를 읽는 Method
```java
System.getProperties
Properties props = System.getProperties;
props.list(System.out);
```

> gc Method
```java
ResourceUser obj = new ResourceUser(); 
obj.use();
System.gc();
```

> RunFinalization Method : 불필요한 객체들의 finalize Method가 더 빨리 호출되도록 만드는 Method
`System.runFinalization();`

> ArrayCopy Method : 배열의 일부/전부를 일괄 복사하는 Method
```java
int arr[] = {0, 1, 2, 3, 4, 5, 6};
System.arrayCopy(arr, 0, arr, 5, 10};
// arr 0 ~ arr 9 / arr 5 ~ arr 14
```

> CuttentTimeMilleies Method : 시스템 시계로부터 현재시각을 읽는 Method
`Long time = System.currentTimeMillis(); // 1/1000초 단위`

 



