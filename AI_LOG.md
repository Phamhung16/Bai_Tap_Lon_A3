# AI Log

Nhật ký sử dụng AI cho đồ án Nhịp Điệu (FIT4014, A3). Tác giả: Phạm Văn Việt Hùng (2071020090).

Công cụ đã dùng:

- **Claude (Anthropic)**, qua claude.ai, có kết nối Google Docs, Google Drive và Figma: soạn tài liệu, dựng wireframe và thiết kế trên Figma, thu thập dữ liệu, viết mã HTML/CSS, soạn báo cáo và tài liệu bàn giao.
- **Figma AI** (gọi từ Claude qua kết nối Figma, model `gemini-3.1-flash-lite-image`): tạo 7 ảnh minh họa cho trang Tin tức.

Mọi nội dung AI tạo ra đều cần sinh viên đọc lại, chạy thử và chịu trách nhiệm khi nộp. Cột "Kiểm chứng" bên dưới chỉ ghi những gì đã thực sự được kiểm tra trong phiên làm việc; các ô `[Sinh viên điền]` là phần sinh viên tự xác nhận.

## Figma AI

Ảnh được tạo ngày 15/11/2026 trong file Figma "Wireframe – Website giới thiệu âm nhạc", page Frame 1. Prompt cố ý tránh khuôn mặt nhận diện được, người thật và chữ trong ảnh.

| File trong `assets/img/` | Dùng cho tin | Prompt (rút gọn) |
| --- | --- | --- |
| `langbiang.jpg` | LangBiang 2026 (bài nổi bật) | Lễ hội âm nhạc ngoài trời lúc chạng vạng giữa đồi thông, đèn sân khấu, đám đông nhìn từ phía sau |
| `bocelli.jpg` | Andrea Bocelli | Sân khấu hòa nhạc cổ điển bên hồ có sương, đàn grand piano dưới đèn ấm, không có người |
| `concert.jpg` | Concert Tự hào là người Việt Nam | Sân vận động đông khán giả giơ đèn điện thoại, ánh sáng đỏ vàng, nhìn từ phía sau |
| `jazz.jpg` | Lễ hội Jazz Đà Lạt | Bóng người chơi saxophone trên sân khấu nhỏ buổi tối, đèn bokeh, rừng thông |
| `ban-quyen.jpg` | Bản quyền số | Tĩnh vật: bản nhạc in, laptop hiện sóng âm, ổ khóa đồng nhỏ |
| `guitar-berlin.jpg` | Liên hoan Guitar Berlin | Cận cảnh tay chơi guitar cổ điển dưới đèn sân khấu |
| `nhan-duyen.jpg` | Hòa nhạc Nhân duyên | Đàn tranh trên sân khấu, ánh sáng ấm, rèm đỏ, không có người |

- Lý do dùng: tránh dùng lại ảnh báo chí có bản quyền.
- Giới hạn: ảnh chỉ minh họa, không phải ảnh thật của sự kiện; ảnh Bocelli không mô tả nghệ sĩ thật.
- Ảnh bìa bài hát trên trang Bảng xếp hạng không dùng AI: đó là khối màu gradient vẽ bằng CSS.
- Kiểm chứng: đã xem ảnh trong Figma sau khi tạo. Quyền sử dụng ảnh theo điều khoản Figma AI: [Sinh viên điền].

## Claude: nhật ký thay đổi

