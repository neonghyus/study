[리눅스]
(https://nulab.com/ko/learn/software-development/git-tutorial/

https://tortoisegit.org/
https://git-for-windows.github.io/

git : 버전관리, 형상관리를 해주는 프로그램
(github 는 원격의 저장소 이며, 위의 프로그램을 이용해서 pull, push 등을 할 수 있다.)

TortoiseGIT -->  GIT 프로그램을 사용하기 쉽게 만들어 준다. windows 에서...

global : 전역  (email....)
local  : 지역  (폴더, 특정부부에만 정보를 입력)

git config -l   :   git 의 설정값 출력
%USER_HOME%

git init  (저장소 만들기, 초기화)

- 사용자 정보 입력(전역)
$ git config --global user.name fix1004
$ git config --global user.email fix1004@naver.com

$ git config user.name fix1004
$ git config user.email fix1004@naver.com

폴더 생성 test/
폴더 삭제 test/../

  1) Repository name : 원격 저장소 이름 입력
  2) Public : 원격 저장소에 올라갈 소스 무료 (즉 오픈소스가 올라간다)
  3) Private : 비공개 소스(유료, 최근에 3개까지 허용)
  4) Initialize this repository with a README   (저장소 초기화)
  (기존 리포지토리를 가져 오는 경우이 4번째 단계를 건너 뜁니다, 체크시 README 자동 생성됨, 또는 creating a new file 을 클릭하여 생성)
   - README.md 파일은 Quick setup 에서 creating a new file 클릭하여 생성가능
  5) .gitignore 파일을 생성하고, 무시 가능한 파일 추가 ,  라이센스 추가
  6) Create repository 클릭하여 생성




README.md  홈페이지의 인덱스와 비슷하다.
md 파일 : 마크다운 문법을 사용하는 파일,  
HTML 형식의 문서를 쉽게 작성하기 위한 문법  (Chrome -> StackEdit 플러그인 사용시 쉽게 편집 가능)

