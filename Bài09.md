


# Phần 1: Phân tích kiến trúc đa Profile

## Câu 1: Nguyên nhân Session Conflict
- Dùng chung một Chrome Profile khiến các tab chia sẻ Cookies và phiên đăng nhập.
- Đăng nhập hoặc đăng xuất tài khoản khác trên cùng hệ thống có thể ghi đè hoặc xóa Session Cookie.
- User Data Directory chứa dữ liệu Profile như Cookies, History, Bookmarks và Extensions.
- Giải pháp: Tách Profile và tài khoản cho từng người dùng.

## Câu 2: Mô hình 3 Profile

| Profile | Mục đích | Màu Theme | Dữ liệu độc lập |
|---|---|---|---|
| Work | Khám bệnh, kê đơn CarePulse | Xanh dương | Cookies, History, Bookmarks, Extensions |
| Personal | PTIT, GitHub, tài khoản cá nhân | Xanh lá | Cookies, History, Bookmarks, Extensions |
| Sandbox/Test | Thử nghiệm website, tiện ích | Cam | Cookies, History, Bookmarks, Extensions |

**Lưu ý:** Mỗi nhân viên cần có tài khoản hệ điều hành riêng để bảo vệ dữ liệu bệnh nhân. Profile Chrome không thay thế cơ chế bảo mật này.

# Phần 2: Bookmark và quy trình an toàn

## Câu 3: Cây thư mục Bookmark

```text
Bookmarks Bar
├── 📁 01_CarePulse_Clinic
│   ├── Hệ thống hồ sơ bệnh án CarePulse
│   ├── Trang kê đơn thuốc
│   └── Lịch hẹn khám bệnh
│
├── 📁 02_Pharma_Portal
│   ├── Dược thư Quốc gia
│   ├── Cổng tra cứu thuốc
│   └── Cổng thông tin Bộ Y tế
│
└── 📁 03_Medical_Tools
    ├── Cổng BHYT
    ├── Google Dịch
    └── Công cụ tính BMI
```

- Mỗi thư mục có thể chứa tối thiểu 10 liên kết.
- Tổng cộng 30 liên kết được gom trong 3 thư mục.

## Câu 4: Favicon-Only
1. Mở 4 trang: CarePulse, Cổng BHYT, Dược thư, Google Dịch.
2. Nhấn `Cmd + D` (Mac) hoặc `Ctrl + D` (Windows).
3. Chọn lưu vào `Bookmarks Bar`.
4. Vào Bookmark Manager: `Ctrl + Shift + O` (Windows) hoặc `Cmd + Option + B` (Mac).
5. Sửa từng Bookmark, xóa tên và giữ nguyên URL.

**Kết quả:** Thanh Bookmark chỉ hiện 4 biểu tượng, tiết kiệm đáng kể diện tích.

## Câu 5: Bảo mật khi cho khách mượn máy
- Chọn **Guest Profile**, không chọn Incognito.
- Guest tách dữ liệu duyệt web khỏi Profile chính.
- Incognito vẫn có thể dùng khi Profile chính đang mở, không phải môi trường tách biệt hoàn toàn.
- Không bật Cloud Sync cá nhân trên máy dùng chung vì có nguy cơ đồng bộ mật khẩu, lịch sử và Bookmark.
- Đăng xuất, đóng Profile Work và khóa phiên làm việc trước khi giao máy.
- Không lưu hồ sơ bệnh án hoặc mật khẩu trên máy dùng chung.
- Khi mất Internet, không mở dữ liệu bệnh nhân đã lưu ngoại tuyến cho khách; chỉ sử dụng hệ thống offline được cấp phép.

# Kết luận
- Multi-Profile: Giảm xung đột phiên đăng nhập.
- Bookmark: Quản lý 30+ liên kết khoa học.
- Guest Profile: Hạn chế khách truy cập dữ liệu cá nhân.
- Cloud Sync: Chỉ bật theo chính sách quản lý của phòng khám.

