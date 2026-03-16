---
name: Combo
description: Quy ước tạo combo/bundle sản phẩm và tính giá
tags: combo, bundle, định giá, tồn kho
---

## Tổng quan

Combo là gói gồm nhiều sản phẩm/biến thể bán chung theo một mức giá hoặc ưu đãi riêng.

## Dữ liệu combo

- Tên combo
- Danh sách sản phẩm thành phần (SKU/biến thể + số lượng)
- Giá combo (cố định) hoặc quy tắc giảm (theo %/số tiền)
- Trạng thái: nháp / đang bán / ngừng bán
- Thời gian áp dụng (tùy chọn)

## Quy tắc tồn kho

- Khi bán combo, trừ tồn kho theo từng sản phẩm thành phần
- Không cho phép bán nếu bất kỳ thành phần nào không đủ tồn (trừ khi bật “cho phép đặt trước”)

## Hiển thị & SEO

- Trang combo có slug riêng (nếu có)
- Có thể hiển thị combo như một “sản phẩm đặc biệt”

