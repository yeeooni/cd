# 자바스크립트 배열 

```javascript
// 배열 
var nation = ['대한민국', '스웨덴', '네덜란드'];
alert(nation[0]); // 대한민국

var arr = [1, 2, 3, 4, 5, 6, 7];
alert(arr.length); //배열의 길이를 출력해라.

//PUSH 함수를 이용하여 배열 끝에 원소를 추가할 수 있다.
var arr = [1, 2, 3, 4, 5, 6, 7];
arr.push(9);
alert(arr); // [1, 2, 3, 4, 5, 6, 7, 9]

//CONCAT 함수를 이용하여 배열의 끝에 복수개의 원소를 추가할 수 있다.
var arr = [1, 2, 3, 4, 5, 6, 7];
arr = arr.concat([8, 9]);
alert(arr); // [1, 2, 3, 4, 5, 6, 7, 8, 9]

//UNSHIFT 함수를 이요하여 배열의 왼쪽에서부터 차례로 삽입할 수 있다.
var arr = [1, 2, 3, 4, 5, 6, 7];
arr.unshift(9);
alert(arr); // [9, 1, 2, 3, 4, 5, 6, 7]

//SPLICE 함수를 이용하여 원하는 자리에 요소를 삽입할 수 있다.
var arr = [1, 2, 3, 4, 5, 6, 7];
arr.splice(3, 0, 9);
	(3, 1, 9) // 세 번째 자리 첫 번째 숫자 제거 후 
	(3, 2, 9) // 세 번째 자리 두 번째 숫자 제거 후 
alert(arr); // [1, 2, 3, 9, 4, 5, 6, 7]

//SHIFT 함수를 이용하여 배열의 첫 번째 요소부터 제거한다.
var arr = [1, 2, 3, 4, 5, 6, 7];
arr.shift();
alert(arr); //[2, 3, 4, 5, 6, 7]

//POP 함수를 이용하여 배열의 끝점 원소를 제거한다.
var arr = [1, 2, 3, 4, 5, 6, 7];
arr.pop();
alert(arr); //[1, 2, 3, 4, 5, 6]

//SOR 함수를 이용하여 배열을 정렬한다.
var arr = [1, 2, 5, 6, 7, 4, 3];
arr.sort();
alert(arr); //[1, 2, 3, 4, 5, 6, 7]
```