README.md 생성 및 사용법
Markdown(마크다운)
# 대제목
## 중제목
### 소제목
안녕하세요 여기는 내용을 적으면 됩니다.
>note : GitHub 어디에 써먹을까요?
Blog : [Lsof.co.kr](http://www.lsof.co.kr) - memobox.kr
|Site|URL|
|--|--|
|GitHub|https://github.com/fix1004|
<img src="https://www.kali.org/wp-content/uploads/2015/02/offsec-logo-gray-trans.png">

- 디렉토리 생성은 go to file 을 클릭하여 /디렉토리/파일 식으로 작성하거나 git을 이용하여 업로드 해야 한다.


동작원리
데이터를 가져오거나 프로젝트를 저장할 때마다  그 시점의 파일에 대해서 스냅샷 저장
변경되지 않은 파일은 다시 파일을 저장하지 않고 이전에 지정한 동일한 파일을 링크
데이터를 저장하기 전에 체크섬을 구하고 이 체크섬을 통해 데이터를 관리
SHA-1 해쉬 사용(16진수 문자 40개로 구성,  파일의 내용 또는 디렉토리 구조를 기반으로 계산)
파일 이름이 아닌 컨텐츠의 해쉬 값을 저장(파일명이 변경되도 내용이 동일하면 같은 해쉬)



Working Directory :  Checkout the project(즉 원격 저장소의 리포지터리를 클론시, 초기화시) 
Stagin Area : 파일을 생성시(ADD)
Repository : Commit 시 저장된다.


Watch : 관심있는 프로젝트의 변경사항 알림이 오도록 설정  (unwatch)
Star : 좋아요
fork : 프로젝트 가지고 오기(종속)
프로젝트가 복제 되므로 지역 저장소에 다운및 수정이 가능하다(GitHub, 오픈소스, 비공개는 제외)
fork 가 많을 수록 관심이 많다고 생각 할 수 있다.
Code : Source 위치 하는곳
issues : 이슈관리,(이슈 트래킹 도구), 협업시 이력관리, 소스의 변경 관리등 유용하게 사용
Pull Request : fork 후 버그, 기능추가등 설정후 Pull Request 하면 기존(base) 프로젝트 진행자가 기존 프로젝트에 추가 할 수 있다.
Wiki : 메뉴얼
insights (Pulse, Graphs)
Pulse : 해당 프로젝트의 변화들과 외부에서 주는 관심들을 보여준다.
Graphs : 프로젝트 현황을 시각화

commits : 몇개의 버전이 존재하는가 (클릭 확인)
releases : 정식버전
contributors : 등록 사용자(수정가능자)

브랜치 : 독립적으로 어떤 작업을 진행하기 위한 개념 필요에 의해 만들어지는 각각의 브랜치는 다른 브랜치의 영향을 
받지 않는다, 즉 여러 작업을 동시에 진행 가능하다, 또한  다른 브랜치와 병합(Merge) 가능하다.



…or create a new repository on the command line
echo "# apache" >> README.md
git init
git add README.md
git commit -m "first commit"
git branch -M master
git remote add origin git@github.com:fix1004/apache.git
git push -u origin master


# ssh-keygen -t rsa -b 4096 -C fix1004@naver.com  ->  id_rsa.pub 의 값을 GitHub에 등록한다.   (.ssh 파일을 백업후 진행)
# eval "$(ssh-agent -s)"  
SSH 에이전트를 시작하고, 환경 변수(SSH_AUTH_SOCK와 SSH_AGENT_PID)를 설정하여 현재 세션에서 SSH 에이전트를 사용할 수 있도록 한다.
# ssh-add ~/.ssh/id_rsa
~/.ssh/id_rsa 파일에 있는 SSH 개인 키를 SSH 에이전트에 추가한다. 출력된 Identity added: /root/.ssh/id_rsa (fix1004@naver.com)은 해당 키가 성공적으로 추가되었음을 나타낸다.
SSH 에이전트는 키를 관리하고, SSH 연결 시 자동으로 인증을 처리할 수 있게 된다.


# git remote -v   (원격 주소 확인)
# git remote add origin git@github.com:fix1004/apache.git
  git remote add origin 사이트 주소
  git remote remove origin  (삭제)
  
https://github.com/github/gitignore (샘플 파일 제공)
.gitignore  --->  파일이나 디텍토리 목록을 저장하고, 해당 파일/디렉토리 리스트는 무시한다. (git에서)

# git push -u origin master




# 전체 정리 ---------------------
[SSH Key Linux]
SSH : cd ~/.ssh 로 이동 
# ssh-keygen -t rsa -b 4096 -C fix1004@naver.com  ->  id_rsa.pub 의 값을 GitHub에 등록한다.   (.ssh 파일을 백업후 진행)
# eval "$(ssh-agent -s)"  
SSH 에이전트를 시작하고, 환경 변수(SSH_AUTH_SOCK와 SSH_AGENT_PID)를 설정하여 현재 세션에서 SSH 에이전트를 사용할 수 있도록 한다.
# ssh-add ~/.ssh/id_rsa
~/.ssh/id_rsa 파일에 있는 SSH 개인 키를 SSH 에이전트에 추가한다. 출력된 Identity added: /root/.ssh/id_rsa (fix1004@naver.com)은 해당 키가 성공적으로 추가되었음을 나타낸다.
SSH 에이전트는 키를 관리하고, SSH 연결 시 자동으로 인증을 처리할 수 있게 된다.

----------------------
[ 로컬 저장소 생성 - Git Bash Here ]
0. $ git log				(GIT 로그 확인)
1. $ git status 			(GIT 레포지터리 상태 조회)
2. $ git config -l 			(환경설정 보기)
3. $ git config --global user.name fix1004	(사용자/이메일 전역설정)
4. $ git config --global user.email fix1004@naver.com
5. $ git init				(로컬 리포지터리 생성)
6. $ git remote -v			(원격 내용 확인)
7. $ git remote add origin 사이트주소		(원격 주소 등록, origin)
8. $ git remote remove origin ( 삭제 )
9. $ git add .				모든파일 스테이징 / git add -i : 메뉴형식
10. $ git rm --cached .       .은 <file> 이다. 	스테이징 제거   git rm --cached test.  즉 add 제거
11. $ git commit <file>			특정 파일 커밋(vim)12. $ git commit -m "메시지" <file> 또는 ( . )      	타이틀 만으로 기록하고 싶을 경우에 사용 (주로 사용)
13. $ git commit -a -m "메시지"		전체 스테이징 및 커밋 (ADD를 하지 않아도 된다)
14. $ .gitignore  	     ( *.bak 등… )  제외파일 - https://github.com/github/gitignore (샘플 파일 제공)

- push(원격 저장)
15. $ git push -u origin master
      git push -u origin master : 로컬 저장소의 마스터 브랜치와 원격 저장소의 기본 브랜치를 동기화 시킴
      (기본 : master, 또는 git push --set-upstream origin master)
      git push -u origin master  로 병합이 되지 않을때  git push -f origin master 로 강제 push 하자

- pull(로컬 저장)
16. $ git pull origin master 
     git pull [alias] [branch] : 원격 저장소의 내용을 로컬에 받고 자동으로 Merge 수행
     원격 저장소로부터 필요한 파일을 다운 + 병합
     지역 브랜치와, 원격 저장소 origin/master 가 같은 위치를 가리킨다.
  
git pull 오류 발생시('fatal: 관계 없는 커밋 내역의 병합을 거부합니다')아래 내용 순서대로 실행1. git fetch --all		git remote 에서 전체 내용을 받아온다.- 병합 오류시 :  git merge --allow-unrelated-histories origin/master   (병합할 저장소 이름/병합하고 싶은 branch 이름)- 해결이 안될경우 아래 명령 실행
2. git reset --hard origin/master	수정된 내역을 지우고 이전내용으로 복구한다.
   -  원격 저장소의 master 브랜치와 로컬 브랜치를 일치시킨다.   -  원격 저장소의 최신 커밋 내용으로 로컬 브랜치가 강제로 리셋되어, 삭제된 파일들이 원격 저장소에서 다시 복원된다.
3. git pull origin master		현재 작업하고있는 로컬에 커밋을 병합한다.

17 # 주의1 : git reset --hard origin/master  실행으로 내용이 지워졌을때


----------------   아래 복구 방법  ----------------
# git reflog
aea0dc1 (HEAD -> master, origin/master) HEAD@{0}: reset: moving to HEAD
aea0dc1 (HEAD -> master, origin/master) HEAD@{1}: reset: moving to HEAD~1
0bb4223 HEAD@{2}: revert: Revert "Create README.md"
aea0dc1 (HEAD -> master, origin/master) HEAD@{3}: reset: moving to origin/master
7b7181d HEAD@{4}: commit (initial): 1. add files
# git reset --hard 7b7181d

주의2 : 병합할 저장소와 유지할 저장소에 동일한 이름의 파일이 없도록 한다. (README.md 등)
$ git remote add <병합할 저장소 이름> <병합할 저장소 주소>
$ git fetch <병합할 저장소 이름>
$ git merge --allow-unrelated-histories <병합할 저장소 이름>/<병합하고 싶은 branch 이름>
 - 잘 안될경우 git reset --hard 방법을 진행
$ git remote remove <병합할 저장소 이름>
$ git commit -m "Merge : <병합할 저장소 이름> into <유지할 저장소 이름>“

1) 원격 저장소에 저장된 커밋 기록들을 가져온다. (병합은 하지 않는다.)
# git fetch --all
2) 연관이 없는 기록들을 병합한다.
# git merge --allow-unrelated-histories origin/master
3) # git add .
4) # git commit -m "Add Files" .
5) git pull은 git fetch와 git merge가 합쳐진 명령어
# git push origin master

- 설명
새로운 커밋은 이전의 커밋기록과 연결되어야 하므로 서로 다른 원격 저장소를 병합할 때에는 refusing to merge unrelate histories error가 발생하거나 아예 merge가 불가능하게 된다. 
이 때 --allow-unrelated-histories 옵션을 사용하면 문제없이 병합이 완료된다


-------------------------------------   log / clone  -------------------------------------
18. $ git log --decorate --all --graph		( 로그 그래프로 보기 )

19. $ git clone [URL] : 공개된 원격 저장소를 다운로드 

- git 로그 코드 정리
git log --pretty=online
- git Head 변경 이력 확인
git reflog
- git reset으로 commit 복원
git reset --hard "CommitID"
- git reset으로 head 복원(현재부터 6개 이전으로 복원)
git reset HEAD~6
- git revert으로 commit 복원
git revert "CommitID”


)
