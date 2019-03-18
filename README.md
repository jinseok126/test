# test

### gitgub 사용법

자신의 repository를 만들었다는 가정하의 연동 순서

1> https://git-scm.com 에서 git 다운한다.

2> cmd에서 git --version을 확인한다 (재대로 git이 설치되었는지 확인하는 과정)

3> git config --global user.name id (여기서 id는 github의 사용자 아이디)

4> git config --global user.email email (여기서 mail은 github 아이디 생성시 등록하였던 이메일)

5> 자신의 git 저장소(local repository) 폴더를 만들어준다. ex) C:\gits

6> cd C:\gits 명령어를 사용하여 만들었던 폴더에 진입한다.

7> 자신의 git repository를 복사하고 git clone 복사했던 원격 저장소를 붙여준다. 

==> 7번까지의 과정을 마쳤을 경우 지정한 폴더에 .git이라는 폴더가 생긴다.(만약 보이지 않을경우 파일 보기에서 숨긴파일도 보이게 설정)
    이 과정까지 실습했을 경우 로컬 저장소와 원격 저장소가 동기화가 된다.


### 파일을 수정하거나 생성했을 경우
1) 여기서 파일을 수정하거나 생성하면 git status 공간에 수정된 파일이 저장되고 이 수정한 내용을 넣어주고 싶을 경우 
   git add               ==> 파일명을 입력하여 수정된 파일들을 수정 내역에 추가한다. (모든 수정 파일을 내역에 올릴 경우 git add .)
 
2) git commit -m "메시지" ==> 수정된 내역을 저장소에 반영한다. (반영이 되면 스냅샷이 찍히게 되어 저장)

3) git push              ==>  원격 저장소에도 수정내역 반영






### 특정 지점으로 돌아가고 싶을 때 사용하는 명령어
1> git log 명령어를 사용하여 특정 history의 commit 코드(?)를 복사한다.
2> Q를 눌러 git log를 빠져나온다.
3> git reset --hard 코드를 하면 로컬 저장소에 특정 history로 저장된다. (여기까지 했을 경우 원격저장소에는 반영안됌)

원격저장소와 로컬 저장소 싱크를 맞춰주는 방법
- git push -f ==> 강제로 하는 방법


### commit 메시지를 변경하는 방법
1> git commit --amend를 입력하면 유닉스 에디터가 나타난다.

2> window일 경우 유닉스 에디터는 수정모드와 관리자모드로 나눠지므로 수정모드에 들어가기 위해 a를 눌러준다. (정상적으로 동작했을 경우 --- INSERT --가 나타남)
 
3> 메시지를 바꾼 후 esc를 누른 후 :wq!를 입력한다.


### branch 사용법
1> git branch를 사용하여 branch 목록을 확인한다. (아무것도 만들지 않았을 경우 master만 존재) 

2> git branch develop 명령을 하게 되면 develop branch가 생성된다.

3> git checkout develop를 입력하게되면 develop branch로 접속하게된다.

4> 여기서 파일을 생성하거나 수정하게되면 develop branch에서만 유효한 파일이 된다.

5> master branch와 develop branch를 합치려면 git checkout master를 입력해 branchfmf switch하고 git merge delvelop 명령어를 이용해 합칠 수 있다.


