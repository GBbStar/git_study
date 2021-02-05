# 상황
  - [개인관리](#개인관리)
  - [협업](#협업)
  - [기타](#기타)
  - [오류해결](#오류해결)
  
# 개인관리
  1. new repository 생성(웹상의 가상 폴더 생성)
  2. 로컬 폴더 생성
  3. 로컬 폴더 우클릭 후 git bash here를 누르고 git init을 통해 git 전용으로 사용을 명시 > 폴더안에 .git 생성됨
  4. git remote add origin [repository address]를 통해 가상 폴더와 로컬 폴더를 연결

  ! 알아둬야 할 점
  1. push 전에는 반드시 pull을 해야한다
  2. add는 깃을 통해 반영할 파일들을 지정하는 것이다
  3. commit은 add를 통해 지정된 파일들에 대한 변화들만 저장한다
  4. 


# 협업
  순서
  1. 협업하고자 하는 프로젝트를 fork
  2. 원래 프로젝트 주소를 git clone
  3. branch 생성 및 checkout
  4. git add 및 git commit
  5. git push origin 새로운 브런치
  6. 깃허브의 Create new pull request 선택
  7. 좌측의 base-fork는 본래 프로젝트의 main을, 우측의 head-fork는 자신이 수정한 프로젝트의 브랜치를 선택
  8. 자신이 수정한 부분을 상세하게 기록
  9. merge 대기



# 기타
  - git pull origin master 
  가상 폴더에 있는 자료들을 로컬 폴더로 끌어옴 (pull)

  - git status
  현재 로컬 폴더와 Git과의 싱크 상태를 나타냄

  - git add .
  로컬 폴더와 가상 폴더 사이에 변경된 폴더들을 추적하는 것

  - git commit -m "message"
  commit을 주석과 함께 달아놓는 것
  git 
  - git commit --help
  커밋 옵션들이 나옴

  - git commit -am ""
  한번이라도 add 된 파일을 추가적인 add 없이 바로 커밋

  - git push origin +master
  실제로 git에 push 하는 것

  - git
  사용할 수 있는 명령어들 출력

  - ls -al 
  파일 목록들

  - git config --global user.name ~~
  - git config --global uesr.email ~~
  자신이 수정한 파일들에 담길 이름과 이메일 (구분가능)

  - git log
  변경사항들과 commit 메세지 확인
  // 각 commit들은 고유한 주소를 가짐

  - git log -p
  각 commit 사이 소스상의 변화사항을 확인 가능

  - git diff [commit id1]..[commit id2]

  - git reset [commit id] --hard
  커밋 취소 : 해당 id까지만 남겨두고 그 이후의 것을 초기화

  - git revert
  마찬가지로 커밋취소임, 단 동시에 새로운 버젼을 만든다

  - git diff 해시코드
  이전버전과 현재 버전의 파일에서 어떠한 부분이 변경되었는지 확인해보고 싶다면



# 브런치
  * git init

  * git remote add origin https://github.com/~.git
  
  * git pull origin 브런치이름

  * git checkout -b 브런치이름

  * git add .

  * git commit -m "어쩌구"

  * git push origin 브런치이름

  * git branch
      현재 브랜치 목록 출력

  * git branch [name]
      새로운 브랜치 생성

  * git checkout [name]
      해당 이름의 브랜치로 변경

  * git log --branches --decorate
      브랜치들간의 log 비교

  * git log --branches --decorate --graph --oneline
      브랜치들간의 log 비교를 최소한의 표현을 하는 그래프를 통해 

  * git log -- branches --decorate --graph
      브랜치들간의 log 비교를 그래프를 통해 알려줌

  * git log [name1]..[name2]
      (브런치)name1에는 없고 name2에는 있는 기록을 보여줌

  * git log -p [name1]..[name2]
      (브런치)name1에는 없고 name2에는 있는 기록을 내용과 함께 보여줌

  * git branch -d [name]
      name의 브런치 삭제


  * 깃 병합 merge

  1. git checkout [name1]
  병합이 반영될 브런치, name1으로 체크아웃

  2. git merge [name2]
  병합할 내용의 브런치, name2을 결정

  ===================================================================

  * 깃 stash

  - 언제 사용하는가
  브런치에서 하고 있던 작업을 마무리(커밋)하지 못하는 상황에서 다른 브런치로 체크아웃해야 할 때

  - git stash 
  지금 작업중인 내용들을 임시로 저장

  - git stash apply
  임시로 저장한 내용들을 다시 불러옴. (list 상에서 가장 위쪽, 최근걸 적용)

  - git stash list
  기존의 저장한 내용들의 기록. 따로 조작하지 않는다면 삭제되지 않음

  - git stash drop
  가장 최근에 임시저장된 기록을 삭제.

  - git stash pop
  가장 최근에 임시저장된 기록을 다시 불러온 후, 삭제

  - git stash --hard 

  ===================================================================

  //
  먼저 변경 사항들을 트랙한다
  그 후 커밋을 달고 
  push을 통해서 가상 폴더로 올린다
  반대로 로컬로 들고오고 싶다면 pull을 통해 들고온다
  //

  유튜브 - 생활코딩 : "본질과 혁신"



  (코딩 온 웹 = 코딩을 온라인 상으로 연습할 때 유용)



  * 커밋도 오브젝트 파일안에 저장된다 = 커밋도 일종의 오브젝트임
  * 커밋 오브젝트에는 누가 했는지, tree를 통해 링크가 걸려있다 (tree에는 해당 버젼에 해당되는 파일과 파일 내용들이 들어가 있다)
  * 커밋에 parent는 이전 커밋 링크가 나오며, 새로운 tree 링크를 가진다 = 새로운 오브젝트임
  == 즉 이전 커밋 트리 링크 (parent)를 통해 다루는 자료들을 보면 수정 전 값을 볼 수 있고, 이후의 커밋 트리 링크를 통해 수정된 자료들을 볼 수 있다
  * 각 커밋 시점에 따라 자료들의 정보는 트리 링크에, 그리고 이전 커밋은 parent를 통해 넘어가며 볼 수 있다
  * 오브젝트 파일은 1. 파일의 내용을 담고있는 blob, 2. 어떤 디렉토리의 파일명과 파일명에 해당되는 blob들에 대한 정보를 담고 있는 tree, 3. commit 정보를 가진다
  * 깃 오픈 책: https://git-scm.com/book/ko/v2
  
# 오류해결
  * fatal: Not a valid object name: 'master'
    - 아직 commit을 한번도 하지 않은 repository이기 때문
    - 최소 1번이상 commit을 진행하면 됨
  
  * There isn't anything to compare. Nothing to compare, branches are entirely different commit histories
    - they don't actually share any of the same history at all
    - ~~~
        git rebase master
        git push -f origin <experiment-branch>
      ~~~
    - ~~~
        git branch new_branch
        git checkout new_branch
        git merge develop --allow-unrelated-histories
      ~~~


