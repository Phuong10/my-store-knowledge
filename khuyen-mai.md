---
name: Khuyến mãi
description: Các loại khuyến mãi, logic đồng thời/loại trừ, điều kiện áp dụng và xung đột
tags: khuyến mãi, coupon, giảm giá, điều kiện, free-ship, đồng thời, loại trừ
---

## Tổng quan

Khuyến mãi là tập các quy tắc làm giảm giá trị đơn hàng hoặc một nhóm sản phẩm trong thời gian nhất định.

## 6 loại khuyến mãi

### 1. Khuyến mãi chung
- Giảm giá theo % hoặc số tiền cố định cho sản phẩm/danh mục
- Áp dụng trực tiếp lên giá sản phẩm

### 2. Khuyến mãi theo giá trị đơn hàng
- Giảm giá khi đơn hàng đạt giá trị tối thiểu (ví dụ: đơn từ 500k giảm 50k)
- Loại KM này tính theo đầu đơn (không tính theo từng SKU)

### 3. Khuyến mãi bán kèm (Mua X giảm Y)
- Mua sản phẩm X được giảm giá hoặc tặng sản phẩm Y
- Áp dụng theo SKU cụ thể

### 4. Khuyến mãi khi thanh toán
- Giảm giá khi khách chọn phương thức thanh toán nhất định (ví dụ: thanh toán online giảm 5%)

### 5. Khuyến mãi đồng giá
- Tất cả sản phẩm trong chương trình có cùng 1 mức giá (ví dụ: đồng giá 99k)

### 6. Khuyến mãi giảm giá theo số lượng
- Mua càng nhiều giảm càng sâu (ví dụ: mua 2 giảm 10%, mua 5 giảm 20%)

## Logic đồng thời và loại trừ

Mỗi chương trình khuyến mãi thuộc 1 trong 2 nhóm:

### Nhóm Đồng thời
- Đơn hàng hoặc sản phẩm có thể áp dụng **nhiều khuyến mãi đồng thời** cùng lúc
- Các KM đồng thời không xung đột với nhau, được cộng dồn

### Nhóm Loại trừ
- Khi nhiều KM loại trừ cùng thỏa mãn cho **cùng 1 SKU**, chỉ được áp dụng **1 KM** (theo độ ưu tiên hoặc KM có mức giảm sâu hơn)
- Khi nhiều KM loại trừ thỏa mãn cho **các SKU khác nhau**, vẫn áp dụng được tất cả (mỗi SKU 1 KM)

### Quy tắc xử lý khi đơn hàng thỏa mãn nhiều KM

**Ví dụ minh họa:**
- KM nhóm loại trừ: A, B
- KM nhóm đồng thời: X, Y

**Trường hợp 1 — Loại KM áp dụng theo SKU:**
- Đơn hàng thỏa mãn KM A và B cho **cùng 1 SKU** → chỉ áp dụng A hoặc B (tùy độ ưu tiên và mức giảm sâu hơn)
- Đơn hàng thỏa mãn KM A và B cho **2 SKU khác nhau** → áp dụng cả A và B (mỗi SKU 1 KM)

**Trường hợp 2 — Loại KM tính theo đầu đơn (ví dụ: giảm giá theo giá trị đơn hàng):**
- Đơn hàng thỏa mãn KM A, B, X, Y → áp dụng: **(A hoặc B)** + **X** + **Y**
- Lý do: KM loại trừ (A hoặc B) khi tính theo đầu đơn đã áp dụng cho toàn bộ SKU nên không bắt thêm KM loại trừ khác. Còn KM đồng thời (X, Y) vẫn cộng dồn bình thường.

### Bảng tóm tắt logic

| Tình huống | KM Loại trừ | KM Đồng thời |
|---|---|---|
| Cùng 1 SKU | Chỉ 1 KM (ưu tiên/sâu hơn) | Áp dụng tất cả |
| Khác SKU | Áp dụng tất cả (mỗi SKU 1 KM) | Áp dụng tất cả |
| Tính theo đầu đơn | Chỉ 1 KM cho cả đơn | Áp dụng tất cả |
| Kết hợp Loại trừ + Đồng thời | (A hoặc B) + X + Y | — |

## Điều kiện áp dụng

- Thời gian hiệu lực (ngày bắt đầu / kết thúc)
- Số lượt sử dụng (tổng / cho mỗi khách)
- Giá trị đơn tối thiểu
- Danh sách sản phẩm/danh mục được áp dụng hoặc bị loại trừ
- Kênh áp dụng (online/offline) (nếu có)

## Theo dõi & báo cáo

- Log sử dụng mã (đơn nào, khách nào, thời điểm)
- Báo cáo hiệu quả theo thời gian/nguồn