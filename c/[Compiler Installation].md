[Compiler Installation]

유용한 사이트

Code::Blocks (http://codeblocks.org)

어떤 운영체제에서도 사용할 수 있는 컴파일러이다.



Download the binary release -> os -> Download from click

File -> New -> Project -> console application click -> next -> c -> ProjectTitle -> ProjectFIleName -> next -> finish



[Programming]

- 용어 설명
  - 주석 (Comments)
  - 기본 (Default)
  - 문장 (Statement)
  - 전 처리기 (Preprocessor)
  - 프린트 (Print)
  - 스캔 (Scan)
  - 함수 (Fucttion)
  - 자릿수 (Digit)
  - 문자 (Character)
  - 부동소수점 (Floating-point number)
- 컴파일러 없이 프로그래밍
  - 자연어 
  - Pseudo Code
  - Algorithm
- 가상 컴파일러
  - https://www.learn-c,org

_Printf() 및 scanf() 함수는 Function  기본적으로 C라이브러리에서 사용할 수 있는 프로그래밍 언어의 기본 라이브러리 함수_

Stdio.h = Standard Input Output. Header file 

전자공학에서 전자장치는 기본저긍로 microprocessor를 사용하는데 거의 모든 소프트웨어는 C 언어를 사용한다.

최근 소프트웨어 교육에 대한 중요성이 강조되면서 점차 C언어 교육에 대한 관심이 높아졌다.

Python, Java를 사용해 Coding 교육으로 사용되는바,  C언어는 다시 교욱에서 관심을 받고 있다.



[DataType]

- 거의 모든 프로그래밍 언어들은 명시적으로 자료형의 개념을 포함하지만 다른 언어들은 다른 용어를 사용할 수 있다. 일반적으로 다음을 포함한다.
  - 정수형
    - int, short, long
    - Unsigned, signed 
  - 실수형
    - double, float, long double
  - 논리형
    - boolean
  - 문자형
    - character, char, String
  - 부동소수점
    - floating-point number
- printf() & scanf()
  - %d 
  - %c
  - %f
  - %lf
  - %s
  - \n 줄바꿈



- 용어 설명
  - 증가 (Increment)
  - 감소 (Decrement)
  - 표준입력출력 (Standard Input Output)
  - 표준라이브러리 (Standard Library)



[직사각형 계산 프로그래밍]

```c
int main(){
    int length, width, area; //길이, 너비, 공간
    printf("Enter ther Length and Width of Rectangle : ");
    scanf("%d %d", &length, &width);
    area = length * width ;
    
    printf("직사강형의 면적? %d", area);
    return 0;
}
```



[Interanal Conversion Program]

```c
#include <stdio.h>
int main(){
    float c, f;
    printf("Enter temp in Celsius : \n");
    scanf("%f ", &c);
    f = (1.8 * c) + 32;
    printf("temperature in fahrenheit : %f", f );
    return 0;
}
```

[Do - while loop]

```c
do{
    
}while();


```

[For loop]

```c
for()
```

