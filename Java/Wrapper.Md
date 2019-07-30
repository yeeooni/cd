#Wrapper Class

1. 정의
> 프리미티브 타입을 객체로 표현하는데 사용되는 다음 클래스들의 통칭  
프리미티브 타입의 데이터를 감싸는 역할을 하는 Wrapper

Wrapper Class_Name | 프리미티브 타입
|:----------------:|:--------------:|
|Byte|byte|
|Short|short|
|Integer|int|
|Long|long|
|Character|char|
|Float|float|
|Double|double|
|Boolean|boolean|

프리미티브 타입의 데이터를 감싸는 역할을 하는 Wrapper Class
> 예) Byte 객체 >> byte 타입 데이터

2. Wrapper Class의 기본적인 사용방법 

```java
Byte obj = new Byte((byte), 1);
Short obj = new Short((short), 123);
Integer obj = new Integer(12345);
Long obj = new Long(1234567689L);
Float obj = new Float(1.5f);
Double obj = new Double(1.00005);
Character obj = new Character('꽃');
Boolean obj = new Boolean(true);

// 래퍼런스 객체 안에 있는 프리미티브 값을 가져오는 방법

Byte num = obj.byteValue();
Short num = obj.shortValue();
Int num = obj.intValue();
Long num = obj.longValue();
Float num = obj.floatValue();
Double num = obj.doubleValue();
Char num = obj.charValue();
Boolean num = obj.booleanValue();

Integer obj = new Integer(12);
Integer obj2 = new Integer(5);

int sum = obj.intValue() + obj2.intValue();
System.out.println(sum);

// 결과 값 : 17

// 문자열 파라미터를 받는 생성자(문자열 파라미터를 프리미티브 값으로 바꾸어서 래퍼런스 객체 안에 저장하는 생성자)

Byte obj = new Byte('1');
Short obj = new Short("123");
Integer obj = new Integer("12345");
Long obj = new LOng("123456789");
Float obj = new Float("1.5");
Double obj = new Double("1.00006);
Boolean obj = new Boolean("true");

int total = 0;
  for(int cnt = 0; cnt < args.length; cnt++){
	total += obj.intValue();
  }
System.out.println(total);

```

3. Wrapper Class의 정적 메소드와 상수
```java
// 정적 메소드
String str = Integer.toBinaryString(9); // "1001"을 return 
String str = Long.toBinaryString(110000L); // "11010110110110000" return

int num = Float.floatToRawIntBits(1.5f); // 1.5f와 똑같은 비트 패턴의 int 값을 return
long num = Long.longToRawLongBits(1.0005); // 1.0005와 똑같은 비트 패턴의 long 값을 return

// 문자열을 프리미티브 타입으로 바꾸는 메소드
byte num = Byte.parseByte("1");
short num = Short.parseShort("123");
int num = Integer.parseInt("1234");
long num = Long.parseLong("1234567890");
float num = Float.parseFloat("1.5");
double num = Double.parseDOuble("1.000005");
boolean result = Boolean.parseBoolean("true");

// Wrapper Class의 생성자를 대신하는 메소드
Byte obj = Byte.valueOf((byte), 1);
Integer obj = Integer.valueOf(12345);
```

4. auto Boxing, auto UnBoxing
```java
Integer obj = new Integer(12000); // Boxing
int num = obj.intValue(); // UnBoxing

// Boxing 프리미티브형의 데이터를 Wrapper Class의 객체로 만드는 과정
int i = 10;
Integer wrapper = new Integer(i);

int i = 10;
Integer wrapper = Integer.valueOf(i);

// UnBoxing Wrapper Class 데이터를 프리미티브형으로 얻어내는 과정
int i = 10;
Integer wrapper = new Integer(i);
int i2 = wrapper.intValue();
```

- JDK 1.5 ~ auto Boxing auto UnBoxing 지원
- Wrapper Class의 대입된 값은 ==, !=와 같은 연산자 이용 값 비교 불가능 
그 이유는 인스턴스를 생성하면서 heap 메모리에 값이 저장되고 객체 변수는 참조 값을 갖기 때문에 따라서 equals 메소드를  
이용하거나 데이터를 UnBoxing하여 값을 비교해야 한다.
