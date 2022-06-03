# TIL Day 01

> 2022년 06월 02일 목요일



## Why Git & Github?

![Git로고](README.assets/168756716-68f9aebb-380f-4897-8141-78d8403f6113-20220603175936081.png)



### Git

- 분산 버전 관리 프로그램
- 백업, 복구, 협업을 위해 사용
- [Git 공식문서](https://git-scm.com/book/ko/v2)



### Github

- Git을 사용하는 프로젝트의 협업을 위한 웹호스팅 서비스
- 포트폴리오를 자랑할 수 있는 공간
- 1일 1커밋 하기
  - [이동욱님 Github 계정](https://github.com/jojoldu)



## CLI

> CLI (Command Line Interface, 커맨드 라인 인터페이스)는 터미널을 통해 사용자와 컴퓨터가 상호 작용하는 방식을 뜻한다.



**터미널 명령어 정리**

|                            명령어                            |                             설명                             |
| :----------------------------------------------------------: | :----------------------------------------------------------: |
|                            mkdir                             |                          폴더 생성                           |
|                            touch                             |                          파일 생성                           |
|                              ls                              |                  현재 폴더의 파일 목록 출력                  |
|                              cd                              |                       다른 폴더로 이동                       |
|                              rm                              |               파일 삭제 / 폴더 삭제 (-r 옵션)                |
| pwd<br />ctrl + L<br />화살표 위아래<br />상대경로<br />절대경로 | 현재 위치<br />스크롤 내리기 <br />이전 라인 가져오기<br /> . (현재), .. (상위)  <br />/c/Users/chelsea/test |

**예시**

```bash
$ mkdir test

$ touch a.txt

$ ls
$ ls -a

$ cd ..
$ cd test

$ rm a.txt
$ rm -r test
```



**명령어 실습** 

1. 바탕화면에 practice.txt 파일 만들기 (touch 명령어)

2. 파일 있는지 확인하기 (ls 명령어)

3. CLI 디렉토리 만들고, practice.txt를 CLI로 이동하기 (mkdir 명령어 / mv 명령어)

4. CLI 디렉토리로 경로 이동하여, 파일이 잘 옮겨 졌는지 확인 (cd 명령어, ls 명령어)

5. practice 파일을 삭제 (rm 명령어)

   - tab을 통해 자동완성가능

6. 다시 바탕화면 경로로 이동 (cd 명령어)

   ```bash
   % cd desktop
   % touch practice.txt
   % ls
   practice.txt
   
   % mkdir CLI
   % ls  
   CLI
   practice.txt
   
   % mv practice.txt CLI/
   % cd CLI
   % ls
   practice.txt
   
   % rm practice.txt 
   % cd desktop
   % ls
   CLI
   ```

   

## Visual Studio Code

> Visual Studio Code (비주얼 스튜디오 코드)는 마이크로소프트에서 개발한 텍스트 에디터의 한 종류이다.



**장점**

- Windows, Mac, Linux 운영체제를 모두 지원한다.

- 기존 개발 도구보다 빠르고 가볍다.

- Extension을 통해 다양한 기능을 설치할 수 있어서, 무한한 확장성을 가진다.

- 무료로 사용 가능하다.

  

**Git Bash 연동하기**

1. 터미널을 연다. (Ctrl + `)
2. 화살표를 누르고 *Select Default Profile*을 클릭한다.
3. *Git Bash*를 선택한다.
4. 휴지통을 눌러서 터미널을 종료하고, 재시작한다.
   - 휴지통은 Kill Terminal 로써, 터미널 자체를 아예 종료한다.
   - 닫기는 Close Terminal 로써, 터미널을 종료하지 않고 창만 보이지 않게 만든다.

5. 기본 터미널이 *Git Bash*로 열리는지 확인한다.



## Markdown

> Markdown (마크다운)은 일반 텍스트 기반의 경량 Markup (마크업) 언어이다.



**Markup (마크업) 이란?**

- 마크(Mark)로 둘러싸인 언어를 뜻한다. 마크란 글의 역할을 지정하는 표시이다.
- HTML도 마크업 언어인데, 글에 제목의 역할을 부여할 때` <h1>제목1</h1>` 과 같이 작성한다.



**마크다운의 장점과 단점**

- 장점
  - 문법이 직관적이고 쉽다.
  - 지원 가능한 플랫폼과 프로그램이 다양하다.
- 단점
  - 표준이 없어서 사용자마다 문법이 상이하다.
  - 모든 HTML의 기능을 대신하지는 못한다.



**주의 사항**

- 마크다운의 본질은 글에 역할을 부여하는 것이다.
- 반드시 역할에 맞는 마크다운 문법을 작성한다. 글씨를 키우고 싶다고 해서 본문에 제목의 역할을 부여하면 안된다.



**참고 자료**

- [Markdown Guide](https://www.markdownguide.org/basic-syntax/)
- [마크다운 문법 정리](https://gist.github.com/ihoneymon/652be052a0727ad59601)





### VS Code에서 git 사용하기

---

**시작하기**

- 파일> open folder
- Ctrl + ` 으로 터미널 들어가기 (영어 자판에서 해야함)



**git 설정하기**

1. ***git init*** : git으로 관리 시작
   - 디렉토리당 한번만
   - 홈폴더나 바탕화면에 하지 않도록 주의
   - ***git ls -a***: 숨김폴더에 .git/ 가 생겼는지 확인!



2. ***git status*** : 파일 상태 확인(중요)

   - 상태를 확인해서 무엇을 해야할 지 알 수 있음

      

3. ***git add 파일명*** : 무대 위로 올리기

   

4. ***git commit -m “커밋사유”*** : 변경 사항 기록

   - git commit -m “first commit”

   - 커밋사유 안 써서 vim 나오면 *esc 누르고 :q* 입력

     

5. ***git config 설정***

   - git config --global user.email “your@email”

   - git config --global user.name “your name”

   - git config --global --list

     

6. ***git log*** : 커밋 내역 확인

   - *git log --oneline* : 로그 정보 한 줄 요약

     

7. ***git diff*** : 커밋들끼리 비교

   - git diff 해시값1 해시값2

     

8. ***github과 연결하기***

   - ***git remote add origin URL***

   - ***git remote -v***

   - ***git remote rm origin*** : origin 삭제

     

9. ***git push*** : github에 local commits 올리기

   - git push origin master : origin의 master branch에 git 올려줘!

```bash
#git 지정하기
git-practice % git init
Initialized empty Git repository in /Users/git-practice/.git/

#a.txt 파일 만들기
git-practice % touch a.txt

#git staging area에 파일 올리기
git-practice % git add a.txt

#add 한 후의 상태: 'new file'
git-practice % git status
On branch master
No commits yet
Changes to be committed:
  (use "git rm --cached <file>..." to unstage)
        new file:   a.txt

#git에 커밋하기
git-practice % git commit -m "first commit"

 1 file changed, 1 insertion(+)
 create mode 100644 a.txt

#git에 config 등록하기(첫 커밋 후 사용자 질문함)
git-practice % git config --global user.name "username"
git-practice % git config --global user.email "user@email"

#config에 등록한 정보 확인
git-practice % git config --global --list 
user.name=username
user.email=user@email

#git 로그 확인하기
git-practice % git log
commit 2f2c2dfd1d71baf3231c354a5e64695f3f75553b (HEAD -> master)
Author: user [user-ui-MacBookPro.local](<mailto:user-ui-MacBookPro.local>)
Date:   Thu Jun 2 15:09:23 2022 +0900
first commit

#로그 한줄 확인
git-practice % git log --oneline
2f2c2df (HEAD -> master) first commit

#파일 편집 후 두 번째 커밋
git-practice % git status
On branch master
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   a.txt
no changes added to commit (use "git add" and/or "git commit -a")

git-practice % git add a.txt
git-practice % git commit -m "second commit"
[master b18dc0b] second commit
 1 file changed, 1 insertion(+)

git-practice % git status
On branch master
nothing to commit, working tree clean

git-practice % git log --oneline
b18dc0b (HEAD -> master) second commit
2f2c2df first commit

#github에 연결하기
git-practice % git remote add origin <https://github.com/username/git-practice.git%>

#연결 확인하기
git-practice % git remote -v
origin  <https://github.com/username/git-practice.git> (fetch)
origin  <https://github.com/username/git-practice.git> (push)

#github에 올리기
git-practice % git push origin master
```



### commit 실습

```bash
git-practice % git add commit_practice.md
git-practice % git status
On branch master
Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        new file:   commit_practice.md

git-practice % git commit -m "solve 1 problem"
[master beb0eb4] solve 1 problem
 1 file changed, 36 insertions(+)
 create mode 100644 commit_practice.md

git-practice % git add commit_practice.md
git-practice % git commit -m "solve 2 problem"
[master 420bdff] solve 2 problem
 1 file changed, 2 insertions(+), 2 deletions(-)

git-practice % git add commit_practice.md
git-practice % git commit -m "solve 3 problem"
[master 0308500] solve 3 problem
 1 file changed, 2 insertions(+), 2 deletions(-)

git-practice % git add commit_practice.md
git-practice % git commit -m "solve 4 problem"
[master d3dda6c] solve 4 problem
 1 file changed, 2 insertions(+), 2 deletions(-)

git-practice % git add commit_practice.md
git-practice % git commit -m "solve 5 problem"
[master be47276] solve 5 problem
 1 file changed, 2 insertions(+), 2 deletions(-)

```



---

### github settings

- 프로필 → settings → repositories → default에  *‘master’* 입력하고 *update*

**Repository 생성**

- 우측 상단 + 버튼 눌러서 생성

**Github 연결**

- local 과 github(remote)를 연결하기 위해서 다리를 놓아줘야 함

  - ***git remote add origin URL***

  ```bash
  % git remote add origin <https://github.com/username/git-practice.git%>
  ```

  - ***git remote -v*** : remote 된 것 확인하기

  ```bash
  % git remote add origin <https://github.com/username/git-practice.git%>
  
  % git remote -v
  origin  <https://github.com/username/git-practice.git> (fetch)
  origin  <https://github.com/username/git-practice.git> (push)
  ```

  - ***git remove rm origin*** 으로 삭제 가능

- ***git push*** : github에 local commits 올리기

  

### Remote 연결 실습

***(github)***

1. TIL 레포지토리를 만들고 URL 을 복사

***(local)***

1. TIL 레포지토리를 만든다 (TIL 폴더 만든 후, git init)
2. README.md 파일을 만든다.
3. 편집 후 add -> commit으로 변경사항을 기록한다

***(remote와 local 길 연결)***

1. git remote add origin URL
2. git remote -v

***(local에서 remote로 변경 사항 올리기)***
git push origin master

```bash
#README.md 생성 및 내용 작성 후 커밋
TIL % git init
TIL % touch README.md
TIL % git add .
TIL % git commit -m "README"

#repository 연결 후 push하기
TIL % git remote add origin https://github.com/username/TIL.git
TIL % git remote -v
origin  https://github.com/username/TIL.git (fetch)
origin  https://github.com/username/TIL.git (push)
TIL % git push origin master

```



---

### Github 연결(하향식)

**1. git clone**

- 이미 git 레포지토리로 설정된 폴더에 clone을 받지 않도록 주의!
- git clone origin URL
- 초기 설정을 하지 않아도 원본 레포지토리의 설정을 그대로 따라감

**2. git pull**

- 로컬1 (push)→ remote →(pull) 로컬2

- git pull을 안하고 작업 후 push 했을 때 충돌!

  → 사용자에게 덮어쓸지 다시 pull하고 작업할 지 선택권을 줌

- 충돌된 파일 중 하나 선택 / 두 가지 내용 모두 합쳐서 저장 / 그냥 다른 내용으로 편집하기



### clone 실습

```bash
#터미널에서 clone 설치하기
desktop % git clone <https://github.com/username/clone_practice.git>
Cloning into 'clone_practice'...
remote: Enumerating objects: 3, done.
remote: Counting objects: 100% (3/3), done.
remote: Total 3 (delta 0), reused 0 (delta 0), pack-reused 0
Receiving objects: 100% (3/3), done.

#vscode에서 local 커밋 후 push
clone_practice % git add .
clone_practice % git commit -m "local 1"
[master 671faee] local 1
 1 file changed, 2 insertions(+), 1 deletion(-)

clone_practice % git push origin master
Enumerating objects: 5, done.
Counting objects: 100% (5/5), done.
Writing objects: 100% (3/3), 275 bytes | 275.00 KiB/s, done.
Total 3 (delta 0), reused 0 (delta 0), pack-reused 0
To <https://github.com/username/clone_practice.git>
   1d6d64f..671faee  master -> master

#remote(clone_practice)레포지토리에서 수정 후 local에 pull하기
clone_practice % git pull origin master
...
Unpacking objects: 100% (6/6), 1.29 KiB | 263.00 KiB/s, done.
From <https://github.com/username/clone_practice>
 * branch            master     -> FETCH_HEAD
   671faee..e50ae40  master     -> origin/master
Updating 671faee..e50ae40
Fast-forward
 README.md | 3 ++-
 1 file changed, 2 insertions(+), 1 deletion(-)

#local에서 내용 추가 후 커밋하기
clone_practice % git add .
clone_practice % git commit -m "local 2"
[master 3c87616] local 2
 1 file changed, 2 insertions(+), 1 deletion(-)

#local 2까지 커밋한 상태
clone_practice % git log --oneline
3c87616 (HEAD -> master) local 2
e50ae40 (origin/master, origin/HEAD) Update README.md
6b1db1c Update README.md
671faee local 1
1d6d64f Initial commit

#origin.master보다 한 단계 더 앞선 상태(=local에서 내용 수정 됨)
clone_practice % git status
On branch master
Your branch is ahead of 'origin/master' by 1 commit.
  (use "git push" to publish your local commits)

nothing to commit, working tree clean

#remote(clone_practice)레포지토리에 push/pull 안 한 상태로 수정

#local에서 local2 커밋 push 시도 -> rejected 발생
clone_practice % git push origin master
To <https://github.com/username/clone_practice.git>
 ! [rejected]        master -> master (fetch first)
error: failed to push some refs to '<https://github.com/username/clone_practice.git>'
hint: Updates were rejected because the remote contains work that you do
hint: not have locally. This is usually caused by another repository pushing
hint: to the same ref. You may want to first integrate the remote changes
hint: (e.g., 'git pull ...') before pushing again.
hint: See the 'Note about fast-forwards' in 'git push --help' for details.

#오류 해결하기 위해 pull
clone_practice % git pull origin master
hint: ...
remote: ...
Unpacking objects: 100% (3/3), 670 bytes | 223.00 KiB/s, done.
From <https://github.com/username/clone_practice>
 * branch            master     -> FETCH_HEAD
   e50ae40..ccdd6a8  master     -> origin/master
Auto-merging README.md
CONFLICT (content): Merge conflict in README.md
Automatic merge failed; fix conflicts and then commit the result.

#merging단계에서 수정사항 저장 후 commit하기 (master|MERGING) -> (master)
clone_practice % git add .
clone_practice % git commit -m "fix conflict"
[master 32171fc] fix conflict

clone_practice % git log --oneline
32171fc (HEAD -> master) fix conflict
ccdd6a8 (origin/master, origin/HEAD) Update README.md
3c87616 local 2
e50ae40 Update README.md
6b1db1c Update README.md
671faee local 1
1d6d64f Initial commit
```



## git 버전관리

**git 버전 관리하지 않아도 되는 파일**

- 비밀번호, AWS 토큰 → 민감정보

- 운영체제, 언어에 따라 생성되는 파일



**.gitignore 파일** : 이 안에 작성하면 버전관리하지 않음

- git에서 한 번 staging area에 올라갔던 내용은 .gitignore에 아무리 추가해도 제외되지 않음
- 따라서 add하기 전에 .gitignore에 넣어줘야함!
- [gitignore](https://www.toptal.com/developers/gitignore/) 사이트





## Branch

> 버전 관리의 꽃. “협업”

- branch = 나뭇가지

- 목적: 이전 commit들을 가진 독립적인 공간에서 master 브랜치에 영향없이 작업할 수 있도록 함

- branch 실습

  1. ***git branch*** : 브랜치 목록 확인
  2. ***git branch 브랜치명*** : 브랜치 생성
  3. ***git switch 브랜치명*** : 브랜치 이동
     - switch 후 다시 git branch 하면 *표시가 있는 곳이 작업하고 있는 브랜치
  4. ***git switch -c 브랜치명*** : 브랜치 생성과 동시에 이동
  5. ***git branch -d 브랜치명*** : 마스터 브랜치에 병합된 브랜치 삭제
  6. ***git branch -D 브랜치명*** : 마스터 브랜치에 병합하지 않은 상태에서 삭제

  ```bash
  #git 시작 후 test.txt 파일 만들기
  git-branch-practice % git init
  Initialized empty Git repository in /Users/user/Git특강/git-branch-practice/.git/
  git-branch-practice % touch test.txt
  
  #test.txt에 master-1, master-2, master-3 각각 커밋 남기기
  git-branch-practice % git add .
  git-branch-practice % git commit -m "master-1"
  git-branch-practice % git add .
  git-branch-practice % git commit -m "master-2"
  git-branch-practice % git add . 
  git-branch-practice % git commit -m "master-3"
  
  #변경사항 확인하기 - 3커밋
  git-branch-practice % git log --oneline
  16e95e3 (HEAD -> master) master-3
  60dc77c master-2
  1cd9153 master-1
  
  #login 브랜치 만들고 브랜치 목록 확인
  git-branch-practice % git branch login
  git-branch-practice % git branch
    login
  * master
  
  #master 브랜치에서 master-4 작성 후 커밋하기
  git-branch-practice % git add .
  git-branch-practice % git commit -m "master-4"
  
  #login 브랜치로 이동 후 test_login.txt 만들고 login-1 커밋 생성
  git-branch-practice % git switch login
  Switched to branch 'login'
  
  git-branch-practice % touch test_login.txt
  git-branch-practice % git add .
  git-branch-practice % git commit -m "login-1"
  
  #master 브랜치로 이동 후 작업 내용 확인
  git-branch-practice % git switch master
  Switched to branch 'master'
  
  git-branch-practice % git log --oneline --all --graph
  * 53dc93b (login) login-1
  | * a99b857 (HEAD -> master) master-4
  |/  
  * 16e95e3 master-3
  * 60dc77c master-2
  * 1cd9153 master-1
  
  #master 브랜치에서 login 브랜치 병합하기 - 충돌발생!
  git-branch-practice % git merge login
  Auto-merging test.txt
  CONFLICT (content): Merge conflict in test.txt
  Automatic merge failed; fix conflicts and then commit the result.
  
  #충돌 내용 수정 후 커밋하기
  git-branch-practice % git add .
  git-branch-practice % git commit -m "fix conflict"
  [master a8e4f62] fix conflict
  (base) user-ui-MacBookPro git-branch-practice % git log --oneline --all --graph
  *   a8e4f62 (HEAD -> master) fix conflict
  |\\  
  | * 53dc93b (login) login-1
  * | a99b857 master-4
  |/  
  * 16e95e3 master-3
  * 60dc77c master-2
  * 1cd9153 master-1
  
  #login 브랜치 삭제하기
  git-branch-practice % git branch -d login
  Deleted branch login (was 53dc93b).
  ```



## Git Workflow

1. **Feature Branch Workflow** (저장소의 소유권이 **있는** 경우)

   - 기능 추가를 위해 각각 branch 생성 및 기능 구현

     - 예) A - login, B - signup , C - profile

   - 각각의 기능 구현 후 원격 저장소에 브랜치 반영

     - 예) A - git push origin login

   - 병합 후 병합 완료된 브랜치 삭제 → github 상에서의 master에는 각 기능이 모두 반영됨

   - 병합된 master의 내용을 다시 pull 해서 이후 작업을 진행함

   - 새로운 기능 추가를 위해 branch 생성 및 과정 반복

     

2. **Forking Workflow** (저장소의 소유권이 **없는** 경우)

   - 소유권이 없는 원격 저장소를 fork를 통해 복제
   - 복제해온 내용을 clone으로 복제
     - 이 때 추후 로컬 저장소를 원본 원격 저장소와 동기화하기 위해 원본 URL 연결
     - git remote add upstream 원본 URL
   - 기능 추가를 위해 branch 생성 및 기능 구현
   - 기능 구현 후 원격 저장소에 브랜치 반영(이때 원본이 아닌 복제(origin)로 보냄)
     - git push origin login
     - push 할 때 origin master 하지 말자! 브랜치로 올리면 pr(협업) 경험이 있다는 것을 증명 가능
   - origin에서 upstream으로 pull request
   - push는 origin, pull 은 master로!



### Forking Workflow 실습

```bash
#원본 저장소에서 fork 해서 clone 다운로드
#clone 폴더에서 작업
dse1516-acrostic-poem % git branch username
dse1516-acrostic-poem % git switch username

#이름으로 브랜치 생성해서 4행시 작성 후 username 브랜치로 푸시
dse1516-acrostic-poem % git add .
dse1516-acrostic-poem % git commit -m "n poem"
dse1516-acrostic-poem % git push origin username

#github에서 원본 저장소로 pull request

#원본저장소에서 merge 해주면 local에서 pull URL 연결 후 pull하기
dse1516-acrostic-poem % git remote add upstream 원본URL
dse1516-acrostic-poem % git pull origin master
```



