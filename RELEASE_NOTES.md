# Release Notes

## Nhịp Điệu - v1.0.0 (bản bàn giao)

- Ngày cập nhật: 2026-11-17
- Tác giả: Phạm Văn Việt Hùng (2071020090).
- Mã phiên bản tài liệu: `v1.0.0` (nhãn bàn giao, không thay thế định danh commit).
- Mã bản mã nộp: 9cecfb8553b7e669df65efefc0d3af61552015a4 (`main`).
- Repository: https://github.com/Phamhung16/Bai_Tap_Lon_A3.git 
- Đúng mã nguồn của bản này: 9cecfb8.
- Nguồn xuất bản: GitHub Pages, https://phamhung16.github.io/Bai_Tap_Lon_A3/.
- Thiết kế tham chiếu: page Frame 1 trong [file Figma](https://www.figma.com/design/ObKV1W3bJGmMLmbmB6ctUa).

### Thay đổi chính

- Hai trang tĩnh viết bằng HTML5 và CSS3, không có JavaScript: `index.html` (Tin tức) và `bang-xep-hang.html` (Bảng xếp hạng), dùng chung `css/style.css`.
- Trang Tin tức: bài nổi bật, lưới 6 thẻ tin, bộ lọc Tất cả / Hôm nay / 7 ngày qua / 30 ngày qua, danh sách Chọn ngày, dòng đếm số tin bằng CSS counter và nút Xem thêm tin.
- Trang Bảng xếp hạng: thẻ quán quân tuần, bảng top 10 Billboard Vietnam Hot 100 và ba tiêu chí sắp xếp (Thứ hạng tuần, Thứ hạng cao nhất, Số tuần trên BXH) bằng thuộc tính `order`.
- Bố cục responsive theo hai mốc 1024 px và 640 px; bảng xếp hạng cuộn ngang trong khung trên điện thoại.
- Dữ liệu tin tức và bảng xếp hạng lấy một lần, viết thẳng trong HTML; website không gọi API.

### Lỗi đã sửa và trạng thái hiện tại

- Ảnh banner bài nổi bật không hiển thị. Nguyên nhân: `index.html` tham chiếu `assets/img/langbiang.jpg` nhưng thư mục `assets/img/` trong gói mã chưa có file ảnh; ảnh export mặc định từ Figma lại mang tên layer cũ và định dạng PNG nên không khớp đường dẫn.
- Đã đổi tên 7 layer ảnh trong Figma cho khớp tên file trong HTML và đặt sẵn chế độ export JPG. Đã thêm `color: transparent` cho `.thumb img` trong `css/style.css` để khi thiếu ảnh chỉ hiện nền xám, không hiện biểu tượng ảnh lỗi và chữ alt.
- Gói mã hiện vẫn chưa kèm ảnh. Lỗi chỉ được xem là đã sửa khi 7 file JPG nằm trong `assets/img/` và Network trả `200` cho từng file; trước đó không ghi nhận là đã sửa hoàn toàn.

### Hạn chế còn lại

- Bộ lọc và sắp xếp cần trình duyệt hỗ trợ `:has()` (Chrome 105+, Edge 105+, Safari 15.4+, Firefox 121+); trình duyệt cũ hơn hiện đủ nội dung nhưng không lọc, không sắp xếp được.
- Mốc Hôm nay, 7 ngày qua, 30 ngày qua tính cố định theo ngày lấy dữ liệu 15/11/2026, không theo ngày hiện tại.
- Chọn ngày chỉ liệt kê những ngày có tin, không phải lịch chọn ngày tự do.
- Bảng xếp hạng là tuần 08/11/2025 (bản trang Billboard trả về khi lấy dữ liệu), chỉ có một tuần; tên bài hát và nghệ sĩ giữ cách viết không dấu của Billboard.
- Hai tin của VietnamPlus dẫn tới trang chuyên mục Âm nhạc, chưa phải link bài cụ thể.
- Liên kết Giới thiệu và Liên hệ ở footer là nội dung chờ (`#`).
- Tài liệu thiết kế chi tiết và tài liệu wireframe còn ghi dữ liệu lưu vào browser storage và file JSON; mã nguồn thực tế viết dữ liệu trong HTML và không lưu gì vào trình duyệt. Cần sửa tài liệu cho khớp trước khi nộp.

### Tiếp tục kiểm tra và bàn giao

1. Export 7 ảnh từ page Frame 1 trong Figma (chọn các layer `langbiang`, `bocelli`, `concert`, `jazz`, `ban-quyen`, `guitar-berlin`, `nhan-duyen`, bấm Export) và chép vào `assets/img/`.

2. Chạy local từ thư mục repository:

	```powershell
	py -m http.server 8000
	```

	Mở `http://localhost:8000/` và `http://localhost:8000/bang-xep-hang.html`.

3. Thử từng nút lọc ngày, danh sách Chọn ngày, Xem thêm tin và ba tiêu chí sắp xếp theo các bước trong `README.md`. Bật chế độ thiết bị 390 px để kiểm tra bố cục điện thoại.

4. Trong DevTools > Network, tải lại trang và lọc `CSS`/`Img`/`Font`. Kiểm tra status và URL của `css/style.css`, font Be Vietnam Pro và 7 ảnh; mọi tài nguyên phải trả `200` (hoặc `304` từ cache sau lần tải đầu) trước khi coi giao diện là đạt.

5. Commit toàn bộ mã cùng `README.md`, `RELEASE_NOTES.md` và `AI_LOG.md`, điền mã commit, URL repository và URL GitHub Pages vào hai file này, rồi xác nhận GitHub Pages đã cập nhật đúng bản đó.
