# Nhịp Điệu

Website demo tĩnh giới thiệu tin tức và bảng xếp hạng âm nhạc. Chỉ dùng HTML5 và CSS3, không có JavaScript.

## Cấu trúc

```
index.html           Tin tức
bang-xep-hang.html   Bảng xếp hạng
css/style.css
assets/img/          Ảnh tin tức
```

## Ảnh

Thư mục `assets/img/` cần 7 ảnh sau (ảnh tạo bằng Figma AI, nằm trong page Frame 1 của file Figma):

| File | Bài |
| --- | --- |
| langbiang.jpg | LangBiang 2026 (bài nổi bật) |
| bocelli.jpg | Andrea Bocelli |
| concert.jpg | Concert Tự hào là người Việt Nam |
| jazz.jpg | Lễ hội Jazz Đà Lạt |
| ban-quyen.jpg | Bản quyền số |
| guitar-berlin.jpg | Liên hoan Guitar Berlin |
| nhan-duyen.jpg | Hòa nhạc Nhân duyên |

Cách lấy: trong Figma chọn layer ảnh, Export dạng JPG, đặt tên như bảng trên.

## Lọc và sắp xếp

- Bộ lọc ngày và nút sắp xếp dùng `input radio` kết hợp selector `:has()`.
- Mốc Hôm nay, 7 ngày qua, 30 ngày qua tính theo ngày lấy dữ liệu 15/11/2026, gắn sẵn bằng class trên từng tin.
- Số tin đang hiển thị dùng CSS counter.
- Sắp xếp bảng xếp hạng dùng thuộc tính `order` với giá trị đặt sẵn trên từng dòng.

Cần trình duyệt hỗ trợ `:has()`: Chrome 105+, Safari 15.4+, Firefox 121+.

## Chạy và triển khai

Mở `index.html` trực tiếp bằng trình duyệt. Để đưa lên GitHub Pages: đẩy thư mục lên một repo, vào Settings, Pages, chọn nhánh `main` và thư mục gốc.
