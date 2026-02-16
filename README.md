# Standby169 🌌

**Standby169** là một webapp dạng Standby Deck, mang phong cách Liquid Glass của iOS 26. Webapp này mình làm để thiết kế màn hình chờ bao gồm: cung cấp thông tin thời gian, trạng thái hoạt động Discord, cũng như trình phát playlist trên YouTube để chạy queue ngay trong web

🔗 **Live Demo:**
- GitHub Pages: https://astear17.github.io/StandbyD/
- Vercel: https://standbyd.vercel.app

<div align="center">
  <img src="https://github.com/Astear17/StandbyD/blob/main/iOS.png?raw=true" width="400">
  <br>
  <em>iOS - Safari Preview (iPhone 7 Plus, 50% scale)</em>
</div>
<br>
<div align="center">
  <img src="https://github.com/Astear17/StandbyD/blob/main/Android.png?raw=true" width="400">
  <br>
  <em>Android - Chrome Preview (Tự vào fullscreen khi mở nhạc)</em>
</div>
<br>
<div align="center">
  <img src="https://github.com/Astear17/StandbyD/blob/main/image.png?raw=true" width="400">
  <br>
  <em>PC Web - MS Edge Preview (Cho phép quản lý/xem queue, 150% scale)</em>
</div>


## ✨ Tính năng chính

- **Giao diện Liquid Glass:** Thiết kế tối màu với hiệu ứng kính mờ (blur droplet), bo góc mềm mại và các góc kính sáng.
- **🕒 Đồng hồ thời gian thực:** Hiển thị giờ giấc chính xác (GMT+7) và ngày tháng hiện tại với font chữ lớn, dễ đọc.
- **👾 Tích hợp Discord Status (Lanyard API):**
  - Hiển thị Avatar, tên hiển thị, và trạng thái Online/Offline/DND.
  - Hiển thị hoạt động/game đang chơi, trạng thái chi tiết và thời gian đã chơi.
  - Hỗ trợ hiển thị Custom Status (Emoji + Text).
- **🎵 Trình phát nhạc YouTube (IFrame API):**
  - Giao diện điều khiển Custom (Play/Pause, Next, Previous, Loop).
  - Selector chọn Playlist nhanh 
  - Tự động chuyển sang chế độ toàn màn hình khi bắt đầu phát nhạc.

## 🛠️ Công cụ dev app:

- **HTML5 & CSS3:** Sử dụng CSS Variables, Flexbox, Grid và Backdrop-filter.
- **JavaScript (Vanilla):** Xử lý logic thời gian và gọi API.
- **YouTube IFrame API:** Để nhúng và điều khiển trình phát video.
- **Lanyard API:** Để lấy dữ liệu trạng thái từ Discord (WebSocket/REST).
- **Fonts & Icons:** Google Fonts (Inter, Source Code Pro) và FontAwesome.

## ⚙️ Hướng dẫn Tùy chỉnh (Configuration)

Nếu bạn muốn fork dự án này và biến nó thành của riêng bạn, hãy thay đổi các thông số sau trong file `index.html`:

### 1. Thay đổi tài khoản Discord
Tìm dòng code sau trong thẻ `<script>` để thay thế bằng Discord User ID của bạn:

```
const USER_ID = "YOUR_DISCORD_USER_ID";
```
> Thay đổi YOUR_DISCORD_USER_ID này thành [ID Discord](https://support.discord.com/hc/en-us/articles/206346498-Where-can-I-find-my-User-Server-Message-ID#h_01HRSTXPS5H5D7JBY2QKKPVKNA) của bạn

> Lưu ý: Bạn cần tham gia [server Discord của Lanyard](https://discord.gg/lanyard) để API hoạt động
2. Thay đổi Playlist nhạc
Tìm phần #playlist-selector trong HTML và thay đổi link Playlist YouTube trong hàm goFullscreenAndStart:
```
<button class="glass-btn" onclick="goFullscreenAndStart('YOUR_PLAYLIST_LINK')">Tên Playlist 1</button>
<button class="glass-btn" onclick="goFullscreenAndStart('YOUR_PLAYLIST_LINK')">Tên Playlist 2</button>
```
3. Thay đổi Múi giờ (Optional)
Mặc định code đang set cứng hiển thị GMT +07:00. Nếu bạn ở múi giờ khác, hãy sửa text trong phần updateVisuals():

```
document.getElementById('date').innerText = `GMT +07:00 - ${dateStr}`;
```

