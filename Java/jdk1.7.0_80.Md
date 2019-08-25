# JDK 7(Java 1.7.0_80) 설치 in Ubuntu 

> 기존에 사용하고 있던 openjdk 8 버전 삭제.

- Open JDK 삭제
`sudo apt-get purge openjdk*`

- 순서
```bash
cd /Downloads #다운로드 디렉토리 이동

sudo mkdir -p /usr/local/java #디렉토리 생성
sudo cp -r jdk-7u80-linux-x64.tar.gz/usr/local/java #압축파일 복사

cd /usr/local/java #디렉토리 이동
sudo tar zxvf jdk-7u80-linux-x64.tar.gz

sudo vi /etc/profile # 파일 설정 추가

JAVA_HOME=/usr/local/java/jdk1.7.0_80
JRE_HOME=/usr/local/java/jdk1.7.0_80
PATH=$PARH:$JRE_HOME/bin:$JAVA_HOME/bin

export JAVA_HOME
export JRE_HOME
export PATH

$sudo update-alternatives --install "/usr/bin/java" "java" "/usr/local/java/jdk1.7.0_80/bin/java" 1
$sudo update-alternatives --install "/usr/bin/javac" "javac" "/usr/local/java/jdk1.7.0_80/bin/javac" 1
$sudo update-alternatives --install "/usr/bin/javaws" "javaws" "/usr/local/java/jdk1.7.0_80/bin/javaws" 1
$sudo update-alternatives --set java /usr/local/java/jdk1.7.0_80/bin/java
$sudo update-alternatives --set javac /usr/local/java/jdk1.7.0_80/bin/javac
$sudo update-alternatives --set javaws /usr/local/java/jdk1.7.0_80/bin/javaws

source /etc/profile #적용

java -version #버전 확인



```


