<!DOCTYPE html>
<html>
<head>
  <meta charset="utf-8">
  <title>GPS 실시간 오버레이</title>
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <link rel="stylesheet" href="https://unpkg.com/leaflet/dist/leaflet.css" />
  <style>
    html, body {
      margin: 0;
      padding: 0;
      background: transparent;
      font-family: sans-serif;
      color: white;
    }
    #map {
      height: 300px;
      width: 100%;
    }
    .info-box {
      background: rgba(0,0,0,0.6);
      padding: 10px;
      font-size: 18px;
      line-height: 1.6;
    }
  </style>
</head>
<body>

  <div id="map"></div>
  <div class="info-box" id="info">GPS 대기 중...</div>

  <script src="https://unpkg.com/leaflet/dist/leaflet.js"></script>
  <script>
    let map = L.map('map').setView([35.1291, 126.8540], 17);
    let marker = L.marker([35.1291, 126.8540]).addTo(map);
    let totalDistance = 0;
    let prevLat = null, prevLng = null;
    const payPerKm = 4000;

    L.tileLayer('https://{s}.tile.openstreetmap.org/{z}/{x}/{y}.png', {
      maxZoom: 19,
    }).addTo(map);

    function deg2rad(deg) {
      return deg * (Math.PI / 180);
    }

    function getDistanceFromLatLon(lat1, lon1, lat2, lon2) {
      const R = 6371; // 지구 반지름 (km)
      const dLat = deg2rad(lat2 - lat1);
      const dLon = deg2rad(lon2 - lon1);
      const a =
        Math.sin(dLat / 2) * Math.sin(dLat / 2) +
        Math.cos(deg2rad(lat1)) * Math.cos(deg2rad(lat2)) *
        Math.sin(dLon / 2) * Math.sin(dLon / 2);
      const c = 2 * Math.atan2(Math.sqrt(a), Math.sqrt(1 - a));
      return R * c; // 거리 (km)
    }

    function updateInfo() {
      const km = totalDistance.toFixed(2);
      const income = Math.floor(totalDistance * payPerKm);
      document.getElementById('info').innerHTML = `
        이동 거리: <b>${km} km</b><br>
        예상 수익: <b>${income.toLocaleString()} 원</b>
      `;
    }

    if (navigator.geolocation) {
      navigator.geolocation.watchPosition(pos => {
        const lat = pos.coords.latitude;
        const lng = pos.coords.longitude;

        marker.setLatLng([lat, lng]);
        map.setView([lat, lng]);

        if (prevLat !== null && prevLng !== null) {
          const d = getDistanceFromLatLon(prevLat, prevLng, lat, lng);
          if (d < 1) totalDistance += d; // 급격한 거리 증가 방지
        }

        prevLat = lat;
        prevLng = lng;

        updateInfo();
      }, err => {
        document.getElementById('info').innerText = 'GPS 오류: ' + err.message;
      }, {
        enableHighAccuracy: true,
        maximumAge: 2000,
        timeout: 10000
      });
    } else {
      document.getElementById('info').innerText = 'GPS를 지원하지 않습니다.';
    }
  </script>
</body>
</html>
