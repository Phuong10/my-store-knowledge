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

### Nhóm Loại trừ
- Khi nhiều KM loại trừ cùng thỏa mãn cho **cùng 1 SKU**, chỉ được áp dụng **1 KM** (theo mức ưu tiên hoặc KM có mức giảm sâu hơn)
- Khi nhiều KM loại trừ thỏa mãn cho **các SKU khác nhau**, vẫn áp dụng được tất cả (mỗi SKU 1 KM)

## Mức ưu tiên (Priority)

- Mỗi chương trình KM (dù là đồng thời hay loại trừ) đều có **mức ưu tiên từ 0 đến 100**
- **Số càng cao = ưu tiên càng cao**, được hệ thống pick trước
- Mức ưu tiên **không phân biệt** nhóm đồng thời hay loại trừ — KM nào có priority cao hơn thì được chọn, bất kể thuộc nhóm nào
- Khi 2 KM có cùng mức ưu tiên, hệ thống chọn KM có mức giảm sâu hơn

**Ví dụ:**
- KM A: đồng thời, ưu tiên = 0
- KM B: loại trừ, ưu tiên = 1
- Nếu site bật "Kích hoạt 1 KM duy nhất" → đơn hàng áp dụng **KM B** (vì ưu tiên 1 > 0, bất kể B là loại trừ)

### Quy tắc xử lý khi đơn hàng thỏa mãn nhiều KM

**Ví dụ minh họa:**
- KM nhóm loại trừ: A (ưu tiên 5), B (ưu tiên 3)
- KM nhóm đồng thời: X (ưu tiên 10), Y (ưu tiên 8)

**Trường hợp 1 — Loại KM áp dụng theo SKU:**
- Đơn hàng thỏa mãn KM A và B cho **cùng 1 SKU** → chỉ áp dụng A (vì ưu tiên 5 > 3)
- Đơn hàng thỏa mãn KM A và B cho **2 SKU khác nhau** → áp dụng cả A và B (mỗi SKU 1 KM)

**Trường hợp 2 — Loại KM tính theo đầu đơn (ví dụ: giảm giá theo giá trị đơn hàng):**
- Đơn hàng thỏa mãn KM A, B, X, Y → áp dụng: **X + Y** (đồng thời, cộng dồn) + **(A hoặc B)** (loại trừ, chọn A vì ưu tiên cao hơn)
- KM loại trừ khi tính theo đầu đơn đã áp dụng cho toàn bộ SKU nên chỉ chọn 1. KM đồng thời vẫn cộng dồn.

### Bảng tóm tắt logic

| Tình huống | KM Đồng thời | KM Loại trừ |
|---|---|---|
| Cùng 1 SKU | Áp dụng tất cả | Chỉ 1 KM (ưu tiên cao nhất) |
| Khác SKU | Áp dụng tất cả | Áp dụng tất cả (mỗi SKU 1 KM) |
| Tính theo đầu đơn | Áp dụng tất cả | Chỉ 1 KM cho cả đơn (ưu tiên cao nhất) |
| Kết hợp Đồng thời + Loại trừ | X + Y (cộng dồn) | + (A hoặc B theo ưu tiên) |

## Setting toàn cục: "Kích hoạt một khuyến mãi duy nhất"

Trong **Cài đặt > Cài đặt chung > Khuyến mãi** có option **"Kích hoạt một khuyến mãi duy nhất"**.

### Khi BẬT
- **Override toàn bộ logic** đồng thời/loại trừ ở trên
- Toàn bộ đơn hàng chỉ được áp dụng **đúng 1 chương trình KM duy nhất**
- Hệ thống chọn KM có **mức ưu tiên cao nhất**, bất kể đồng thời hay loại trừ
- Nếu cùng mức ưu tiên → chọn KM có mức giảm sâu nhất

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