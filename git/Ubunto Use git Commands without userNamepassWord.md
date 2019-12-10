### Use git Commands without userName/passWord

- 우분투에서 터미널로 깃을 사용할 때 push 할 때마다 아이디, 비밀번호를 입력해주어야 하는 작업을 없앤다. 
  - config cahe timeout을 조정하는 방법
  - ssh key를 등록하는 방법
  - git clone 시 repo url에 비밀번호를 입력하는 방법
- timeout 시 다시 아이디와 비밀번호를 입력해야 하므로 패스.
- ssh key를 삭제하기 전까지는 영구적이다.
- clone 시 repo url는 비추천으로 패스.



- 공개키를 등록해야 사용할 수 있다.

  - 공개키 등록전 확인

    ```shell
    cd ~/.ssh
    ls
    ```

  - 공개키 생성

    ```shell
    ssh-keygen -t rsa
    
    - id_rsa.pub #공개키, 알려줄 키 값 / 필수 생성
    - id_rsa #개인키, 알려주면 안되는 키 / 필수 생성
    
    ```

  

1. **ssh key 등록**
   - github login
   - profile -> setting -> ssh and gpg keys
   - new ssh key 
   - git local ssh key -> _ssh public key_ cat ~/.ssh/id_rsa.pub -> 
   - title ->
   - key 복사한 local ssh 값 삽입
   - use ssh 복사 
   - git remote set-url origin ssh_link

