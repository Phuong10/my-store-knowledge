---
name: Ứng dụng
description: Tích hợp ứng dụng/tiện ích, quyền truy cập, cấu hình và an toàn
tags: ứng dụng, tích hợp, webhook, quyền, API
---

## Tổng quan

Ứng dụng là tích hợp bên thứ ba hoặc tiện ích nội bộ giúp mở rộng chức năng (vận chuyển, thanh toán, marketing, CRM…).

## Các ứng dụng phổ biến trên Webcake (tham khảo)

Lưu ý: Tên ứng dụng/module có thể khác nhau tuỳ gói hoặc tuỳ ứng dụng bạn cài thêm.

- Khóa học (LMS): bán khóa học, quản lý bài học/chương, phân quyền truy cập sau thanh toán, drip content (mở bài theo lịch) (nếu có)
- Đặt lịch (Booking): dịch vụ, nhân sự/chi nhánh, khung giờ, đặt cọc (nếu có), nhắc lịch, chính sách huỷ/đổi lịch
- OTP/Xác thực: gửi OTP đăng nhập/đăng ký/xác nhận đơn; cấu hình nhà cung cấp, giới hạn tần suất, thời gian hết hạn OTP
- Thành viên/Điểm thưởng: tích điểm, hạng thành viên, quy đổi ưu đãi, giới hạn/chu kỳ điểm
- Đa ngôn ngữ: quản lý nội dung theo từng ngôn ngữ, SEO theo ngôn ngữ (nếu có)
- Chat/Inbox/CRM: đồng bộ hội thoại, gắn thẻ khách, ghi chú, phân công xử lý (nếu có)
- Marketing: popup/form thu lead, email/SMS automation, pixel/analytics, affiliate (nếu có)

## Cấu hình ứng dụng

- Thông tin kết nối (API key/secret, token) (nếu có)
- Môi trường: sandbox / production (nếu có)
- Mapping dữ liệu (ví dụ: trạng thái đơn, phí ship, phương thức thanh toán)

## Quyền & bảo mật

- Nguyên tắc “ít quyền nhất” (chỉ cấp các quyền cần thiết)
- Ẩn thông tin nhạy cảm trong log/hiển thị
- Lưu lịch sử thay đổi cấu hình và ai thao tác

## Webhook / Đồng bộ (nếu có)

- Sự kiện phổ biến: tạo đơn, cập nhật thanh toán, cập nhật vận chuyển, hoàn tiền
- Cơ chế retry khi webhook thất bại
- Xác thực webhook (chữ ký/secret)
