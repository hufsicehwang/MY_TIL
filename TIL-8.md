# 🦄TIL-8🦄


## Intent
1. __Intent intent = new Intent(a.this , b.class);__  _// a -> b로 화면 전환_
2. startActivity(intent);// 위에서 만든 객체로 화면전환 실행

## Intent 하면서 데이터 값 받아오기


ex) 버튼 눌러서 화면전환시 hint값 받아오기 // 이 과정은 회원가입 같은 곳에 쓰일 거 같음!

1. 빈 문자 String str; 선언하기
2. str = et_id.getText().toString();// str = hint한거임
3. intent.putExtra(hint, str); (name, 변수) //getExtra하면서 name쓰임

// intent하면서 putextra로 str을 보내준거임


4. 이동 화면 에서 Intent intent = getIntent();  // 넘어온 값을 intent에서 받아준다.
5. str = intent.getStringExtra("hint"); // str에 넣어준다
6. tv_sub.setText(str);            // tv_sub를 setText해준다

-------
.getText().toString()은 세트인거 같음!


__Intent intent = new Intent(a.this , b.class);__ : 여기서 intent객체를 만드는 것임!!


intent.putExtra(name, str) : intent로 값 보내줌


Intent intent = getIntent() : intent로 받아줌


str = intent.getStringExtra("hint") : 받아준 놈을 변수에 넣어줌

