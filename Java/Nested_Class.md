# Nested Class

1. Inner Class
> 하나의 클래스 내부에 또 다른 클래스가 내포되어 있는 상태

##### 특징
- 중첩되는 클래스는 하나 이상 가능.
- Outer Class Member를 Inner Class에서 사용 가능.
- Outer Class에서 Inner Class Member 사용 불가능.

```java
public class Outer{
	//내용부;
	public class Inner{
		//내용부;
	}// Inner Class
}// Outer Class
````

- 중첩 클래스 객체 생성
`Outer outer = new Outer();`  
`Outer.Inner inner = outer.new Inner();`

- 생성된 클래스 파일 형식
> Inner Class는 $라는 기호로 표시

```java

public class Exam{
	private String outer = "Outer";

	public class Inner{
		private String inner = "Inner";

		public void display(){
			System.out.println(outer + " Class");
			System.out.println(inner + " Class");
		}

	}
}
	
public class ExamCon{
	public static void main(String[] args){
		Exam outer = new Exam();
		Exam.Inner = outer.new Inner();

		inner.display();
	}
}
```

2. Static Inner Class
> 중첩 클래스 내부에서 Static과 관련된 멤버를 선언할 수 있는 클래스 
