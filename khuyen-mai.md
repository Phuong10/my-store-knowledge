---
name: Khuyến mãi
description: Các loại khuyến mãi, logic đồng thời/loại trừ, độ ưu tiên, setting toàn cục và xung đột
tags: khuyến mãi, coupon, giảm giá, điều kiện, free-ship, đồng thời, loại trừ, ưu tiên
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
- **ƯU TIÊN CAO HƠN nhóm Loại trừ** — khi hệ thống xử lý, KM đồng thời luôn được áp dụng trước

### Nhóm Loại trừ
- Khi nhiều KM loại trừ cùng thỏa mãn cho **cùng 1 SKU**, chỉ được áp dụng **1 KM** (theo độ ưu tiên hoặc KM có mức giảm sâu hơn)
- Khi nhiều KM loại trừ thỏa mãn cho **các SKU khác nhau**, vẫn áp dụng được tất cả (mỗi SKU 1 KM)
- Có mức ưu tiên **THẤP HƠN** nhóm Đồng thời

### Thứ tự ưu tiên xử lý

1. **KM Đồng thời** — áp dụng trước, cộng dồn tất cả
2. **KM Loại trừ** — áp dụng sau, chỉ chọn 1 nếu xung đột trên cùng SKU hoặc cùng đầu đơn

### Quy tắc xử lý khi đơn hàng thỏa mãn nhiều KM

**Ví dụ minh họa:**
- KM nhóm loại trừ: A, B
- KM nhóm đồng thời: X, Y

**Trường hợp 1 — Loại KM áp dụng theo SKU:**
- Đơn hàng thỏa mãn KM A và B cho **cùng 1 SKU** → chỉ áp dụng A hoặc B (tùy độ ưu tiên và mức giảm sâu hơn)
- Đơn hàng thỏa mãn KM A và B cho **2 SKU khác nhau** → áp dụng cả A và B (mỗi SKU 1 KM)

**Trường hợp 2 — Loại KM tính theo đầu đơn (ví dụ: giảm giá theo giá trị đơn hàng):**
- Đơn hàng thỏa mãn KM A, B, X, Y → áp dụng: **X + Y** (đồng thời, ưu tiên cao) + **(A hoặc B)** (loại trừ, ưu tiên thấp)
- Lý do: KM đồng thời (X, Y) được ưu tiên áp dụng trước và cộng dồn. KM loại trừ (A hoặc B) khi tính theo đầu đơn đã áp dụng cho toàn bộ SKU nên chỉ chọn 1.

### Bảng tóm tắt logic

| Tình huống | KM Đồng thời (ưu tiên cao) | KM Loại trừ (ưu tiên thấp) |
|---|---|---|
| Cùng 1 SKU | Áp dụng tất cả | Chỉ 1 KM (ưu tiên/sâu hơn) |
| Khác SKU | Áp dụng tất cả | Áp dụng tất cả (mỗi SKU 1 KM) |
| Tính theo đầu đơn | Áp dụng tất cả | Chỉ 1 KM cho cả đơn |
| Kết hợp Đồng thời + Loại trừ | X + Y (áp dụng trước) | + (A hoặc B) (áp dụng sau) |

## Setting toàn cục: "Kích hoạt một khuyến mãi duy nhất"

Trong **Cài đặt > Cài đặt chung > Khuyến mãi** có option **"Kích hoạt một khuyến mãi duy nhất"**.

### Khi BẬT
- **Override toàn bộ logic** đồng thời/loại trừ ở trên
- Toàn bộ đơn hàng chỉ được áp dụng **đúng 1 chương trình KM duy nhất**
- Hệ thống sẽ chọn KM theo độ ưu tiên hoặc mức giảm sâu nhất
- Ví dụ: đơn hàng thỏa mãn cả KM1 và KM2 → chỉ áp dụng 1 trong 2

### Khi TẮT
- Logic đồng thời/loại trừ hoạt động bình thường theo bảng tóm tắt ở trên
- Đơn hàng có thể được áp dụng nhiều KM cùng lúc (tùy nhóm)

## Điều kiện áp dụng

- Thời gian hiệu lực (ngày bắt đầu / kết thúc)
- Số lượt sử dụng (tổng / cho mỗi khách)
- Giá trị đơn tối thiểu
- Danh sách sản phẩm/danh mục được áp dụng hoặc bị loại trừ
- Kênh áp dụng (online/offline) (nếu có)

## Theo dõi & báo cáo

- Log sử dụng mã (đơn nào, khách nào, thời điểm)
- Báo cáo hiệu quả theo thời gian/nguồn