### [명령어] JAVA, JAVAC version 변경

1. 현재 자바 버전 확인
   - java -version
   - echo $JAVA_HOME
   - javac -version
2. 자바 프로그램의 위치 확인
   - which java
   - which javac
3. 자바 링크 경로 확인
   - ls -l /usr/local/java/jdk1.8.0_231/bin/java
   - readlink -f
4. 업그레이드 된 자바 버전으로 재링크
   - unlink /usr/local/java
   - ln -s 자바설치경로 /usr/bin/java
   - unlink /usr/local/javac
   - ln -s 자바설치경로 /usr/bin/javac