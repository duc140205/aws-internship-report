---
title : "Sử dụng Admin Dashboard"
date :  "2025-09-09" 
weight : 10
chapter : false
pre : " <b> 5.10. </b> "
---

## Sử dụng Admin Dashboard

Admin Dashboard cung cấp giao diện toàn diện để quản lý tư vấn viên, lịch trình và lịch hẹn.

### Trang Tổng quan

Sau khi đăng nhập, trang chủ dashboard hiển thị:

**Thống kê Hệ thống:**
- Tổng số khách hàng
- Tổng số tư vấn viên
- Tổng số lịch hẹn

**Phân loại Lịch Hẹn:**
- Biểu đồ trực quan hiển thị lịch hẹn theo trạng thái:
  - Đang chờ (Pending)
  - Đã xác nhận (Confirmed)
  - Đã hoàn thành (Completed)
  - Đã hủy (Cancelled)

**Lịch Hẹn Gần đây:**
- Danh sách các lịch hẹn gần nhất
- Xem nhanh khách hàng, tư vấn viên, ngày và trạng thái

### Quản lý Tư vấn viên

Điều hướng đến phần **Consultants** để quản lý đội ngũ tư vấn viên.

#### Xem Tư vấn viên

- Xem tất cả tư vấn viên trong dạng bảng
- Các cột: Tên, Email, Chuyên môn, Trạng thái
- Khả năng tìm kiếm và lọc

#### Thêm Tư vấn viên Mới

1. Nhấp vào nút **Add Consultant**
2. Điền thông tin tư vấn viên:
   - Họ và Tên
   - Email
   - Chuyên môn
   - Tiểu sử
   - URL Ảnh đại diện (tùy chọn)
3. Nhấp **Create**

{{% notice info %}}
Tạo tư vấn viên sẽ tự động tạo tài khoản Cognito tương ứng với thông tin đăng nhập tạm thời được gửi đến email của họ.
{{% /notice %}}

#### Chỉnh sửa Thông tin Tư vấn viên

1. Nhấp vào nút **Edit** bên cạnh tư vấn viên
2. Cập nhật các trường mong muốn
3. Nhấp **Save Changes**

#### Xóa Tư vấn viên

1. Nhấp vào nút **Delete** bên cạnh tư vấn viên
2. Xác nhận xóa
3. Tài khoản Cognito của tư vấn viên cũng sẽ bị xóa

{{% notice warning %}}
Xóa tư vấn viên sẽ không xóa các lịch hẹn lịch sử của họ, nhưng họ sẽ không còn có thể đặt lịch được nữa.
{{% /notice %}}

#### Reset Mật khẩu Tư vấn viên

1. Nhấp vào nút **Reset Password**
2. Mật khẩu tạm thời mới sẽ được tạo
3. Tư vấn viên sẽ nhận mật khẩu qua email

### Quản lý Lịch trình

Điều hướng đến phần **Schedules** để quản lý lịch rảnh của tư vấn viên.

#### Xem Lịch trình

- Xem tất cả các khung giờ của tất cả tư vấn viên
- Lọc theo tư vấn viên, ngày trong tuần, hoặc trạng thái
- Chế độ xem lịch để trực quan hóa tốt hơn

#### Thêm Khung giờ

1. Nhấp **Add Time Slot**
2. Chọn tư vấn viên
3. Chọn ngày trong tuần (Thứ 2 - Chủ nhật)
4. Đặt giờ bắt đầu và giờ kết thúc
5. Nhấp **Create**

#### Chỉnh sửa Khung giờ

1. Nhấp vào nút **Edit** bên cạnh khung giờ
2. Sửa đổi thời gian hoặc trạng thái
3. Nhấp **Save**

#### Xóa Khung giờ

1. Nhấp vào nút **Delete** bên cạnh khung giờ
2. Xác nhận xóa

{{% notice tip %}}
Bạn có thể tạo khung giờ lặp lại bằng cách thêm cùng một giờ cho nhiều ngày trong tuần.
{{% /notice %}}

### Quản lý Lịch Hẹn

Điều hướng đến phần **Appointments** để giám sát lịch hẹn toàn diện.

#### Xem Lịch Hẹn

- Chế độ xem bảng của tất cả lịch hẹn
- Lọc theo:
  - Trạng thái (Pending, Confirmed, Completed, Cancelled)
  - Khoảng thời gian
  - Tư vấn viên
  - Khách hàng

#### Chi tiết Lịch Hẹn

Nhấp vào bất kỳ lịch hẹn nào để xem:
- Thông tin khách hàng
- Thông tin tư vấn viên
- Ngày và giờ
- Trạng thái
- Ghi chú
- Thời gian tạo

#### Tạo Lịch Hẹn Thủ công

1. Nhấp **Create Appointment**
2. Chọn khách hàng (hoặc tạo mới)
3. Chọn tư vấn viên
4. Chọn ngày và giờ
5. Thêm ghi chú (tùy chọn)
6. Nhấp **Book Appointment**

#### Cập nhật Lịch Hẹn

1. Nhấp **Edit** trên lịch hẹn
2. Sửa đổi chi tiết (thời gian, tư vấn viên, ghi chú)
3. Nhấp **Update**

{{% notice info %}}
Thông báo email sẽ được gửi đến cả khách hàng và tư vấn viên khi lịch hẹn được tạo hoặc cập nhật.
{{% /notice %}}

#### Hủy Lịch Hẹn

1. Nhấp **Cancel** trên lịch hẹn
2. Tùy chọn thêm lý do hủy
3. Xác nhận hủy
4. Email thông báo sẽ được gửi

#### Thay đổi Trạng thái Lịch Hẹn

Cập nhật thủ công trạng thái lịch hẹn:
- **Pending** → **Confirmed**: Phê duyệt đặt lịch
- **Confirmed** → **Completed**: Đánh dấu đã hoàn thành
- **Bất kỳ** → **Cancelled**: Hủy lịch hẹn

### Tính năng Tìm kiếm và Lọc

Tất cả các bảng dữ liệu hỗ trợ:
- **Search**: Tìm kiếm văn bản tự do trên các trường liên quan
- **Sort**: Nhấp vào tiêu đề cột để sắp xếp
- **Filter**: Sử dụng bộ lọc dropdown cho trạng thái, ngày, v.v.
- **Pagination**: Điều hướng qua các bộ dữ liệu lớn

### Cài đặt Dashboard

Truy cập cài đặt từ menu góc trên bên phải:
- Cập nhật hồ sơ admin của bạn
- Thay đổi mật khẩu
- Cấu hình mẫu email
- Tùy chọn hệ thống

{{% notice tip %}}
Sử dụng tính năng tìm kiếm của dashboard để nhanh chóng tìm tư vấn viên, khách hàng hoặc lịch hẹn cụ thể thay vì cuộn qua danh sách dài.
{{% /notice %}}

Bây giờ bạn có toàn quyền kiểm soát hệ thống MeetAssist thông qua Admin Dashboard!
