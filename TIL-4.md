# 🦄TIL-4🦄

## branch 생성, 이동, push
터미널과 안드로이드 안에서 하는 방법이 있다.

- 터미널
  - git branch　　　　　　#브랜치의 목록을 보여줌 __'*'는 현재 branch를 말함__
  - git branch sub1　　　#sub1 이라는 branch 생성
  - git checkout sub1　　#sub1으로 브랜치 이동
  - sub1에서 파일을 만듬
  - git commit -m "~"　　　#로컬에 저장함
  - git push origin sub1　#__브랜치 이름으로 push하면서 원격 저장소에 sub1의 브랜치로 push됨__ 
 
 - 안드로이드
   - vcs -> git -> branches　#브랜치 목록과 이동, 생성, 삭제를 다 할 수 있음　#단축기!! __ctrl+shift+`__　#__브랜치 앞에 태그 모양이 현재 브랜치임!!__
   
## branch pull
- git checkout su1  -> 원격저장소에 브랜치 push 했으면 원격 저장소의 브랜치에 접근하면서 자동으로 pull함!!

## branch merge
- git checkout master
- git merge sub1
- git push origin master -> sub1에서 작업한 것을 master로 병합

!!여기서 의문!!
master로 이동하면 vsc -> git이 없다 ctrl+shift+`도 안먹힌다 왜그럴까? 혼자 스스로 새로운 브랜치를 만들고 병합해서 그런가??
하여튼 master에서 터미널로 push하면 된다!

### 병합이 끝나면 왠만하면 branch는 삭제해 주자.

참고 사이트
https://tagilog.tistory.com/377
