---
name: Sản phẩm
description: Quy ước dữ liệu sản phẩm, biến thể, tồn kho, giá và hiển thị
tags: sản phẩm, biến thể, tồn kho, giá, hình ảnh
---

## Tổng quan

Sản phẩm là đơn vị bán hàng chính trên cửa hàng. Một sản phẩm có thể có **biến thể** (màu/size), **tồn kho**, **giá bán**, **hình ảnh**, và thông tin **SEO/hiển thị**.

## Thuộc tính cơ bản

- Tên sản phẩm
- SKU (cho sản phẩm hoặc từng biến thể)
- Danh mục (có thể nhiều)
- Mô tả ngắn / mô tả chi tiết
- Hình ảnh (ảnh đại diện + gallery)
- Trạng thái: nháp / đang bán / ngừng bán

## Biến thể (Variants)

- Thuộc tính biến thể: màu, size, chất liệu… (tùy cấu hình)
- Mỗi biến thể có thể có:
  - SKU riêng
  - Giá riêng (hoặc kế thừa)
  - Tồn kho riêng
  - Ảnh riêng

## Giá & Tồn kho

- Giá niêm yết (giá gốc) và giá bán (nếu có)
- Quy tắc làm tròn/định dạng tiền tệ theo cấu hình cửa hàng
- Tồn kho:
  - Theo biến thể (khuyến nghị)
  - Cảnh báo sắp hết hàng (ngưỡng cấu hình)
  - Cho phép/không cho phép đặt khi hết hàng (tùy cấu hình)

## Hiển thị & SEO

- Slug/đường dẫn thân thiện
- Meta title / meta description
- Ảnh OG (nếu có)
- Quy tắc: slug duy nhất, không trùng lặp

## Quy trình thường gặp

1. Tạo sản phẩm (thông tin cơ bản)
2. Thêm biến thể (nếu có) + SKU + giá + tồn
3. Gắn danh mục + thêm hình ảnh
4. Thiết lập SEO + trạng thái “đang bán”

