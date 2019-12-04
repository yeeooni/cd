### Ubuntu Oracle java 설치

1. jdk 설치

2. 명령어 기입

   ```shell
   sudo mv [jdk] /usr/local/java/
   
   cd /usr/local/java/
   sudo tar xvfz [jdk] #압축풀기
   
   sudo vi /etc/profile
   
   
   JAVA_HOME=/usr/local/java/[jdkVersion]
   JRE_HOME=$JAVA_HOME/jre
   PATH=$PATH:$JAVA_HOME/bin:$JRE_HOME/bin
   export JAVA_HOME
   export JRE_HOME
   export PATH
   
   ./etc/profile
   source /etc/profile
   
   java -version
   javac -version
   
reboot
   ```
   
   