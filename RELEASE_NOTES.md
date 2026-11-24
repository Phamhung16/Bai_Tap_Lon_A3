# Release Notes

## Nhịp Điệu - v1.0.0 (bản bàn giao)

- Ngày cập nhật: 2026-11-17
- Tác giả: Phạm Văn Việt Hùng (2071020090).
- Mã phiên bản tài liệu: `v1.0.0` 
- Mã commit bản này : 982df6c89e2ec78bbc0e72c03775a64505fefd94 
- Repository: https://github.com/Phamhung16/Bai_Tap_Lon_A3.git 
- GitHub Pages: https://phamhung16.github.io/Bai_Tap_Lon_A3/ 
- Thiết kế tham chiếu: page Frame 1 trong [file Figma](https://www.figma.com/design/ObKV1W3bJGmMLmbmB6ctUa).

### Thay đổi chính

- Hai trang tĩnh viết bằng HTML5 và CSS3, không có JavaScript: `index.html` (Tin tức) và `bang-xep-hang.html` (Bảng xếp hạng), dùng chung `css/style.css`.
- Trang Tin tức: bài nổi bật, lưới 6 thẻ tin, bộ lọc Tất cả / Hôm nay / 7 ngày qua / 30 ngày qua, danh sách Chọn ngày, dòng đếm số tin bằng CSS counter và nút Xem thêm tin.
- Trang Bảng xếp hạng: thẻ quán quân tuần, bảng top 10 Billboard Vietnam Hot 100 và ba tiêu chí sắp xếp (Thứ hạng tuần, Thứ hạng cao nhất, Số tuần trên BXH) bằng thuộc tính `order`.
- Bố cục responsive theo hai mốc 1024 px và 640 px; bảng xếp hạng cuộn ngang trong khung trên điện thoại.
- Dữ liệu tin tức và bảng xếp hạng lấy một lần, viết thẳng trong HTML; website không gọi API.

### Lỗi đã sửa  cập nhật

- Đã bổ sung đủ 7 ảnh JPG trong `assets/img/`; tên file khớp với các đường dẫn trong `index.html`.
- Đã sửa thuộc tính `width` và `height` theo kích thước ảnh thực tế: `langbiang.jpg` là 1320 × 840; sáu ảnh còn lại là 768 × 435.
- Đã thay hai URL VietnamPlus dạng chuyên mục bằng URL bài viết cụ thể: bài Liên hoan Guitar quốc tế Berlin và bài hòa nhạc “Nhân duyên”.
- Đã bỏ hai liên kết chân trang `href="#"` (Giới thiệu, Liên hệ) vì dự án chưa có trang đích tương ứng.
- Đã thêm `color: transparent` cho `.thumb img` để khớp với mô tả trong tài liệu bàn giao.

### Kiểm thử và giới hạn cần ghi trung thực

- Kiểm tra tĩnh gói ZIP: 7/7 ảnh tồn tại; đường dẫn ảnh khớp; thuộc tính kích thước khớp kích thước file; không còn `href="#"`; hai URL VietnamPlus là URL bài viết riêng.
- Chưa có kết quả chạy trình duyệt/HTTP trong môi trường này, vì vậy không ghi nhận T13/T14/T17/T19 là đã đạt chỉ từ kiểm tra tĩnh.
- T16 (menu Chọn ngày tự đóng sau khi chọn) chưa được sửa. README xác định dự án không dùng JavaScript; với cấu trúc `<details>` và radio hiện tại, HTML/CSS thuần không có cơ chế chuẩn để đóng phần tử `<details>` ngay khi chọn một nhãn radio. Muốn đáp ứng chính xác T16 cần cho phép JavaScript hoặc thay đổi thiết kế điều khiển ngày.

### Hạn chế còn lại

- Bộ lọc và sắp xếp cần trình duyệt hỗ trợ `:has()` (Chrome 105+, Edge 105+, Safari 15.4+, Firefox 121+); trình duyệt cũ hơn hiện đủ nội dung nhưng không lọc, không sắp xếp được.
- Mốc Hôm nay, 7 ngày qua, 30 ngày qua tính cố định theo ngày lấy dữ liệu 15/11/2026, không theo ngày hiện tại.
- Chọn ngày chỉ liệt kê những ngày có tin, không phải lịch chọn ngày tự do.
- Bảng xếp hạng là tuần 08/11/2025 (bản trang Billboard trả về khi lấy dữ liệu), chỉ có một tuần; tên bài hát và nghệ sĩ giữ cách viết không dấu của Billboard.
- Hai tin VietnamPlus đã được cập nhật thành liên kết bài viết cụ thể trong gói ZIP cập nhật.
- Liên kết Giới thiệu và Liên hệ đã được bỏ khỏi footer vì chưa có trang đích.
- Tài liệu thiết kế chi tiết và tài liệu wireframe còn ghi dữ liệu lưu vào browser storage và file JSON; mã nguồn thực tế viết dữ liệu trong HTML và không lưu gì vào trình duyệt. Cần sửa tài liệu cho khớp trước khi nộp.

### Tiếp tục kiểm tra và bàn giao

1. Gói ZIP cập nhật đã có đủ 7 ảnh JPG trong `assets/img/`; không cần export lại nếu dùng đúng gói này.

2. Chạy local từ thư mục repository:

	```powershell
	py -m http.server 8000
	```

	Mở `http://localhost:8000/` và `http://localhost:8000/bang-xep-hang.html`.

3. Thử từng nút lọc ngày, danh sách Chọn ngày, Xem thêm tin và ba tiêu chí sắp xếp theo các bước trong `README.md`. Bật chế độ thiết bị 390 px để kiểm tra bố cục điện thoại.

4. Trong DevTools > Network, tải lại trang và lọc `CSS`/`Img`/`Font`. Kiểm tra status và URL của `css/style.css`, font Be Vietnam Pro và 7 ảnh; mọi tài nguyên phải trả `200` (hoặc `304` từ cache sau lần tải đầu) trước khi coi giao diện là đạt.

5. Commit toàn bộ mã cùng `README.md`, `RELEASE_NOTES.md` và `AI_LOG.md`, điền mã commit, URL repository và URL GitHub Pages vào hai file này, rồi xác nhận GitHub Pages đã cập nhật đúng bản đó.
