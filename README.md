# TIL Day 01

> 2022년 06월 02일 목요일



## Why Git & Github?

![img](TIL_Day_01.assets/168756716-68f9aebb-380f-4897-8141-78d8403f6113.png)



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
Initialized empty Git repository in /Users/youngrong/git-practice/.git/

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
git-practice % git config --global user.name "brightgemm"
git-practice % git config --global user.email "dudfhd0107@g.skku.edu"

#config에 등록한 정보 확인
git-practice % git config --global --list 
user.name=brightgemm
user.email=dudfhd0107@g.skku.edu

#git 로그 확인하기
git-practice % git log
commit 2f2c2dfd1d71baf3231c354a5e64695f3f75553b (HEAD -> master)
Author: 문영롱 [youngrong@mun-yeonglong-ui-MacBookPro.local](<mailto:youngrong@mun-yeonglong-ui-MacBookPro.local>)
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
git-practice % git remote add origin <https://github.com/brightgemm/git-practice.git%>

#연결 확인하기
git-practice % git remote -v
origin  <https://github.com/brightgemm/git-practice.git> (fetch)
origin  <https://github.com/brightgemm/git-practice.git> (push)

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
  % git remote add origin <https://github.com/brightgemm/git-practice.git%>
  ```

  - ***git remote -v*** : remote 된 것 확인하기

  ```bash
  % git remote add origin <https://github.com/brightgemm/git-practice.git%>
  
  % git remote -v
  origin  <https://github.com/brightgemm/git-practice.git> (fetch)
  origin  <https://github.com/brightgemm/git-practice.git> (push)
  ```

  - ***git remove rm origin*** 으로 삭제 가능

- ***git push*** : github에 local commits 올리기



### Remote 연결 실습

(github)

1. TIL 레포지토리를 만든다
2. URL 을 복사한다.

(local)

1. TIL 레포지토리를 만든다 (TIL 폴더 만든 후, git init)
2. README.md 파일을 만든다.
3. 편집 후,
   add -> commit으로 변경사항을 기록한다

(remote와 local 길 연결)

1. git remote add origin URL
2. git remote -v

(local에서 remote로 변경 사항 올리기)
git push origin master

* 주의 : URL은 .git으로 끝나야 함 
  origin의 오타주의