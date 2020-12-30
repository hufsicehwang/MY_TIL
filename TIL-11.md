# 🐳TIL-11🐳


## 카카오 맵 띄우기
- TIL-9를 참조해서 api 적용하는 기반 다지기


### 라이브러리 파일 적용 ###
  - 다운 받은 sdk 파일을 안드로이드 프로젝트 파일에 적용 하는데 jniLibs는 만드는 것이고 적용 경로는 정확히 해야함!
    - 이 확장자 파일을 잘못 적용하면 앱이 뜨긴뜨나 흰 화면인 경우가 많았음
    
    
    
### 네이티브 앱키 및 해시 키 ###
  - 네이티브 앱키
    - 카카오 developer 사이트에서 주어진 것을 manifest의 application 안에 metata 의 value 값으로 적확히 넣어야함
  - __해시 키__
    - 해시 키는 디버그 해시키를 적용해야함! 카카오에는 해시키 구하는 방법이 나와있지 않지만 구글링을 통해 추가 적인 과정이 필요함
    - 해시 키 구하는 매소드 실행 후 logcat에서 확인 가능
    ```java 
    private void getHashKey(){      
        PackageInfo packageInfo = null;
        try {
            packageInfo = getPackageManager().getPackageInfo(getPackageName(), PackageManager.GET_SIGNATURES);
        } catch (PackageManager.NameNotFoundException e) {
            e.printStackTrace();
        }
        if (packageInfo == null)
            Log.e("KeyHash", "KeyHash:null");

        for (Signature signature : packageInfo.signatures) {
            try {
                MessageDigest md = MessageDigest.getInstance("SHA");
                md.update(signature.toByteArray());
                Log.d("KeyHash", Base64.encodeToString(md.digest(), Base64.DEFAULT));
            } catch (NoSuchAlgorithmException e) {
                Log.e("KeyHash", "Unable to get MessageDigest. signature=" + signature, e);
            }
        }
    ```
    
    
    ### 적용 해야 할 것들 ###
    - dependencies
      - implementation fileTree(include: ['*.jar'], dir: 'libs')
      - implementation files('libs/libDaumMapAndroid.jar')
    - manifest
      - android:usesCleartextTraffic="true"
    - Activity
      - __import!!!!!!!__
  
