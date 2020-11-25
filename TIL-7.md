# 🦄TIL-7🦄


## EditText, Button
- EditText = 밑 줄이 쳐져있는 텍스트 박스
  - layout - EditText - hint(text) - id부여하기
- Button - id부여하기


## 연동하기
1. 클래스 안에 (oncreate메소드 밖) 변수 선언하기
  - EditText (et_id);
  - Button (btn_id);
2. oncreate안에서 코드파일의 id와 layout의 id 연동하기
  - et_id = __findViewByid__(R.id.et_id)
  - btn_id = __findViewByid__(R.id.btn_id)
  
  
## 버튼 눌렀을때 행동 취하기
- override 메소드 이용하기
  btn_id.__setOnClickListener(new View.OnClickListener()__{
  
  @ovveride
  
  public void __onClick(View v)__{
  
  et_id.__setText__("바꿀 텍스트");
  
  }
  
----
1. __findViewByid()__: 동적인 코드파일의 변수와 정적인 레이아웃 id를 연동해줌
2. __setOnClickListener(new View.OnClickListener()__ : 클릭시 행동을 취할 수 있음
3. __onClick(View v)__: 셋온클릭리스너랑 세트인 것 같음 __여기(온클릭)__에서 취할 행동을 적음
4. __setText__: text를 바꿈
