## 1. 애플리케이션 추가하기

![image.png](/img/kakao_map_api/1.png)

## 2. 키 복사하기

### JavaScript 키 복사

![image.png](/img/kakao_map_api/2.png)

## 3. Web 플랫폼 등록

![image.png](/img/kakao_map_api/3.png)

![image.png](/img/kakao_map_api/4png)

### Visual Studio Code의 Live Server를 사용할 것이므로 `http://127.0.0.1:5500` 입력 후 저장

## 4. [https://apis.map.kakao.com](https://apis.map.kakao.com/)에 접속 후 중앙의 Web 클릭

![image.png](/img/kakao_map_api/5.png)

## 5. 접속 후 좌측 메뉴에서 Sample 클릭

![image.png](/img/kakao_map_api/6.png)

## 6. 지도 생성하기

### 코드 복사 붙여넣기 후 appkey에 발급받은 키 입력

```html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8" />
    <title>지도 생성하기</title>
  </head>
  <body>
    <!-- 지도를 표시할 div 입니다 -->
    <div id="map" style="width:100%;height:350px;"></div>

    <script
      type="text/javascript"
      src="//dapi.kakao.com/v2/maps/sdk.js?appkey=발급받은 APP KEY를 사용하세요"
    ></script>
    <script>
      var mapContainer = document.getElementById("map"), // 지도를 표시할 div
        mapOption = {
          center: new kakao.maps.LatLng(33.450701, 126.570667), // 지도의 중심좌표
          level: 3, // 지도의 확대 레벨
        };

      // 지도를 표시할 div와  지도 옵션으로  지도를 생성합니다
      var map = new kakao.maps.Map(mapContainer, mapOption);
    </script>
  </body>
</html>
```

## 7. 최종 코드

```html
<!DOCTYPE html>
<html lang="ko">
  <head>
    <meta charset="UTF-8" />
    <title>지도 생성하기</title>
    <style>
      * {
        text-align: center;
      }

      #map {
        margin: auto;
        width: 500px;
        height: 300px;
      }
    </style>
  </head>
  <body>
    <h2>카카오맵 API</h2>
    <p>서울 종로구 사직로 161 경복궁</p>
    <!-- 지도를 표시할 div -->
    <div id="map"></div>
    <script src="//dapi.kakao.com/v2/maps/sdk.js?appkey=e13dae2a90ecbbe1a6a885baab0c28fd"></script>
    <script>
      var mapContainer = document.getElementById("map"), // 지도를 표시할 div
        mapOption = {
          center: new kakao.maps.LatLng(37.5798, 126.9771), // 지도의 중심좌표 (경복궁)
          level: 3, // 지도의 확대 레벨
        };
      // 지도를 표시할 div와 지도 옵션으로 지도 생성
      var map = new kakao.maps.Map(mapContainer, mapOption);
    </script>
  </body>
</html>
```

![image.png](/img/kakao_map_api/7.png)
