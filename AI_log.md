## Thông tin sinh viên

- Họ và tên: Phạm Hoàng Anh
- Mã sinh viên – Lớp: 2071020007 - CNTT20-02
- Ngày thực hiện: 25/11/2026
- Link repository: https://github.com/PhamHoangAnh08/K20_ClubITDNU_CNTT20-02.git
- URL website: https://phamhoanganh08.github.io/K20_ClubITDNU_CNTT20-02/
- Tình huống: [x] Website của tôi [ ] Repo luyện của giảng viên

## 1. Nhận định của tôi trước khi hỏi AI

- Trang/thao tác gặp lỗi: Trang chủ "index.html" và tệp "css/style.css" khi kiểm tra hiển thị trên màn hình hẹp.
- Mong muốn và hiện tượng thực tế: Mong muốn 3 thẻ giới thiệu các ban chuyên môn tự động xếp dọc 1 cột và toàn bộ giao diện vừa khít chiều ngang màn hình. Thực tế là khối ""banner" xanh bị hụt sang trái, dư ra một khoảng trắng lớn ở lề bên phải màn hình.
- Dữ kiện đã kiểm tra (cấu trúc tệp, Request URL, Status…): Đã kiểm tra thẻ "<div class="table-wrapper">" của bảng lịch hoạt động và thêm "overflow-x: hidden" cho "body" nhưng khoảng trắng bên phải vẫn không biến mất.
- Tôi nghi nguyên nhân là: Có một phần tử bên dưới đang bị tràn chiều ngang ra ngoài khung nhìn (viewport) trên màn hình nhỏ.
- Vì sao tôi nhận định như vậy: Trước đó Em đã đổi tên một số class trong "index.html" (như đổi "cards-grid" thành "cac-ban") nhưng có thể chưa cập nhật đồng bộ hết trong phần `@media` của `style.css`.

## 2. Tôi hỏi AI và nhận được gợi ý

- Nguồn: [x] Công cụ AI: Gemini [ ] Phản hồi mẫu của giảng viên
- Câu hỏi/prompt tôi đã gửi (hoặc tình huống của phản hồi mẫu):

  Gửi ảnh chụp giao diện điện thoại bị dư khoảng trắng bên phải kèm đoạn code cuối tệp `style.css` và hỏi cần sửa lại như thế nào.

- Gợi ý chính của AI:

  Trong khối `@media (max-width: 768px)` ở cuối `style.css`, dòng 88 vẫn đang để tên class cũ là `.cards-grid` trong khi HTML đã đổi thành `.cac-ban`, khiến 3 cột ban chuyên môn không xếp dọc mà nằm ngang đẩy tràn trang. Cần đổi `.cards-grid` thành `.cac-ban` và bổ sung `flex-direction: column;`.

## 3. Quyết định của tôi

- [x] Chấp nhận gợi ý
- [ ] Chỉnh sửa gợi ý rồi áp dụng
- [ ] Bác bỏ gợi ý

- Tôi quyết định làm gì: Sửa tên class `.cards-grid` thành `.cac-ban` trong khối `@media (max-width: 768px)` của tệp `css/style.css`.
- Lý do, dựa trên dữ kiện nào: Đối chiếu trực tiếp giữa dòng 388 của `style.css` và thẻ `<div class="cac-ban">` trong `index.html` thấy đúng là bị lệch tên nên CSS responsive không có tác dụng.

## 4. Thực hiện và kiểm chứng

- Tệp/vị trí đã sửa (không sửa thì ghi rõ): `css/style.css` (dòng 387–390 trong khối `@media (max-width: 768px)`).
- Nội dung thay đổi hoặc cách xử lý khác: Đổi `.cards-grid` thành `.cac-ban` và thêm `flex-direction: column;` để các thẻ tự xếp dọc trên màn hình dưới 768px.
- Commit của bản sửa, nếu có: mã commit bản đã sửa 20ddfdd
- Bản sửa đã deploy: [x] Có [ ] Chưa [ ] Không phát sinh bản sửa

| Nội dung kiểm tra | Trước xử lý Sau xử lý/thử lại |
|
| Request URL và Status của tài nguyên liên quan | `css/style.css` tải bình thường (Status 200) | `css/style.css` tải bình thường (Status 200) |
| Giao diện/chức năng trên URL website | Dư khoảng trắng lớn ở lề phải trên mobile | Các cột xếp dọc gọn gàng, hết khoảng trắng tràn lề phải |

- Cách thử lại và kết quả thực tế: Lưu tệp `css/style.css`, bật chế độ kiểm tra giao diện điện thoại (F12) trên Live Server thấy khoảng trắng bên phải đã biến mất, các thẻ xếp dọc cân đối; sau đó đẩy code lên GitHub Pages và kiểm tra lại trên URL website.
- Căn cứ để đối chiếu (URL tệp, commit, đường dẫn ảnh chụp hoặc dữ kiện quan sát): Quan sát trực tiếp giao diện sau khi sửa trên trình duyệt và URL GitHub Pages.

## 5. Kết luận

- [x] Đã xử lý được [ ] Xử lý được một phần [ ] Chưa xử lý được
- Điều tôi rút ra hoặc việc cần làm tiếp: Khi đổi tên class trong HTML cần rà soát và đổi đồng bộ cả ở phần CSS thông thường lẫn phần `@media` responsive; tiếp theo sẽ kiểm tra thêm giao diện trên điện thoại thật.
