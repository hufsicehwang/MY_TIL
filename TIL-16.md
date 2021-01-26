# 🐬TIL-16🐬

## Fragment안에서 RecyclerView 사용하기
recyclerview가 이미 구현 되있다고 가정함
- fragment안에서 쓰는 이유는 viewpager 때문임!!
  - 즉, 탭을 구현후 하나의 탭 안에 recyclerview를 쓰기 위함.
  
- fragment의 레이아웃 파일에 [recyclerview]를 사용해야함!   
- __fragment의 oncreatview에서 써야함!!!__
```java
public View onCreateView(LayoutInflater inflater, ViewGroup container,
                             Bundle savedInstanceState) {
        // Fragment에서 recyclerview 쓰기!!!!
        list = new ArrayList<>();
        ViewGroup rootVoew = (ViewGroup)inflater.inflate(R.layout.fragment_blank1,container,false);
        recyclerView = (RecyclerView) rootVoew.findViewById(R.id.rv);

        mainAdapter = new MainAdapter(getActivity(),list);
        recyclerView.setLayoutManager(new LinearLayoutManager(getActivity()));
        recyclerView.setAdapter(mainAdapter);


        for(int i = 0;i<10;i++){
            Maindata mainData = new Maindata(R.mipmap.ic_launcher, "홍드로이드", "리사이클러뷰"+i);
            list.add(mainData);
        }


        return rootVoew;
    }
```        
- 일반 코드 파일에서의 onCreat 매소드가 fragment에서는 onCreatView라고 생각하자!!
  - recyclerview에서 lis.add()역시 fragment의 onCreatView에서 사용해야함!
  
## tap 글꼴 변경하기
- style.xml에 추가하기
```java
<style name="tab_text" parent="@android:style/TextAppearance.Widget.TabWidget">
        <item name="android:fontFamily">@font/baebalsmingok</item>
        <item name="android:textSize">20dp</item>
        <item name="android:fontStyle">normal</item>

    </style>
```
- 기존 xml에서 tablayout에 속성 부여하기
```
app:tabTextAppearance="@style/tab_text"
```
