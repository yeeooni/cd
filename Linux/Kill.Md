# kill  

1. signal 정의  
_SoftWare Interrupt 어떤 이벤트가 발생했음을 프로세스에게 알려주는 매커니즘_  
_시그널 숫자는 1 ~ 의미있는 이름으로 정의되어 있다._  
`/usr/include/signal.h`  

```shell
kill -l
# 1) SIGHUP 2) SIGINT 3)SIGQUIT... 
````
2. 사용방법  
_kill 명령어 뒤에 시그널의 숫자를 붙이고 프로세스 ID를 준다. / SIG를 뺀 이름을 주고 프로세스 ID를 준다._  

3. signal handler  
_signal 발생은 비동기 작업이며, 개발자는 프로그램을 만들 때 특정 시그널을 수신했을 때 실행되기를 바라는 함수를 등록할 수 있다._  
|action|기본동작|
|:-----|:------:|
|TERM|시그널을 수신한 프로세스 종료|
|IGN|시그널 무시|
|CORE|시그널을 수신한 프로세스를 종료하면서 코어덤프 파일 생성|
|STOP| 시그널을 수신한 프로세스 정지|
|CONT|중지된 프로세스 재시작|


