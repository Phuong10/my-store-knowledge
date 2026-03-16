---
name: Đơn hàng
description: Trạng thái đơn hàng, thanh toán, vận chuyển, hoàn/đổi và đối soát
tags: đơn hàng, trạng thái, thanh toán, vận chuyển, hoàn tiền
---

## Tổng quan

Đơn hàng ghi nhận giao dịch mua: thông tin khách, sản phẩm, thanh toán, vận chuyển và lịch sử xử lý.

## Thành phần dữ liệu

- Mã đơn hàng
- Thông tin khách hàng (tên, SĐT, email)
- Địa chỉ giao hàng
- Danh sách sản phẩm (item, biến thể, số lượng, giá)
- Phí: vận chuyển, giảm giá, thuế (nếu có)
- Tổng tiền cần thanh toán
- Ghi chú khách/nhân viên

## Trạng thái (gợi ý)

- Trạng thái đơn: nháp / chờ xác nhận / đang xử lý / đang giao / hoàn tất / hủy
- Trạng thái thanh toán: chưa thanh toán / đã thanh toán / hoàn tiền (một phần/toàn phần)
- Trạng thái vận chuyển: chưa gửi / đã gửi / giao thành công / hoàn về

## Quy tắc quan trọng

- Mọi thay đổi trạng thái cần lưu lịch sử (ai, khi nào, lý do)
- Không chỉnh sửa “giá đã chốt” sau khi đơn đã thanh toán (trừ nghiệp vụ điều chỉnh có log)
- Hoàn/đổi hàng liên kết với đơn gốc và lý do cụ thể

## Quy trình xử lý đơn (tham khảo)

1. Tiếp nhận đơn (tự động hoặc tạo thủ công)
2. Xác nhận tồn kho + xác nhận đơn
3. Tạo vận đơn / bàn giao đơn vị vận chuyển
4. Cập nhật trạng thái giao hàng
5. Hoàn tất hoặc xử lý hoàn/đổi (nếu phát sinh)

