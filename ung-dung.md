---
name: Ứng dụng
description: Tích hợp ứng dụng/tiện ích, quyền truy cập, cấu hình và an toàn
tags: ứng dụng, tích hợp, webhook, quyền, API
---

## Tổng quan

Ứng dụng là tích hợp bên thứ ba hoặc tiện ích nội bộ giúp mở rộng chức năng (vận chuyển, thanh toán, marketing, CRM…).

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

