---
name: Thanh toán
description: Phương thức thanh toán, luồng xử lý, hoàn tiền và đối soát
tags: thanh toán, COD, chuyển khoản, thẻ, ví điện tử, hoàn tiền
---

## Tổng quan

Thanh toán mô tả các phương thức thu tiền, trạng thái thanh toán của đơn hàng và quy trình hoàn/đối soát.

## Phương thức thanh toán (tham khảo)

- COD (thu hộ)
- Chuyển khoản ngân hàng
- Thẻ (cổng thanh toán)
- Ví điện tử

## Trạng thái thanh toán (gợi ý)

- Chưa thanh toán
- Đang xử lý
- Đã thanh toán
- Thất bại / bị hủy
- Hoàn tiền (một phần/toàn phần)

## Quy tắc xác nhận

- Chuyển khoản: đối chiếu theo mã đơn + sao kê/giao dịch
- Cổng thanh toán: ưu tiên webhook/callback để cập nhật trạng thái
- COD: xác nhận khi đối soát thu hộ từ đơn vị vận chuyển

## Hoàn tiền

- Gắn với đơn hàng và lý do hoàn (hủy đơn, hoàn hàng, giảm trừ)
- Lưu lịch sử hoàn: số tiền, phương thức, thời gian, trạng thái xử lý

