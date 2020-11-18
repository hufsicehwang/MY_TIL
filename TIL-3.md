#🦄3일차🦄
## git - android 연동 하는 방법!!
git과 android를 연동 하는 방법은 엄청 나게 많다. 대부분의 방법에서는 처음 git 정보를 로그인 하는 것 부터 알려져 있지만
나의 경우 git 정보는 등록 돼 있음으로 다음의 방법만 기억하자.

### android -> git
1. 윈도우 + R 키를 눌러 cmd 입력후 터미널 뛰우기
2. git config --global user.name "이름"
3. git config --global user.email "이메일"     -> 여기서 이름과 이메을은 깃 사용자 정보 인 것 같음
4. 안드로이드에서 build - clean project
5. vcs - import version control - share project on git hub   ->  첫 커밋과 푸시 동시에 git에 새로운 repository가 생김!
6. 변경 사항 commit 후 push

### git -> android
1. git에서 파일을 수정 후 commit changes.
2. android에서 vcs - update project
