# git-test
[깃허브 참조](https://velog.io/@suyeon-hong/%EC%9E%90%EC%A3%BC-%EC%82%AC%EC%9A%A9%ED%95%98%EB%8A%94-git-%EB%AA%85%EB%A0%B9%EC%96%B4-%EC%A0%95%EB%A6%AC)

[마크다운 참조](https://www.heropy.dev/p/B74sNE)

## git init
### 처음에 해야할것이다.
### 깃 초기화, 저장소 생성

## git add file.exe
### 너가 수정 한 파일을 로컬에 올려둔다

## git commit -m '메모'
### 너가 방금 로컬에 올린것들에 메모를 추가해주는것이다.

## git push
### 로컬에 있는것들을 깃허브 프로젝트에 올려주는것이다.

## git status
### 뭔가 이상하다면 이걸 써라 변경사항이나 커밋 내용 현재 위치를 알려주는것이다.

## git pull
### 너가 작업한게 필요없어지거나 버그가 생겨서 다시 해야 할 경우 사용할것이다.

---


# git 초기 설정
> ## git init
> > ### 깃 초기화, 저장소 생성
> ## git remote add origin [깃허브 원격 저장소(레파지토리)주소 ]
> > ### 레파지토리와 로컬 저장소 연결
> ## git config --global user.name [이름]
> > ### 사용자 이름 설정
> ## git config --global user.email [이메일주소]
> > ### 사용자 이메일 설정


# 자주 사용하는 명령어
> ## git clone [깃허브 원격 저장소(레파지토리)주소]
> > ### 레파지토리에서 로컬 폴더로 복제
> ## git pull
> > ### 레파지토리에서 변경된 사항 로컬 폴더로 복사
> ## git add .
> > ### 변경사항 스토리지에 올리기
> ## git status
> > ### 현재 상태 확인 (변경사항, 커밋내용, 현재 위치)
> ## commit -m [변경사항 메모]
> > ### 변경사항에 대한 정보 메모
> ## git push
> > ### 원격 깃허브 저장소로 전송
> ## git merge [브랜치명]
> > ### 메인브랜치로 해당 브랜치 병합
> ## git branch
> > ### 현재 깃 공간(로컬)에서의 브랜치 조회
> ## -- git branch - a
> > ### 로컬, 원격 공간 전체 브랜치 조회
> ## git branch - v
> > ### 브랜치 상세정보, 마지막 커밋메세지 조회
> ## git branch [브랜치명]
> > ### 해당 브랜치 삭제
> ## git checkout [브랜치명]
> > ### 해당 브랜치로 이동
> ## git log
> > ### 커밋 히스토리 조회


# commit 내역 삭제하기
```원격 저장소에 push한 커밋을 삭제하여 이전으로 되돌리고 싶은 경우, 로컬 저장소에서 커밋내역을 삭제한 뒤 커밋 히스토리를 강제로 push하여 사용할 수 있다.```
> ## git log
> > ### 커밋 내역 조회
> ## git reset HEAD~[숫자]
> > ### 최근 커밋내역에서 숫자 이전의 상태로 돌아감
> ## git push -f origin [브랜치명]
> > ### 원격저장소로 강제 push


# pull로 원격파일 강제로 덮어쓰기
```git pull 명령어를 사용했을 때 로컬 파일에서 변경된 사항이 원격 파일과 충돌하여 오류가 나는 경우, 덮어쓰기 해도 무방한 파일이라면 강제로 덮어쓰기해서 사용할 수 있다.```
> ## git fetch --all
> > ### git pull 받을 목록을 레파지토리에서 업데이트
> ## git reset --hard HEAD
> > ### 원격 저장소의 마지막 커밋 상태로 돌아감 (원격저장소에 거밋된 내역 이후의 로컬에서 자장된 모든 커밋내역 삭제)
> ## git pull


# 커밋하지않고 pull 받아오기
```작업도중 새로운 변경사항을 받아와야 할 때, 커밋하지 않은 상태에선 pull 실행이 되지 않는다. stash를 이용해 임시저장한 뒤 새로운 변경사항을 받아오고 pop을 이용해 꺼내올 수 있다.```
> ## git stash
> > ### 스테이지에 있는 내용과 아직 스테이지에 들어가지 않은 변경사항을 모두 저장
> ## --git stash -m '메세지'
> > ### 커밋과 같이 변경사항에 메세지를 붙일 수 있음
> ## git stash list
> > ### 임시저장된 목록, 인덱스값 확인 가능
> ## git status
> > ### 워킹트리가 비어있는지 확인
> ## git pull
> > ### 변경사항 받아오기
> ## git stash pop
> > ### stash로 저장한 변경사항 워킹트리에 반영 (스테이지상태 미반영, pop으로 꺼내오는순간 stash에 저장됐던 내용은 삭제됨)
> ## git stash pop --index
> > ### 스테이지 상태까지 같이 반영
> ## git stash pop --index
> > ### 스테이지 상태까지 같이 반영
> ## git stash pop stash@{인덱스값}
> > ### 해당 인덱스값의 stash로 저장한 변경사항 반영


# 원격 브랜치 가져오기
```프로젝트 협업 중 각자 브랜치에서 merge하기 전 변경사항을 로컬에서 보고싶을 때 사용할 수 있다. 팀원 중 한 명이 다른 사람들이 올린 PR을 보고 땡겨받아서 확인했다는 말을 듣고 검색해보고 알게되었다.```
> ## git remote update
> > ### 원격 저장소 갱신
> ## git branch -a
> > ### 원격 저장소 포함 git에 저장된 브랜치 리스트 조회
> ## git checkout -t origin/브랜치명
> >  ### 원격 저장소의 브랜치와 동일한 이름과 내용을 가진 로컬 브랜치가 생성되고 해당 브랜치로 이동 된다.

---

- branch1에서 branch2를 파생할 경우 branch1의 로그기록을 유지한채로 branch2가 생성된다. main에서 branch를 만드는 습관을 들이자.
- 의미없는 커밋은 지양하자. 항상 branch를 새로 만들어서 작업하는 습관을 들이기, 수정사항이 있을 때에도 새로 branch를 만들어서 push해야 PR을 올릴 수 있다.

---

# Branch 전략
```개발 진행을 하다보면, 코드를 여러개로 복사해야 하는 일이 잦다. 코드를 통쨰로 복사 한 뒤 원래 코드와는 상관없이 독립적으로 개발을 진행 할 수 있게 도와주는걸 branch라고 말한다.```
> ## Git Flow 전략
> ![git-flow](/img/git-flow.png "git-flow")
> > ### Git Flow는 크게 Main 브랜치, 