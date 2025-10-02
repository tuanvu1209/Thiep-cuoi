# 🗺️ Hướng Dẫn Bản Đồ Tương Tác

## ✨ Tính năng mới

Trang web đã được tích hợp **Leaflet.js** - thư viện bản đồ tương tác miễn phí, đẹp và chuyên nghiệp!

### 🎯 Có gì mới:

1. **Bản đồ tương tác** - Zoom in/out, kéo thả
2. **Custom marker** - Icon đỏ hình giọt nước với emoji 💒
3. **Popup thông tin** - Hiển thị tên địa điểm, địa chỉ, số điện thoại
4. **Vòng tròn highlight** - Màu đỏ nhạt làm nổi bật khu vực
5. **Nút chỉ đường** - Trên mobile, tự động mở Google Maps
6. **Responsive** - Tự động điều chỉnh cho mọi thiết bị

## 📍 Cách Thay Đổi Tọa Độ

### Bước 1: Tìm tọa độ địa điểm của bạn

**Cách 1: Dùng Google Maps**
1. Mở [Google Maps](https://maps.google.com)
2. Tìm địa điểm tổ chức của bạn
3. Click chuột phải vào địa điểm
4. Click vào tọa độ (ví dụ: `10.7769, 106.7009`)
5. Tọa độ đã được copy!

**Cách 2: Dùng link Google Maps**
1. Mở link Google Maps của địa điểm
2. Trong URL, tìm phần `@10.7769,106.7009`
3. Đó là tọa độ (Latitude, Longitude)

### Bước 2: Cập nhật trong code

Mở file `index.html` và tìm dòng **1260**:

```javascript
const weddingLocation = [10.7769, 106.7009]; // Lat, Lng
```

Thay đổi thành tọa độ của bạn:

```javascript
const weddingLocation = [TỌA-ĐỘ-LAT, TỌA-ĐỘ-LNG]; // Lat, Lng
```

**Ví dụ:**
- Nhà Hát Thành Phố HCM: `[10.7769, 106.7009]`
- Landmark 81: `[10.7944, 106.7218]`
- Nhà Thờ Đức Bà: `[10.7797, 106.6991]`

### Bước 3: Cập nhật thông tin địa điểm

Tìm dòng **1091-1099** để đổi tên và địa chỉ:

```html
<div class="map-text">
    <strong>TÊN ĐỊA ĐIỂM CỦA BẠN</strong><br>
    ĐỊA CHỈ ĐẦY ĐỦ
</div>
```

Và dòng **1294-1296** trong popup:

```javascript
<div class="popup-title">🏛️ TÊN ĐỊA ĐIỂM</div>
<div class="popup-address">
    📍 ĐỊA CHỈ ĐẦY ĐỦ<br>
    QUẬN, THÀNH PHỐ<br>
    <br>
    📞 <a href="tel:SỐ-ĐIỆN-THOẠI">SỐ ĐIỆN THOẠI</a>
</div>
```

## 🎨 Tùy Chỉnh Bản Đồ

### Thay đổi mức zoom (độ phóng to)

Tìm dòng **1265**:
```javascript
zoom: 16,  // Từ 1 (xa nhất) đến 19 (gần nhất)
```

### Thay đổi màu vòng tròn highlight

Tìm dòng **1305-1309**:
```javascript
L.circle(weddingLocation, {
    color: '#d94141',        // Màu viền
    fillColor: '#d94141',    // Màu nền
    fillOpacity: 0.1,        // Độ trong suốt (0-1)
    radius: 100              // Bán kính (mét)
}).addTo(map);
```

### Thay đổi style bản đồ

Có thể dùng các tile layer khác:

**1. Terrain (địa hình):**
```javascript
L.tileLayer('https://{s}.tile.opentopomap.org/{z}/{x}/{y}.png', {
    attribution: 'Map data: OpenTopoMap',
    maxZoom: 17
}).addTo(map);
```

**2. Cartodb Light (sáng, tối giản):**
```javascript
L.tileLayer('https://{s}.basemaps.cartocdn.com/light_all/{z}/{x}/{y}{r}.png', {
    attribution: '&copy; OpenStreetMap, &copy; CartoDB',
    maxZoom: 19
}).addTo(map);
```

**3. Cartodb Dark (tối):**
```javascript
L.tileLayer('https://{s}.basemaps.cartocdn.com/dark_all/{z}/{x}/{y}{r}.png', {
    attribution: '&copy; OpenStreetMap, &copy; CartoDB',
    maxZoom: 19
}).addTo(map);
```

## 📱 Tính Năng Mobile

Trên thiết bị mobile, bản đồ tự động có:
- ✅ Touch zoom (chụm 2 ngngón tay)
- ✅ Kéo thả mượt mà
- ✅ Nút "🧭 Chỉ đường" - Mở Google Maps để dẫn đường

## 🔧 Troubleshooting

### Bản đồ không hiển thị?
1. Kiểm tra kết nối internet
2. Mở Console (F12) để xem lỗi
3. Đảm bảo tọa độ đúng format: `[lat, lng]`

### Marker không đúng vị trí?
- Kiểm tra lại tọa độ
- Đảm bảo thứ tự: **Latitude trước, Longitude sau**

### Muốn ẩn nút chỉ đường?
Xóa hoặc comment đoạn code từ dòng **1313-1327**

## 🌟 Ví Dụ Tọa Độ Một Số Địa Điểm Phổ Biến

### TP. Hồ Chí Minh:
- Dinh Độc Lập: `[10.7768, 106.6955]`
- Bảo Tàng Lịch Sử: `[10.7881, 106.7026]`
- Nhà Thờ Tân Định: `[10.7893, 106.6925]`

### Hà Nội:
- Nhà Hát Lớn: `[21.0240, 105.8581]`
- Văn Miếu: `[21.0277, 105.8355]`
- Hồ Hoàn Kiếm: `[21.0285, 105.8542]`

### Đà Nẵng:
- Cầu Rồng: `[16.0617, 108.2267]`
- Cầu Tình Yêu: `[16.0544, 108.2272]`
- Bảo Tàng Chăm: `[16.0625, 108.2220]`

---

**Chúc bạn thành công! 🎊**

*Bản đồ đẹp sẽ làm trang web cưới của bạn chuyên nghiệp hơn nhiều!*

