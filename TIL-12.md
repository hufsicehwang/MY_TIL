# 🐬TIL-12🐬

## 카카오 맵 여러 가지 메소드
- mapView.setMapCenterPointAndZoomLevel(MapPoint.mapPointWithGeoCoord(33.41, 126.52), 9, true);
  - 중심점 + 줌 레벨 설정
- mapView.zoomIn(true); / mapView.zoomOut(true);
  - 임의로 줌인 줌 아웃을 통해 줌 레벨을 설정 하는 것 같음
- __MapPoint mapPoint = MapPoint.mapPointWithGeoCoord(위도 ,경도 );__
  - 마커의 위치를 위와 같이 mappoint 객체로 나타 내야함

## 마커
```java
MapPOIItem marker = new MapPOIItem();
        marker.setItemName("My House");
        marker.setTag(0);
        marker.setMapPoint(mapPoint);
        marker.setMarkerType(MapPOIItem.MarkerType.BluePin); // 기본으로 제공하는 BluePin 마커 모양.
        marker.setSelectedMarkerType(MapPOIItem.MarkerType.RedPin); // 마커를 클릭했을때, 기본으로 제공하는 RedPin 마커 모양.
        mapView.addPOIItem(marker);
```

## polyline
```java
MapPolyline polyline = new MapPolyline();
        polyline.setTag(1000);
        polyline.setLineColor(Color.argb(126, 0, 0, 0)); // Polyline 컬러 지정. argb

        // Polyline 좌표 지정.
        polyline.addPoint(MapPoint.mapPointWithGeoCoord(37.33758955338443, 127.26937613483179));
        polyline.addPoint(MapPoint.mapPointWithGeoCoord(37.33640308871953, 127.25242953036509));
        polyline.addPoint(MapPoint.mapPointWithGeoCoord(37.33785369170434, 127.25249383940952));


        mapView.addPolyline(polyline); // Polyline 지도에 올리기.

        // 지도뷰의 중심좌표와 줌레벨을 Polyline이 모두 나오도록 조정.
        MapPointBounds mapPointBounds = new MapPointBounds(polyline.getMapPoints());
        int padding = 100; // px
        mapView.moveCamera(CameraUpdateFactory.newMapPointBounds(mapPointBounds, padding));
```

# 타이틀 바 제거
manifest에서 


android:theme="@style/Theme.AppCompat.NoActionBar"
