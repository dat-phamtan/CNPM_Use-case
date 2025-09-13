## Use-case Detail — Student đăng ký tham gia chương trình Tutor và chọn Tutor

### Các thành phần chính

| Mục | Nội dung |
|--|--|
| **Use-case name** | Student đăng ký tham gia chương trình Tutor và chọn Tutor |
| **Primary actor** | Student |
| **Secondary actors** | HCMUT_SSO (xác thực)<br>Tutor Coordinator (quản lý Tutor) |
| **Trigger** | Student đã đăng nhập và nhấn nút "Đăng ký chương trình Tutor" |
| **Pre-conditions** | Student đã có tài khoản trong hệ thống HCMUT_SSO <br> Student chưa từng tham gia chương trình Tutor |
| **Post-conditions** | Student được xác nhận tham gia chương trình <br> Student đã được gán cho một Tutor <br> - Dữ liệu được lưu để Tutor Coordinator theo dõi |

---

### Main flow 

| Step | Mô tả |
|--|--|
| 1 | Student đăng nhập bằng HCMUT_SSO |
| 2 | Student nhấn "Đăng ký chương trình Tutor" để mở form đăng ký |
| 3 | Student kiểm tra thông tin điền sẵn từ HCMUT_SSO và nhập thêm: môn/vấn đề cần trợ giúp, thời gian ưu tiên |
| 4 | Student nhấn "Xác nhận" để gửi yêu cầu |
| 5 | Hệ thống kiểm tra dữ liệu, truy vấn danh sách Tutor phù hợp và hiển thị |
| 6 | Student chọn 1 Tutor và nhấn "Chọn" |
| 7 | Hệ thống xác nhận dữ liệu và lưu đăng ký (kèm ID Tutor được chọn) |
| 8 | Hệ thống hiển thị thông báo "Đăng ký thành công" và gửi mail xác nhận |

---

### Alternative flows

| ID | Điều kiện | Xử lý |
|--|--|--|
| 1a | Student nhập sai tên đăng nhập/mật khẩu hoặc để trống | Hiển thị thông báo lỗi "Tên đăng nhập hoặc mật khẩu không chính xác", quay lại bước 1 |
| 3a | Student không nhập đủ thông tin bắt buộc (môn/vấn đề, thời gian,…) | Hiển thị thông báo lỗi "Vui lòng nhập đầy đủ thông tin", quay lại bước 3 |
| 5a | Không kết nối được Database khi truy vấn Tutor | Hiển thị thông báo lỗi "Hệ thống bận, thử lại sau", quay lại bước 4 |
| 7a | Không kết nối được Database khi lưu đăng ký | Hiển thị thông báo lỗi "Hệ thống bận, thử lại sau", quay lại bước 6 |
| 7b | Tutor được chọn vừa hết lịch rảnh | Hiển thị thông báo lỗi "Tutor hiện có lịch chưa phù hợp, vui lòng chọn Tutor khác", quay lại bước 6 |
