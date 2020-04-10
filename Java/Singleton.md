# Singleton Pattern

```java
//Normal.java

public class Normal{
	public Normal(){
		System.out.println("Normal Instance Created!");
	}
}

//Singleton.java
public class Singleton{
	private static Singleton singleton = new Singleton();
	// 정적으로 클래스의 객체를 선언
	//private로 생성된 생성자는 자기자신에서는 호출할 수 있다.

	private Singleton(){
		System.out.println("Singleton Instance Created!");
	}
	public static Singleton getInstance(){
		return singleton;
	}
}

//Main.java
public class Main{
	public static void main(String[] args){
		Normal no = new Normal();
		Normal mal = new Normal();
		Singleton single = Singleton.getInstance();
		Singleton ton = Singleton.getInstance();
	}
}

/* 
 두 개의 생성자를 호출한 결과 (2 번 출력) 싱글톤은 (1 번 출력)
 싱글톤패턴을 사용하여 만든 객체는 언제나 서로 같다는 것을 보증
 고정된 메모리 영역을 사용하도록 단 한번 new 연산자로 인스턴스를 얻어오기때문에 메모리 낭비 해소
 전역변수로 선언되고 전역메소드로 호출하기때문에 다른 클래스에서 사용하기 쉽다.
 성능면에서 월등
*/

```