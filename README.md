# 💕 Trang Web Cưới - Wedding Website

Trang web cưới đẹp với hiệu ứng hiện đại và nhạc nền tự động phát.

## ✨ Tính năng

### 🎵 Nhạc Nền Tự Động
- **Tự động phát khi vào web** (nếu trình duyệt cho phép)
- **Icon đĩa than (vinyl record) đang quay** khi phát nhạc
- **Click để tắt/bật** nhạc bất cứ lúc nào
- **Hiệu ứng quay 3D** mượt mà và chân thực
- **Nhạc lặp lại tự động** suốt thời gian xem web

### 📱 Thiết Kế
- ✅ Tối ưu cho mobile (iPhone, Android)
- ✅ Hiệu ứng xuất hiện khi scroll
- ✅ Hero section với tên cô dâu & chú rể
- ✅ Album ảnh đẹp với nhiều layout
- ✅ **Timeline hành trình yêu** - Đẹp, hiện đại, có animation
- ✅ **Bản đồ tương tác Leaflet.js** - Zoom, kéo thả, chỉ đường
- ✅ Font chữ thanh lịch
- ✅ Tất cả nội dung bằng tiếng Việt

## 🎼 Cách Thêm Nhạc

### Cách 1: File MP3 Local (Đơn giản nhất)
1. Đặt file nhạc của bạn vào cùng thư mục với `index.html`
2. Đổi tên file thành `wedding-song.mp3`
3. Xong! Nhạc sẽ tự động phát

### Cách 2: Link URL Online
Sửa dòng 720 trong file `index.html`:
```html
<source src="https://your-music-url.mp3" type="audio/mpeg">
```

## 🎨 Tùy Chỉnh

### Thay Đổi Tên Cô Dâu & Chú Rể
Sửa dòng 725-732 trong `index.html`:
```html
<div class="bride-name">
    <div class="name">Tên Cô Dâu</div>
    <div class="role">BRIDE</div>
</div>

<div class="groom-name">
    <div class="name">Tên Chú Rể</div>
    <div class="role">GROOM</div>
</div>
```

### Thay Đổi Ngày Cưới
Tìm và thay đổi: `2025.05.20`

### Thay Đổi Ảnh
Thay thế các URL ảnh trong code:
```html
<img src="đường-dẫn-ảnh-của-bạn.jpg" alt="Mô tả">
```

### Thay Đổi Địa Điểm & Bản Đồ
**Xem hướng dẫn chi tiết:** `HUONG-DAN-MAP.md`

**Nhanh:**
1. Tìm tọa độ trên Google Maps
2. Sửa dòng 1260: `const weddingLocation = [LAT, LNG];`
3. Sửa tên & địa chỉ tại dòng 1091-1099

## 🎵 Icon Đĩa Than

Icon đĩa than được tạo hoàn toàn bằng CSS với:
- **Vòng rãnh vinyl** chân thực
- **Nhãn giữa màu đỏ** với gradient
- **Lỗ giữa đen** như đĩa thật
- **Hiệu ứng quay 360°** khi nhạc phát
- **Hiệu ứng pulse** xung quanh khi đang chạy
- **Không cần icon font hay ảnh**

## 🗺️ Bản Đồ Tương Tác

Trang web sử dụng **Leaflet.js** - thư viện bản đồ mã nguồn mở:

### Tính năng:
- 📍 **Interactive map** - Zoom, kéo thả, responsive
- 🎯 **Custom marker** - Icon đỏ đẹp mắt với emoji 💒
- 💬 **Popup tự động** - Hiển thị thông tin địa điểm
- 🎨 **Vòng tròn highlight** - Làm nổi bật khu vực
- 🧭 **Nút chỉ đường** (mobile) - Mở Google Maps
- 🆓 **Miễn phí 100%** - Không cần API key!

### Thay đổi địa điểm:
Xem file `HUONG-DAN-MAP.md` để biết cách:
- Tìm tọa độ GPS
- Cập nhật vị trí
- Tùy chỉnh màu sắc & style
- Đổi tile layer (terrain, dark mode, etc.)

## 🌐 Sử Dụng

### Test Local
1. Mở file `index.html` bằng trình duyệt
2. Nhạc sẽ tự động phát (hoặc sau lần click/scroll đầu tiên)
3. Đĩa than sẽ quay khi nhạc đang phát
4. Click đĩa than để tắt/bật

### Deploy Online & Share Link
**📱 Để share link với preview đẹp trên Messenger/Zalo:**

Xem hướng dẫn chi tiết: **`HUONG-DAN-SHARE-LINK.md`**

**Tóm tắt:**
1. Deploy lên hosting (GitHub Pages/Netlify/Vercel)
2. Cập nhật `og:url` và `og:image` với absolute URL
3. Test trên Facebook Debugger
4. Share!

**Hosting miễn phí:**
- GitHub Pages: `https://username.github.io/repo-name/`
- Netlify: `https://your-site.netlify.app`
- Vercel: `https://your-site.vercel.app`

## 📝 Lưu Ý

### Về Auto-play
Hầu hết trình duyệt hiện đại (Chrome, Safari, Firefox) **chặn autoplay** để bảo vệ người dùng. 

Trang web sẽ:
1. **Thử tự động phát** khi load
2. Nếu bị chặn → **Chờ lần tương tác đầu tiên** (click/scroll/touch)
3. Sau đó nhạc sẽ tự động bắt đầu

Điều này là **bình thường** và theo chuẩn web hiện đại!

### File Nhạc
- Khuyến nghị: **< 5MB** để load nhanh
- Format tốt nhất: **MP3** (hỗ trợ rộng rãi)
- Bitrate: **128-192 kbps** (cân bằng chất lượng/dung lượng)

### Ảnh
- Sử dụng ảnh đã tối ưu (< 500KB/ảnh)
- Khuyến nghị: **WebP** hoặc **JPEG** 
- Resize về kích thước phù hợp mobile

## 🎨 Màu Sắc

- **Màu chính**: #d94141 (đỏ cưới)
- **Background**: Trắng & #fafafa
- **Text**: #333, #666, #999
- **Đĩa than**: Đen #1a1a1a

## 📱 Responsive

- **Mobile**: < 375px
- **Tablet**: 376px - 768px
- **Desktop**: > 768px

Tối ưu đặc biệt cho **iPhone** và **Android**!

## 🙏 Credits

Được tạo với ❤️ cho ngày trọng đại của bạn.

---

**Chúc mừng hạnh phúc! 🎊💐**

