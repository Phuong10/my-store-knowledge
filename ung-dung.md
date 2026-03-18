---
name: Ứng dụng
description: Tích hợp ứng dụng/tiện ích, quyền truy cập, cấu hình và an toàn
tags: ứng dụng, tích hợp, webhook, quyền, API
---

## Tổng quan

Ứng dụng là tích hợp bên thứ ba hoặc tiện ích nội bộ giúp mở rộng chức năng cho website trên Webcake.

## Các ứng dụng trên Webcake

### Thiết kế sản phẩm (Product Design)

- Cho phép khách hàng tự thiết kế/cá nhân hóa sản phẩm trước khi đặt hàng (in ấn, khắc tên, chọn màu/chất liệu…)
- Tích hợp trực tiếp trên trang sản phẩm, khách hàng tương tác trực quan
- Lưu bản thiết kế của khách kèm theo đơn hàng để xưởng sản xuất
- Hỗ trợ upload hình ảnh, thêm text, chọn template có sẵn (tuỳ cấu hình)
- Quản lý các template thiết kế, vùng thiết kế (design zone) trên sản phẩm

### reCaptcha

- Tích hợp Google reCAPTCHA để bảo vệ form trên website khỏi spam/bot
- Hỗ trợ reCAPTCHA v2 (checkbox) hoặc v3 (invisible) tuỳ cấu hình
- Áp dụng cho các form: đăng ký, đăng nhập, liên hệ, bình luận, đặt hàng
- Cấu hình: nhập Site Key và Secret Key từ Google reCAPTCHA
- Có thể bật/tắt reCAPTCHA cho từng form cụ thể

## Cấu hình ứng dụng

- Thông tin kết nối (API key/secret, token) (nếu có)
- Môi trường: sandbox / production (nếu có)
- Mapping dữ liệu (ví dụ: trạng thái đơn, phí ship, phương thức thanh toán)

## Quyền & bảo mật

- Nguyên tắc "ít quyền nhất" (chỉ cấp các quyền cần thiết)
- Ẩn thông tin nhạy cảm trong log/hiển thị
- Lưu lịch sử thay đổi cấu hình và ai thao tác

## Webhook / Đồng bộ (nếu có)

- Sự kiện phổ biến: tạo đơn, cập nhật thanh toán, cập nhật vận chuyển, hoàn tiền
- Cơ chế retry khi webhook thất bại
- Xác thực webhook (chữ ký/secret)