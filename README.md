# 협업 프로젝트
Github `README.md` 같이 만들기

- 이한얼

- 얼그레이

- 이빨

- 빨래터

- 터널

- 널뛰기

## 2. 컨플릭트 내보기
컨플릭트를 내보겠습니다.


### 컨플릭트란?
위키피디아 내용을 요약해서 정리하세용
## 3. 컨플릭트란?

참고링크: https://suwoni-codelab.com/git/2018/04/06/Git-Merge-conflict/
'''
1. git merge
브랜치를 병합하는 명령어
현재상태의 브랜치에서 다른 브랜치명 의 브랜치를 가져와 합친다.
$ git merge 브랜치명

Updating eb44dc3..dbdb555
Fast-forward
 test.txt | 1 +
 1 file changed, 1 insertion(+)
 create mode 100644 test.txt
충돌이 일어나지 않으면 아래와 같이 병합된 로그가 출력된다.
맨위에 merger 기록을 보면 master, new_branch 가 같은 위치를 가리키고 있다.
7-1

2. Conflict 해결 예제
임의로 충돌(Conflict)를 발생시켜 본다.
master 브랜치 상태에서 프로젝트 내 menu.txt 파일을 아래와 같이 맨 아랫줄에 내용을 추가한다.
Spaghetti alla Carbonara
Apple Pie
Cheesecake
Chicken Tikka Masala
Tomato
충돌유발- master
커밋을 수행한다.
$ git add . 
$ git commit
브랜치를 전환하고 같은파일 같은 라인에 다른 내용을 입력한다.
$ git checkout new_branch
$ vi menu.txt 
Spaghetti alla Carbonara
Apple Pie
Cheesecake
Chicken Tikka Masala
Tomato
충돌유발- new_branch
다시 추가 후 커밋 -a 옵션이 수정된 파일 추가를 함께 실행한다.
$ git commit -a
현재 new_branch 브랜치 상태에서 머지를 수행
$ git merge master
Auto-merging menu.txt
CONFLICT (content): Merge conflict in menu.txt
Automatic merge failed; fix conflicts and then commit the result.


git status를 수행해보면 아래와 같이 충돌된 파일을 확인할 수 있다.
$ git status
On branch new_branch
You have unmerged paths.
  (fix conflicts and run "git commit")

Unmerged paths:
  (use "git add <file>..." to mark resolution)

	both modified:   menu.txt

no changes added to commit (use "git add" and/or "git commit -a")
menu.txt파일을 확인 해보자
HEAD 는 현재 브랜치를 가리키며 master는 병합한 브랜치다.
개발자가 직접 충돌된 부분을 확인하고 수정 저장한다.
Spaghetti alla Carbonara
Apple Pie
Cheesecake
Chicken Tikka Masala
Tomato
충돌유발- new_branch
충돌된 부분을 수정 후 반영하기 위해서는 add와 commit을 수행해야한다.
$ git add . 
$ git commit
이때 커밋 메세지에는 기본적으로 아래와 같이 merge 메세지가 기본값으로 입력되어 있다.
원하는대로 수정 저장해주자.
Merge branch 'master' into new_branch

저장하고 빠져나오면 아래 메세지를 확인할 수 있다.
$ git commit 
[new_branch bb1bb99] Merge branch 'master' into new_branch
로그를 확인 해보자
$ git log --graph --decorate --oneline
7-2

'''

아래 내용은 Pluralsight의 Master Git, 누구나 이해할 수 있는 Git 입문, 생활코딩 지옥에서 온 Git의 내용을 토대로 정리한 내용입니다.

1. git merge
브랜치를 병합하는 명령어
현재상태의 브랜치에서 다른 브랜치명 의 브랜치를 가져와 합친다.
$ git merge 브랜치명

Updating eb44dc3..dbdb555
Fast-forward
 test.txt | 1 +
 1 file changed, 1 insertion(+)
 create mode 100644 test.txt
충돌이 일어나지 않으면 아래와 같이 병합된 로그가 출력된다.
맨위에 merger 기록을 보면 master, new_branch 가 같은 위치를 가리키고 있다.
7-1

2. Conflict 해결 예제
임의로 충돌(Conflict)를 발생시켜 본다.
master 브랜치 상태에서 프로젝트 내 menu.txt 파일을 아래와 같이 맨 아랫줄에 내용을 추가한다.
Spaghetti alla Carbonara
Apple Pie
Cheesecake
Chicken Tikka Masala
Tomato
충돌유발- master
커밋을 수행한다.
$ git add . 
$ git commit
브랜치를 전환하고 같은파일 같은 라인에 다른 내용을 입력한다.
$ git checkout new_branch
$ vi menu.txt 
Spaghetti alla Carbonara
Apple Pie
Cheesecake
Chicken Tikka Masala
Tomato
충돌유발- new_branch
다시 추가 후 커밋 -a 옵션이 수정된 파일 추가를 함께 실행한다.
$ git commit -a
현재 new_branch 브랜치 상태에서 머지를 수행
$ git merge master
Auto-merging menu.txt
CONFLICT (content): Merge conflict in menu.txt
Automatic merge failed; fix conflicts and then commit the result.


git status를 수행해보면 아래와 같이 충돌된 파일을 확인할 수 있다.
$ git status
On branch new_branch
You have unmerged paths.
  (fix conflicts and run "git commit")

Unmerged paths:
  (use "git add <file>..." to mark resolution)

	both modified:   menu.txt

no changes added to commit (use "git add" and/or "git commit -a")
menu.txt파일을 확인 해보자
HEAD 는 현재 브랜치를 가리키며 master는 병합한 브랜치다.
개발자가 직접 충돌된 부분을 확인하고 수정 저장한다.
Spaghetti alla Carbonara
Apple Pie
Cheesecake
Chicken Tikka Masala
Tomato
충돌유발- new_branch
충돌유발- master
충돌된 부분을 수정 후 반영하기 위해서는 add와 commit을 수행해야한다.
$ git add . 
$ git commit
이때 커밋 메세지에는 기본적으로 아래와 같이 merge 메세지가 기본값으로 입력되어 있다.
원하는대로 수정 저장해주자.
Merge branch 'master' into new_branch

저장하고 빠져나오면 아래 메세지를 확인할 수 있다.
$ git commit 
[new_branch bb1bb99] Merge branch 'master' into new_branch
로그를 확인 해보자
$ git log --graph --decorate --oneline
7-2