# 🐬TIL-13🐬

## MapView Event 감지
MapView.MapViewEventListener, MapView.POIItemEventListener, MapView.OpenAPIKeyAuthenticationResultListener등의 인터페이스를 구현 해 이벤트 발생에 대한 결과를 통보 받을수 있다
- 즉! 한번 클릭, 이중 클릭, 드래그, 지도의 위치 변경 등등 다양한 이벤트의 통보를 다룰 수 있음!
- _하는 방법_
  - 위의 세개의 리스너를 해당 class에서 implement를 시키고 해당 매소드 들을 오버라이딩 해야함!!!!!
  - 해당 오버라이딩 매소드 및 mapview class의 제공 메소드 등으로 지도 구현이 가능해 짐!!!!!!!!
  

## 꼭 필요한 코드 들
```
mapView.setMapViewEventListener(this); // this에 MapView.MapViewEventListener 구현.
mapView.setPOIItemEventListener(this);
onMapViewInitialized(mapView);
```
위의 세개는 기본 적인 조작을 위해 필히 있어야함!

## 클릭 받는 임의의 좌표 생성
```
MapPoint mapPoint2 = MapPoint.mapPointWithGeoCoord(x, y);
```
임의의 좌표(위도, 경도)에 대한 내용을 담을 수 있는 객체의 선언은 위와 같이 해야함!


### oher
안드로이드 배포를 위해서는 패키기 명을 바꿔야함!

패키기명을 바꾸는 방법
- 왼쪽 틀에서 톱니모양(설정) -> compact packages 눌러 채크표시 해제 -> 자바 카테고리의 패키기명 우클릭 -> 이름 재설정 완료후 아래의 _do refact_ -> 이후 manifest, build gradle 및 코드파일의 패키기명도 바꾸기 
