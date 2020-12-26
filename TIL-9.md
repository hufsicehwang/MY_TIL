# 🦄TIL-9🦄


## 카카오 맵 open api 이용하기


### 기초
1. sdk 파일 다운로드
2. 카카오 개발자 사이트에서 앱 등록
3. [플랫폼] – [Android 플랫폼 등록] – [패키지명]
  - 패키지명: manifests.xml (시작 xml 정하는 파일)에서 패키지명 확인 가능
4. 앱키를 등록해야하는데 우선은 네이티브 앱키만 입력하는 거 같음

### 라이브러리 파일 추가
(sdk 파일을 -> 로킬 c에 있는 나의 안드로이드 파일로 옮기는 것)
- 다운 받은 sdk 파일에서 libDaumMapAndroid.jar는 /app/libs에 저장
- libMapEngineApi.so은 /app/source/main/jniLibs
  - 여기서 .so는 3개다 복사하는데 jniLibs 파일은 없음으로 내가 만드는 것임.


