# 🔗 Hướng Dẫn Share Link với Preview Đẹp

## ✨ Đã Thêm Open Graph Meta Tags

Trang web đã được tích hợp Open Graph tags để hiển thị preview đẹp khi share trên:
- 📱 **Messenger** (Facebook)
- 💬 **Zalo**
- 👍 **Facebook**
- 🐦 **Twitter**
- 💼 **LinkedIn**

## 📸 Preview Sẽ Hiển Thị:

```
┌─────────────────────────────────┐
│  [Ảnh thumbnail.png]            │
│                                 │
│  💒 Ngày Cưới Bích Loan & Anh  │
│     Tuấn - 26.10.2025           │
│                                 │
│  Trân trọng kính mời bạn đến   │
│  dự lễ cưới của chúng tôi...   │
│                                 │
│  🔗 your-domain.com             │
└─────────────────────────────────┘
```

## 🚀 Bước 1: Deploy Website

### Option 1: GitHub Pages (Miễn phí, dễ nhất)

1. Tạo repository mới trên GitHub
2. Upload tất cả files lên repo
3. Vào Settings → Pages
4. Source: Deploy from branch `main`
5. Lấy link: `https://username.github.io/repo-name/`

### Option 2: Netlify (Miễn phí)

1. Vào [netlify.com](https://netlify.com)
2. Kéo thả toàn bộ folder vào
3. Lấy link: `https://your-site.netlify.app`

### Option 3: Vercel (Miễn phí)

1. Vào [vercel.com](https://vercel.com)
2. Import project
3. Lấy link: `https://your-site.vercel.app`

## 🔧 Bước 2: Cập Nhật Meta Tags

Sau khi có domain/link hosting, sửa file `index.html`:

### Tìm dòng 20:
```html
<meta property="og:url" content="">
```

### Đổi thành:
```html
<meta property="og:url" content="https://your-actual-domain.com">
```

### Tìm dòng 16:
```html
<meta property="og:image" content="./images/thumbnail.png">
```

### Đổi thành (QUAN TRỌNG):
```html
<meta property="og:image" content="https://your-actual-domain.com/images/thumbnail.png">
```

**Lưu ý:** Phải dùng **absolute URL** (có https://) chứ không phải relative URL (./images)

## 📝 Ví Dụ Cụ Thể:

Nếu bạn deploy lên Netlify với domain: `https://bichloananhtuan.netlify.app`

```html
<!-- Thay đổi 2 dòng này -->
<meta property="og:url" content="https://bichloananhtuan.netlify.app">
<meta property="og:image" content="https://bichloananhtuan.netlify.app/images/thumbnail.png">
<meta name="twitter:image" content="https://bichloananhtuan.netlify.app/images/thumbnail.png">
```

## 🧪 Bước 3: Test Preview

### Facebook / Messenger Debugger:
1. Vào [developers.facebook.com/tools/debug](https://developers.facebook.com/tools/debug/)
2. Paste link website của bạn
3. Click "Debug" → "Scrape Again"
4. Xem preview

### Zalo:
1. Gửi link vào chat Zalo
2. Preview sẽ tự động hiển thị
3. Nếu không hiện, xóa cache Zalo và thử lại

## 📐 Yêu Cầu Ảnh Thumbnail:

- **Kích thước khuyến nghị:** 1200x630 px
- **Tỷ lệ:** 1.91:1 (landscape)
- **Format:** PNG, JPG
- **Dung lượng:** < 1MB
- **Nội dung:** Rõ ràng, dễ đọc khi thu nhỏ

## ⚠️ Lưu Ý Quan Trọng:

### 1. Cache của Facebook/Zalo:
- Sau khi sửa meta tags, cần "scrape again" trên FB Debugger
- Có thể mất vài phút để cache update

### 2. Đường dẫn ảnh:
- ❌ **KHÔNG** dùng: `./images/thumbnail.png`
- ❌ **KHÔNG** dùng: `/images/thumbnail.png`
- ✅ **DÙNG:** `https://domain.com/images/thumbnail.png`

### 3. HTTPS:
- Bắt buộc dùng HTTPS (không phải HTTP)
- GitHub Pages, Netlify, Vercel đều có HTTPS miễn phí

### 4. Test trước khi share:
- Test trên FB Debugger trước
- Đảm bảo ảnh hiển thị đúng
- Sau đó mới share cho mọi người

## 🎨 Tùy Chỉnh Preview:

Bạn có thể đổi nội dung trong các meta tags:

```html
<!-- Tiêu đề -->
<meta property="og:title" content="TÊN BẠN MUỐN">

<!-- Mô tả -->
<meta property="og:description" content="MÔ TẢ BẠN MUỐN">

<!-- Ảnh -->
<meta property="og:image" content="LINK-ẢNH-KHÁC">
```

## ✅ Checklist Deploy:

- [ ] Deploy website lên hosting
- [ ] Có domain/URL công khai
- [ ] Cập nhật `og:url` với domain thật
- [ ] Cập nhật `og:image` với absolute URL
- [ ] Cập nhật `twitter:image` với absolute URL
- [ ] Test trên Facebook Debugger
- [ ] Test bằng cách share vào Messenger
- [ ] Test trên Zalo
- [ ] Share cho bạn bè! 🎉

## 🆘 Troubleshooting:

### Preview không hiển thị?
1. Kiểm tra ảnh có tồn tại tại đúng đường dẫn
2. Kiểm tra URL ảnh phải là HTTPS
3. Scrape lại trên FB Debugger
4. Xóa cache trình duyệt/app

### Ảnh bị mờ?
- Tăng kích thước ảnh lên 1200x630px
- Dùng ảnh chất lượng cao hơn

### Zalo không hiện preview?
- Zalo có thể cache lâu hơn
- Thử gửi link với query param: `?v=2`
- Hoặc đợi 24h để cache tự động clear

---

**Chúc bạn deploy thành công! 🚀**

