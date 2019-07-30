# 자료구조

1. 정의
> 데이터를 효율적으로 사용할 수 있도록 구조를 만들어서 저장해둔 것  
하나의 데이터가 아닌 여러 데이터를 담을 때 사용하는 것

2. 종류 
자료구조|ClassName
|:------:|:-------:|
|list|ArrayList LinkedList (Vector)|
|Stack|LinkedList (Stack)|
|Queue|LinkedList|
|HashTable|HashMap (HashTable)|
|집합|HashSet|

- java.util
- Vector, Stack, HashTable 사용이 권장되지 않음

3. 사용방법
```java
ArrayList<String> list = new ArrayList<String>();
list.add("포도");
list.add(new Integer(52)); // 불가능
```

##list : ArrayList Class
- 리스트에 저장할 데이터의 타입을 정한다.
- 타입 파라미터로 ArrayList 객체를 생성
- ArrayList객체에 데이터를 저장
- 데이터를 가져오기 `String str = list.get(2);` // index 2 위치에 있는 데이터
- 데이터 크기를 가져오기 `int size = list.size;` // 데이터 수 
- 데이터를 중간에 삽입 `list.add(2, "키위");` // index 2 위치에 데이터 삽입
- 기존 데이터를 교체하는 방법 `list.set(0, "오렌지");` // index 0 위치에 데이터 교체
- 데이터 삭제(1) `list.remove(1);` // index 1 위치에 데이터 삭제
- 데이터 삭제(2) `list.remove("키위");` // "키위" 데이터 삭제
- 데이터 검색(1) `int index = list.indexOf("사과");` // 사과의 위치를 확인
- 데이터 검색(2) `int index = list.lastIndexOf("사과");` // 중복된 사과의 위치 중 가장 마지막 위치 확인

##list : LinkedList Class
```java
LinkedList<String> list = new LinkedList<String>();
list.add("포도");
list.add("딸기");
list.add("키위");
list.add("복숭아");
list.add("참외");
```
Iterator Method
```java
Iterator<String> iterator = list.iterator();
String str = iterator.next(); // NoSuchElementException 발생가능

while(iterator.hasNext()){
	String str = iterator.next();
	System.out.println(str);
}

// 향상된 for문 list 사용하는 방법
for(String str : list){
	// 반복 실행 부분
}// 이런 형식의 for 문에서는 리스트로부터 Iterator 객체가 자동으로 얻어지고,
그 Iterator 객체를 이용하여 얻은 데이터가 str 변수에 자동으로 대입
```

##Stack : 데이터를 넣은 순서의 역순으로만 꺼낼 수 있는 자료 구조 
```java
LinkedList<Integer> stack = new LinkedList<Integer>();
stack.addLast(new Integer(12)); // Stack 12 추가
```

##Queue : 데이터를 넣은 순서와 같은 순서로만 꺼낼 수 있는 자료 구조
> Queue 에 넣은 데이터는 순서대로 저장  
Queue에서 데이터를 꺼낼때는 넣은 순서대로 꺼내진다.  
Queue로 사용할 수 있는 Class : LinkedList Class

```java
LinkedList<String> queue = new LikedList<String>();
queue.offer("토끼"); // Queue 에 토끼를 삽입 
str = queue.poll(); // 제일 앞에 있는 "토끼"가 나온다.
str = queue.peek(); // 데이터는 그대로 보존한 체 값을 return
```

##HashTable : 여러개의 통을 만들어두고 키값을 이용하여 데이터를 넣을 통 번호를 계산하는 자료 구조
> HashMap Class 기본으로 생성할 경우 16개가 만들어진다.

```java
HashMap<String, Integer> hashTable = HashMap<String, Integer>(100); // 100개의 통으로 구성된 HashTable 생성
hashTable.put("해리", 95); // 데이터 넣기
hashTable.get(key); // 데이터 찾기
hashTable.remover(key); // 데이터 지우기 

//  HashTable 계산 시 사용되는 hasCode() Method

String obj = new String("헤르미온느");
String obj2 = new String("헤르미온느");

int hash = obj.hasCode();
int hash = obj2.hashCode();

Public int hashCode(){
	return firstName.length() + lastName.length(); // 필드값을 기반으로 리턴값을 계산하면 같은 값의 객체들을 같은 값을 리턴하게 됨
}

Public int hashCode(){
	return firstName.hashCode() + lastName.hashCode(); 
}
```

##Set : 수학에서 말하는 집합처럼 데이터를 중복 저장하지 않는다.
> HashSet Class
```java
HashSet <String> hashSet = new HashSet<String>();
hashSet.add("java"); // 데이터 추가, 이미 있는 데이터를 저장하면 집합에 변동이 일어나지 않는다.
hashSet.size(); // 데이터의 수를 return

Interator<String> iterator = hashSet.iterator();
whiled(iterator.hasNext()){
	String str = iterator.next();
}
```

