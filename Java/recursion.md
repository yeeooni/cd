# 순환 (재귀 함수) 
**recursion**

```java
public class code1{ //recursion은 항상 무한루프에 빠지는 것이 아니다.
	public static void main(String args[]){
		int n = 4;
	}
	public static void funk(int k){
		if(k <= 0 ){
			return; // Base case : 적어도 하나의 recursion에 빠지지 않는 경우가 존재해야 한다.
		}else {
			System.out.println("Hello");
			funk(n-1); // recursion case, Base case으로 수렴해야 한다.
		}
	}
}
4 >> funk(3) "Hello"
3 >> funk(2) "Hello"
2 >> funk(1) "Hello"
```

```java
public class code 2{
	public static void main(String args[]){
		int result = funk(4);
	}
	
	public static void funk(int n){
		if(n == 0){
			return 0;
		}else {
			return n + funk(n - 1);
		}
	}
}
4 + funk(3)
3 + funk(2)
2 + funk(1)
1 + funk(0) = 0
```
