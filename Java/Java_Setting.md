# Java Setting

- [oracle.com]( https://www.oracle.com/index.html ) >> "JDK" >> Download

  - jdk-8u231 (2019.11.06 기준) 

- 환경변수 설정 

  - 내컴퓨터 >> 속성 >> 고급 >> 시스템설정 >> 환경변수 >> 시스템변수 >> 새로만들기 >> 편집

    |              JAVA_HOME               | CLASSPATH |         PATH         |
    | :----------------------------------: | --------- | :------------------: |
    | C:\Program Files\Java\\[jdk Version] | .         | **%JAVA_HOME%\bin;** |

- 설정 확인 (CMD)

  - java -version, javac