| Ngày | Yêu cầu | Kết quả AI tạo ra | Kiểm chứng |
| --- | --- | --- | --- |
| 15/11/2026 | Tạo template tài liệu thiết kế phần mềm | Template gồm thông tin tài liệu, tổng quan, yêu cầu, kiến trúc, thiết kế chi tiết, kiểm thử, triển khai | Sinh viên tự điền nội dung vào bản Google Doc |
| 15/11/2026 | Bỏ phần API, web dùng storage | Sửa kiến trúc thành web + browser storage, bỏ bảng API, đổi bảng dữ liệu sang key storage | Code về sau không dùng storage; tài liệu cần sửa lại cho khớp (xem Hạn chế) |
| 15/11/2026 | Tạo wireframe từ tài liệu thiết kế | Wireframe đen trắng 2 màn hình Tin tức và Bảng xếp hạng | Đã chụp màn hình kiểm tra bố cục |
| 15/11/2026 | Viết tài liệu wireframe vào Google Doc | Tài liệu mô tả từng vùng, hành vi và câu hỏi mở | Đã đọc lại file sau khi ghi |
| 15/11/2026 | Tạo link Figma cho wireframe | File Figma, dựng lại 2 màn hình wireframe, chèn link vào tài liệu | Đã chụp màn hình từng frame trong Figma |
| 15/11/2026 | Hoàn thiện thiết kế Tin tức, tự tìm dữ liệu | Thiết kế hi-fi Tin tức; 7 tin lấy qua tìm kiếm web, tiêu đề và tóm tắt viết lại; 7 ảnh Figma AI; cập nhật tài liệu | Đã chụp màn hình thiết kế; nguồn từng tin ghi trong tài liệu |
| 15/11/2026 | Tạo page Frame 1 gồm Tin tức và Bảng xếp hạng | Page Frame 1; thiết kế hi-fi Bảng xếp hạng với top 10 Billboard Vietnam Hot 100; cập nhật tài liệu | Trang Billboard trả về tuần 08/11/2025, không phải tuần hiện tại; đã ghi rõ trong thiết kế và tài liệu |
| 15/11/2026 | Code bằng HTML5, CSS3 | `index.html`, `bang-xep-hang.html`, `css/style.css`; lọc và sắp xếp không dùng JavaScript | Chạy trình duyệt headless: chụp 1440 px và 390 px, thử lọc 30 ngày qua và sắp xếp theo số tuần |
| 16/11/2026 | Ảnh banner Tin tức không hiển thị | Chẩn đoán thiếu file trong `assets/img/`; đổi tên layer ảnh trong Figma, đặt export JPG; thêm `color: transparent` cho ảnh trong CSS | Chưa kiểm chứng sau khi chép ảnh: [Sinh viên điền kết quả Network] |
| 16/11/2026 | Đưa tài liệu thiết kế, wireframe, Figma vào báo cáo A3 | Điền trang bìa, mục 1, mục 2, bảng yêu cầu R1–R4, bảng quyết định thiết kế, 4 dòng phụ lục; chép toàn bộ hai tài liệu vào mục 2 | Đã đọc lại báo cáo sau khi ghi; lý do chọn đề tài là bản viết chung, cần sinh viên sửa |
| 17/11/2026 | Tạo README, Release Notes, AI Log | `README.md`, `RELEASE_NOTES.md`, `AI_LOG.md` | [Sinh viên điền] |

## Phần sinh viên tự thực hiện

[Sinh viên điền: các quyết định đã tự chọn (chủ đề, phạm vi, yêu cầu dùng HTML5/CSS3), phần đã chỉnh sửa lại sau khi AI tạo, các phép thử đã tự chạy.]

## Hạn chế và điểm cần xác minh

- Tài liệu thiết kế còn ghi kiến trúc web + browser storage, và tài liệu wireframe ghi dữ liệu lưu thành file JSON; mã nguồn thực tế viết dữ liệu trong HTML và không lưu gì vào trình duyệt.
- Mốc ngày trong bộ lọc tính cố định theo ngày lấy dữ liệu 15/11/2026.
- Bảng xếp hạng là tuần 08/11/2025; tên bài và nghệ sĩ không dấu theo Billboard.
- Hai tin VietnamPlus dẫn tới trang chuyên mục, chưa phải bài cụ thể.
- Ngày đăng của tin Andrea Bocelli và tin concert là ngày diễn ra sự kiện, không phải ngày đăng bài.
