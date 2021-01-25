# 🐬TIL-15🐬

## ViewPager
- build gradle에서 동기화 시키기
```
implementation 'com.google.android.material:material:1.2.1'
``` 
- viewpager를 사용할 레이아웃에서 <Tablayout>을 부모로 두고 자식으로 사용할 <TabItem>을 둔다. 그후 <viewPager>를 둔다.
- __ViewpagerAdapter를 만든다.__ 
  - FragmentPagerAdapter를 extends 한다음 두개의 get메소드를 오버라이딩한다.
  - __ctrl + o 를 눌러 getPageTitle를 오버라이딩 한다__
- viewpager를 사용할 코드 파일에서 코딩한다.
 ```java
 ViewPager viewPager = findViewById(R.id.viewpager);
        ViewPagerAdapter viewPagerAdapter = new ViewPagerAdapter(getSupportFragmentManager());
        viewPager.setAdapter(viewPagerAdapter);

        //tab, viewpager연동
        TabLayout tab = findViewById(R.id.tab);
        tab.setupWithViewPager(viewPager);
 ```
 
 ## RecyclerView
 RecyclerView는 액티비티 1개, 레이아웃 파일 1개, 코드 파일 2개가 필요하다.
 - 액티비티의 레이아웃 파일에서 <RecyclerView>를 생성한다.   (MainActivity)
 - 레이아웃 파일에서 나타내고 싶은 데이터의 형태를 만들어 준다. (item_list)
 - 코드 파일에 데이터 클래스를 만들어 준다. (MainData)
    - 1. Text는 String, image는 int형으로 앞선 레이아웃 파일에서 사용한 만큼 선언해준다.
    - 2. alt + insert키를 눌러 생성자, getter and setter 매소드를 만들어준다.
 - 코드 파일에서 어댑터를 만들어 준다. (MainAdapter)
    - 너무 어렵고 복잡 함으로 [android test] reporsitory 참조.
 - 메인 코드 파일에서 연동
 ```java
 recyclerView = (RecyclerView) findViewById(R.id.rv);
        linearLayoutManager = new LinearLayoutManager(this);
        recyclerView.setLayoutManager(linearLayoutManager);
        arrayList = new ArrayList<>();
        mainAdapter = new MainAdapter(arrayList);
        recyclerView.setAdapter(mainAdapter);
        for(int i = 0;i<10;i++){
            MainData mainData = new MainData(R.mipmap.ic_launcher, "홍드로이드", "리사이클러뷰"+i);
            arrayList.add(mainData);
        }
```
### Tips
- recyclerview를 가로로 만드로 싶다면 메인 코드파일에서
```java
linearLayoutManager = new LinearLayoutManager(this,LinearLayoutManager.HORIZONTAL,false);
```
- recyclerview의 list.add()는 메인 코드 파일에서 하는 거임!
