I. Các thành phần chính
- Use Case: Student đăng ký tham gia chương trình Tutor và chọn Tutor
- Actors:
  + Student (primary)
  + HCMUT_SSO (secondary - xác thực)
  + Tutor Coordinator (secondary - quản lý Tutor)
- Trigger: Student đã đăng nhập nhấn nút "Đăng ký chương trình Tutor"
- Pre-conditions:
  + Student đã có tài khoản trong hệ thống HCMUT_SSO
  + Student chưa tham gia chương trình Tutor
- Post-conditions:
  + Student được xác nhận tham gia
  + Student đã được gán cho một Tutor
  + Dữ liệu lưu vào hệ thống đẻ Tutor Coordinator theo dõi
II. Main flow
1 Student đăng nhập bằng HCMUT_SSO
2 Student nhấn "Đăng ký chương trình Tutor" để vào trang mở form đăng ký
3 Student kiểm tra thông tin được điền sẵn dựa vào HCMUT_SSO, điền thông tin còn thiếu như: môn/vấn đề cần trợ giúp, thời gian ưu tiên
4 Student nhấn "Xác nhận" để gửi yêu cầu
5 Hệ thống kiểm tra dữ liệu rồi hiển thị danh sách Tutor gợi ý
6 Student chọn Tutor rồi nhấn "Chọn" để gửi
7 Hệ thống xác nhận dữ liệu và lưu đăng ký
8 Hệ thống hiển thị kết quả trên màn hình "Đăng ký thành công" và gửi mail xác nhận
III. Alternative flow
1a. Nếu Student nhập sai tên đăng nhập, mật khẩu hoặc để trống --> Hiển thị thông báo lỗi "Tên đăng nhập hoặc mật khẩu không chính xác", quay lại bước 1
3a. Nếu Student không nhập đủ thông tin cho các mục (môn/vấn đề, thời gian,...) --> Hiển thị thông báo lỗi "Vui lòng nhập đầy đủ thông tin", quay lại bước 3
5a. Nếu không kết nối được với Database --> Hiển thị thông báo lỗi "Hệ thống bận, thử lại sau", quay lại bước 4
7a. Nếu không kết nối được với Database --> Hiển thị thông báo lỗi "Hệ thống bận, thử lại sau", quay lại bước 6
7b. Nếu Tutor được chọn chưa có lịch phù hợp --> Hiển thị thông báo lỗi "Tutor hiện có lịch chưa phù hợp, vui lòng chọn Tutor khác", quay lại bước 6
