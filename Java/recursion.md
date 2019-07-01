# 순환 (재귀 함수) 
**recursion**

```{java}
public class code1{
	public static void main(String args[]){
		int n = 4;
	}
	public static void funk(int k){
		if(k <= 0 ){
			return;
		}else {
			System.out.println("Hello");
			funk(n-1);
		}
	}
}
```
