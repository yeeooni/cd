# 1. 시작하기 
[img : 누구나 쉽게 이해할 수 있는 GIT 입문](https://backlog.com/git-tutorial/kr/) 

> git이란 소스코드를 효과적으로 관리하기 위한 *'분산형 버전 관리 시스템'*  
> 원래는 Linux 소스코드를 관리할 목적으로 개발되었다.

![capture_intro1_1_2](../img/capture_intro1_1_2.png)

> 여러 명이 공유한 파일을 동시에 편집하는 과정에서 충돌이 일어난다.  
이런 문제를 해결하기 위해 만들어진 것이 Git과 같은 버전 관리 시스템이다.

![capture_intro1_1_3](../img/capture_intro1_1_3.png)

# 2. 저장소(Git Repository)

> 말그대로 파일이나 폴더를 저장해 두는 곳이다.  
> Git 저장소가 제공하는 가장 좋은 점은 파일이 변경 이력 별로 구분되어 저장된다는 점이다. 

![capture_intro1_2_1](../img/capture_intro1_2_1.png)

# 3. 브랜치(Branch)
![Branch](../img/capture_stepup1_1_1.png)
> 소프트웨어를 개발할 때 개발자들은 동일한 소스코드를 함께 공유한다.  
동일한 코드위에서 개발자들마다 수정과 새로운 기능을 만들어낸다.  
이럴 때, 동시에 다양한 작업을 할 수 있게 만들어 주는 기능이 *\'branch\'* 이다.  
브랜치란 독립적으로 어떤 작업을 진행하기 위한 개념이다.  

![Branch 전략](../img/capture_stepup1_1_2.png)
> 이렇게 만들어진 브랜치는 다른 브랜치와 병합(Merge)로, 작업한 내용을 다시 새로운  
하나의 브랜치로 모을 수 있다.

+ 마스터 브랜치 (Master Branch)
> 저장소를 처음 생성하게되면, master라는 이름의 브랜치를 만들어 준다.  
이 새로운 저장소에 새로운 파일을 추가하거나 파일의 내용을 변경하여 그 내용을  
저장(커밋,Commit)하는 것은 모두 *\'master\'* 라는 이름의 브랜치를 통해 처리한다.  

+ 브랜치 전환하기
![브랜치 전환](../img/capture_stepup1_3_1.png)
> 현재 선택된 브랜치가 아닌 다른 브랜치에서 작업을 하고 싶을 때, *\'체크아웃(checkout)\'*  
명령어를 실행하여 원하는 브랜치로 전환할 수 있다. 체크아웃을 실행하면, 우선 브랜치  
안에 있는 마지막 커밋 내용이 작업 트리에 펼쳐진다. 브랜치가 전환되었다면 이 후에 실행한 커밋은  
전환한 브랜치에 추가된다.  
**HEAD**란 현재 사용 중인 브랜치의 선두 부분을 나타내는 이름이야.  
머리라고 생각하면 두 눈이 달려있잖아? 눈으로 바라보는 그 시각을 뜻한다고 생각하면 되.  
기본적으론 master의 선두 부분을 나타내지. 


+ 브랜치 생성 
> 나는 브랜치를 나누기 귀찮아서... 누구나 그럴테지?  
master에 하나에 모든 소스를 주입하는 방식으로 사용했었는데.  
키트리를 다니면서까지도 아무생각없이 사용하다가 막상 취업이 되고 현업에 오게되니  
형상관리시스템을 사용하는 가장 큰 목적이 소스관리와 협업인데, 당연히 너무 괄시하고 멸시했다고 생각이 들어.  
가장 큰 이유는 빌어먹을 귀찮아서일테지만.  
그렇기에! 반성하는 의미로 이 저장소를 정리하면서 브랜치를 나누어 관리할 예정이고, 개발이 끝나면  
**병합(merge)** 혹은 **리베이스(rebase)** 할 것이다. 현재 Develop_git 으로 나누었고,  
브랜치를 생성하는 방법을 간단히 적어보겠다.  

```
git branch <브랜치명>
//브랜치를 생성하는 구문이다.
```

```
git checkout -b <브랜치명>
//위와 같이 적어준다면, 브랜치를 만드는 동시에 해당 브랜치로 체크아웃을 해준다.
```

```
//하지만 내가 생성한 이 브랜치는 로컬(local)과 저장소의 remotem branch가 생성되어 있지않아서, 
git push 명령어를 사용하지 못했다.

[오류내용] 
kimeuiyeon@nerdy:~/explicit-knowledge$ git push
fatal: The current branch Develop_git has no upstream branch.
To push the current branch and set the remote as upstream, use

    git push --set-upstream origin Develop_git

```

```
git push --set-upstream origin <브랜치명>
```

> 이 문제는 위와 같이 명령어를 입력하여 해결하였다. 브랜치를 생성한다음 _꼭꼭꼭_  
각자가 local 및 저장소 기준이므로, local의 branch를 remote branch와 연동하는  
작업을 해주어야 한다. 필수는 아니지만 차후에 관리에 좋다.
_Git을 사용하다보면 원격 저장소에 있는 **branch**를 로컬 저장소로 pull 하는 경우가 있다._

_협업을 하고 있는 다른 팀원은 branch를 가져와서 작업을 해야하는 경우,  혼자서 2대의 pc를 사용하고 작업파일을 git으로 관리하는데 branch를 따서 작업하는 경우 저장소를 그대로 clone을 하던지 pull을 하면 원격 저장소의 branch도 같이 받아질 것이라 생각하지만 그렇지 않다._

`git checkout -t [원격저장소의 branchName]` 명령을 이용하여 가져와야한다.

1. `git remote update`

2. `git branch -r` 원격 저장소의 branch 리스트 확인
3. `git checkout -t [branchName]`

---

+ 병합(merge)
> 브랜치와 브랜치를 합친다라는 개념이라는건 다들 알고 있겠지.  
몰라도 되. 합친다는 것만 알고 있다면 말이야.
우선 하나의 기능의 개발이 끝나면 마스터브랜치로 체크아웃을 하고 명령어를 입력할꺼야.
```
git merge <생성했던 브랜치명>

//그 전에 pull-request를 이용하여 master에서 conflict등의 오류가 없는지 확인하는게 좋다.
git pull-request
```
---

+ 브랜치 삭제
> 작업이 끝나고, 기준 branch로 pull-request가 종료되어서 merge까지 완료되었다면,  
 branch를 삭제 해주는게 좋다. 우선 master branch로 체크아웃을 해준다.
```
git checkout master
git branch -d <브랜치명>

// 그러나, 작업된 사항이나 commit한 이력이 남아있는 경우, 브랜치가 삭제되지 않는 경우가 있다.
// 이러한 경우에는 강제로 브랜치를 삭제할 수 있다.
git branch -D <브랜치명>

// 그 후, 원격 브랜치도 삭제해준다.
git push origin :<브랜치명>
```
---

+ merge --squash
> 새로운 브랜치에서 모든 커밋을 하나의 커밋으로 병합하여 'master' 브랜치로 가져와야할 때 사용하는 명령어
```
// 현재 마크다운 브랜치(마크다운.md 관리하는 브랜치)로 체크아웃하고 git log를 확인한 상태 

commit 3b7806f7539e21640005147acbf9f5455f87c0a0 (HEAD -> Develop_md, origin/Develop_md)
Author: yeeooni <12.12kimiyeon@gmail.com>
Date:   Thu Jun 27 10:57:52 2019 +0900

    정의 추가

commit bb77dcd02c031fde47a16ec72000ed2983a7fce9
Author: yeeooni <12.12kimiyeon@gmail.com>
Date:   Thu Jun 27 10:45:46 2019 +0900

    수정

commit a3a57a5ed9897d3fb1ad79e036d19c850c85c90a
Author: yeeooni <12.12kimiyeon@gmail.com>
Date:   Thu Jun 27 10:43:41 2019 +0900

    수정

commit f468f81d03fc4af040d540adf4bf91ee02d72fd9
Author: yeeooni <12.12kimiyeon@gmail.com>
Date:   Thu Jun 27 10:42:07 2019 +0900

    마크다운 정의 (이미지 추가)

commit 8921b3d841ff650c4acb588bf95eecc72c832607
:
```

```
// 마스터브랜치로 체크아웃하고 git log를 확인한 상태

commit 3a44151e1173e34340e3e249bc88c6b907b4e1b9 (HEAD -> master, origin/master, origin/HEAD)
Merge: ddbdb29 a20b95b
Author: yeeooni <12.12kimiyeon@gmail.com>
Date:   Wed Jun 26 00:38:26 2019 +0900

    Merge branch 'Develop_git'

commit a20b95b201ecc6d2d94d94792f95b985eb02ea91 (origin/Develop_git, Develop_git)
Author: yeeooni <12.12kimiyeon@gmail.com>
Date:   Wed Jun 26 00:37:59 2019 +0900

    수정

commit 367915674aeb6bfcea3ad871ee37b86c30223fa7
Author: yeeooni <12.12kimiyeon@gmail.com>
Date:   Wed Jun 26 00:36:18 2019 +0900

    문법 수정

commit ddbdb29186a1a8bc0ba26c53139c6587192761e7
Author: yeeooni <12.12kimiyeon@gmail.com>
Date:   Wed Jun 26 00:33:06 2019 +0900

    수정
:
```

```
// merge --squash 적용 후 마스터 브랜치 git log 상태

kimeuiyeon@nerdy:~/explicit-knowledge$ git log
commit 4f3e1ac7efc41d653186ee414efa5bc097c30a81 (HEAD -> master, origin/master, origin/HEAD)
Author: yeeooni <12.12kimiyeon@gmail.com>
Date:   Thu Jun 27 11:02:46 2019 +0900

    Develop_md merge

commit 3a44151e1173e34340e3e249bc88c6b907b4e1b9
Merge: ddbdb29 a20b95b
Author: yeeooni <12.12kimiyeon@gmail.com>
Date:   Wed Jun 26 00:38:26 2019 +0900

    Merge branch 'Develop_git'

commit a20b95b201ecc6d2d94d94792f95b985eb02ea91 (origin/Develop_git, Develop_git)
Author: yeeooni <12.12kimiyeon@gmail.com>
Date:   Wed Jun 26 00:37:59 2019 +0900

    수정

commit 367915674aeb6bfcea3ad871ee37b86c30223fa7
Author: yeeooni <12.12kimiyeon@gmail.com>
Date:   Wed Jun 26 00:36:18 2019 +0900

    문법 수정
kimeuiyeon@nerdy:~/explicit-knowledge$ git branch
  Develop_git
  Develop_ic
  Develop_md
  Develop_sql
* master
  readme
kimeuiyeon@nerdy:~/explicit-knowledge$ 
```

+ commit --amend
> 이전에 커밋한 내용을 수정하는 작업 

```
// 커밋 내용 수정 전 git log 상태

kimeuiyeon@nerdy:~/explicit-knowledge$ git log
commit cf4e4708b78782974738f65136590f3493f8823b (HEAD -> Develop_git, origin/Develop_git)
Author: yeeooni <12.12kimiyeon@gmail.com>
Date:   Thu Jun 27 11:20:02 2019 +0900

    수평선 추가

// 커밋 내용 수정 후 git log 상태 

commit 864978f152e4fce434488f61da5b31ad37a675af (HEAD -> Develop_git)
Author: yeeooni <12.12kimiyeon@gmail.com>
Date:   Thu Jun 27 11:20:02 2019 +0900

    수평선 추가
    commit : --amend 실행
```

# git 명령어 

+ git log
> log 보기

```
// 로그에 모든 브랜치를 표시하고, 그래프로 표현하고, 브랜치 명을 표시하고, 한줄로 표시할 때

git log --branches --graph --decorate --oneline
```

+ git add 취소하기(파일 상태를 Unstage으로 변경)
```
// 모든 파일이 Staged 상태로 전환
$ git add *

// 파일들의 상태를 확인
$ git status

// `git reset HEAD [file]` 명령을 통해 git add를 취소 가능 
$ git reset HEAD [파일명] 생략하면 파일 전체를 취소
```

+ git commit 취소하기 
```
// commit 목록 확인
$ git log 

// [방법 1] commit을 취소하고 해당 파일들을 Staged 상태로 워킹 디렉토리에 보존
$ git reset --soft HEAD^

// [방법 2] commit을 취소하고 해당 파일들을 Unstaged 상태로 워킹 디렉토리에 보존
$ git reset --mixed HEAD^
$ git reset HEAD^
$ git reset HEAD~2 // 마지막 2개의 commit을 취소

// [방법 3] commit을 취소하고 해당 파일들을 Unstaged 상태로 워킹 디렉토리에서 삭제
$ git reset --hard HEAD^
```

+ git push 취소하기 
```
// 가장 최근의 commit을 취소하고 워킹 디렉토리를 되돌린다.
$ git reset HEAD^

// 우선 브랜치와 HEAD가 지난 몇 달 동안에 가리켰었던 커밋 목록 확인
$ git reflog 
$ git log -g

// 원하는 심점으로 워킹 디렉토리를 되돌린다.
$ git reset HEAD@{number} 또는 $ git reset [commit id]

// 되돌려진 상태에서 다시 commit을 한다.
$ git commit -m "커밋 메시지"

// 원격 저장소에 강제로 push 한다.
$ git push origin [branch name] -f 또는 $ git push origin +[branch name]

```

+ git commit -v
```
// 커밋메시지를 입력하는 화면 아래 코드 diff가 나온다.
```

+ git commit -am '커밋 메시지 내용'
```
`git commit` 명령을 실행할 때 `-a` 옵션을 추가하면 git은 Tracked 상태의 파일을 자동으로 Staging Area에 넣는다.  
`git add` 명령을 실행하는 수고를 덜 수 있다.

```

**CHERRY-PICK**
_브랜치1, 브랜치2가 존재할 때 브랜치2의 특정 commit 내용을 브랜치1로 가져오고 싶을 때_  
_브랜치2의 log를 확인하여 주소를 복사하고, 브랜치1로 checkout 후 git cherry-pick (커밋 주소)_






