### 🐬TIL-17🐬

# SplashActivity (시작 화면)
- Empty Activity 하나를 만들어 원하는 형태의 레이아웃 파일을 만들어 준다.
- 그 다음 코드 파일에서
```java
 Handler handler = new Handler();
        handler.postDelayed(new Runnable() {
            @Override
            public void run() {
                Intent intent = new Intent(getApplicationContext(),setAdress.class); // 넘어갈 화면.class
                startActivity(intent);
                finish();
            }
        },3000);
    }
```    

# _Animation_
- res -> anim directory를 만들어 준다.
- 애니매이션 효과 파일을 만들어 준다. (wave는 복합적인 것 이다.)
  - alpha (선명도 애니매이션)
  ```java
  <alpha xmlns:android="http://schemas.android.com/apk/res/android"
    android:duration="2500"
    android:fromAlpha="0.0"
    android:interpolator="@android:anim/accelerate_interpolator"
    android:toAlpha="1.0" />
  ```
  - rotate (회전 애니매이션)
  ```java
  <rotate xmlns:android="http://schemas.android.com/apk/res/android"
    android:interpolator="@android:anim/linear_interpolator"
    android:repeatCount="infinite"
    android:duration="4000"
    android:pivotX="50%"
    android:pivotY="50%"
    android:fromDegrees="0"
    android:toDegrees="360">
   </rotate>
   ```
   - scale (크기 애니매이션)
   ```java
   <scale xmlns:android="http://schemas.android.com/apk/res/android"
        android:duration="2500"
        android:fromXScale="0.0"
        android:fromYScale="0.0"
        android:toXScale="1.0"
        android:toYScale="1.0"
        android:pivotX="50%"
        android:pivotY="50%"
        />
    ```
    - transrate (이동 애니매이션)
    ```java
    <translate
    xmlns:android="http://schemas.android.com/apk/res/android"
      android:duration="3000"
      android:fromXDelta="-100%"
      android:toXDelta="0">
    </translate>
    ```
    - wave (복합적인 요소)
    ```java
    <set xmlns:android="http://schemas.android.com/apk/res/android" android:interpolator="@android:anim/accelerate_interpolator">
    <alpha
        android:fromAlpha="0.0"
        android:toAlpha="1.0"
        android:duration="2000" />
    <scale
        android:fromXScale="0.5" android:toXScale="1.2"
        android:fromYScale="0.5" android:toYScale="1.2"
        android:pivotX="50%" android:pivotY="50%"
        android:duration="2000" />
    <scale
        android:fromXScale="1.2" android:toXScale="1.0"
        android:fromYScale="1.2" android:toYScale="1.0"
        android:pivotX="50%" android:pivotY="50%"
        android:startOffset="2000"
        android:duration="2000" />
     </set>
     ```
     
- 적용 방법
  - 코드 파일에서
    ```java
       text = findViewById(R.id.text_Splash);  
       Animation animation = AnimationUtils.loadAnimation(getApplicationContext(),R.anim.scale);  // 애니매이션.xml 선택
       text.startAnimation(animation);
    ```   
