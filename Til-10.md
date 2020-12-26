## 🐳TIL-10🐳 ##


# 구글맵 연동하는 방법
1. 구글맵 플렛폼 검색 후 api 키 생성
2. 키 제한에서 안드로이드 설정 후 패키지 이름 및 SHA1 인증서 입력
  - 안드로이드 안 우측에 gradle누른 후 app > Tasks > android > signingReport 통해 SHA1키 확인 가능
3. manifest에 api키 등록하기
  - application에서 meta-data 생성후 name과 value 설정 여기서 name은 알아볼수 있게 그냥하고 value가 api키 값인거 같음
4. Gradle Scripts - build.gradle에서 implementation해주기
  - implementation 'com.google.android.gms:play-services-maps:17.0.0'
  - implementation 'com.google.android.gms:play-services-location:17.1.0'
5. xml 에서 <fagment>생성후 id와 calss 정의해주기
6. 코드 파일에서 코딩 (2-2 TeamProject에서 참조)
