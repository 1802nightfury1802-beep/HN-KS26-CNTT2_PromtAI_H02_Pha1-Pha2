  

-  **Mã đề:** 04

-  **Họ tên:** Bùi Hải đăng

-  **Lớp:** CNTT2

-  **Link repository Pha2:** https://github.com/1802nightfury1802-beep/HN-KS26-CNTT2_PromtAI_H02_Pha1-Pha2

-  **Công cụ AI đã dùng (ChatGPT/Claude/Gemini):** Gemini

  

> Pha 2 (20 phút cuối). Mỗi mục: mở cuộc trò chuyện mới, gửi nguyên văn prompt đã viết trong bai_lam_pha1.md, dán câu trả lời và link chia sẻ vào đây. Xong, kéo thả file này vào repository Pha2.

  

## 4.2. Trích xuất tin nhắn đặt vé xe ra JSON

  

**KET QUA AI**

  

```text

[

{

"ma_tuyen": "SGDL",

"ngay_di": "2026-12-22",

"ve_nguoi_lon": 2,

"ve_tre_em": 1,

"loai_cho": "giuong",

"ghi_chu": null

},

{

"ma_tuyen": "SGNT",

"ngay_di": "2027-01-02",

"ve_nguoi_lon": 3,

"ve_tre_em": 0,

"loai_cho": null,

"ghi_chu": "một người đang mang thai 6 tháng"

},

{

"ma_tuyen": "SGCT",

"ngay_di": null,

"ve_nguoi_lon": 4,

"ve_tre_em": 0,

"loai_cho": "ghe",

"ghi_chu": "bà nội đi xe lăn"

}

]

```

  

**Link trò chuyện:** https://share.gemini.google/12EhrWWCfqyB

  

## 4.3. Báo giá bằng Chain-of-Thought

  

**KET QUA AI**

  

```text

Chào quý khách, chuyên viên tư vấn của nhà xe Phương Nam Express xin gửi bảng tính chi tiết báo giá vé tuyến Sài Gòn – Đà Lạt (SGDL) cho đoàn mình theo từng bước như sau:

  

1. **Tiền người lớn:**

* Đơn giá vé tuyến SGDL: 320.000 đồng/vé.

* Số lượng: 8 người lớn.

* Phép tính: $8 \times 320.000 = 2.560.000\text{ đồng}$.

  
  

2. **Tiền trẻ em:**

* Nhóm trẻ từ 5 đến 10 tuổi (gồm 3 bé: 6, 7 và 9 tuổi) được tính 75% giá vé người lớn: $320.000 \times 75\% = 240.000\text{ đồng/vé}$.

* Bé 2 tuổi (dưới 5 tuổi) ngồi cùng người lớn được miễn phí ($0\text{ đồng}$).

* Phép tính: $(3 \times 240.000) + (1 \times 0) = 720.000\text{ đồng}$.

  
  

3. **Tiền vé (trước giảm giá):**

* Tổng tiền vé người lớn và tiền vé trẻ em.

* Phép tính: $2.560.000 + 720.000 = 3.280.000\text{ đồng}$.

  
  

4. **Giảm giá nhóm:**

* Vì đoàn có 8 người lớn (đạt điều kiện từ 6 người lớn trở lên) nên được giảm 5% trên tổng tiền vé.

* Phép tính tiền giảm: $3.280.000 \times 5\% = 164.000\text{ đồng}$.

* Tiền vé sau giảm: $3.280.000 - 164.000 = 3.116.000\text{ đồng}$.

  
  

5. **Phụ thu:**

* Đoàn có 2 kiện hành lý cồng kềnh với mức phụ thu 100.000 đồng/kiện (không áp dụng giảm giá).

* Phép tính: $2 \times 100.000 = 200.000\text{ đồng}$.

  
  

6. **Tổng tiền:**

* Tổng tiền thanh toán bao gồm tiền vé sau giảm cộng với phụ thu.

* Phép tính: $3.116.000 + 200.000 = 3.316.000\text{ đồng}$.

  
  
  

[RESULT: 3.316.000 đồng]

  

**Link trò chuyện:** https://share.gemini.google/e1GeVlM4eQvA

  

### b) Kiểm tra kết quả AI

  

AI trả lời đúng, không cần chinh sửa thêm!

  

## 4.4. Dây chuyền xử lý khiếu nại – kết quả Trạm 1

  

**KET QUA AI**

  

```text

{

"loai_su_co": "sai_loai_xe",

"so_khach": 3,

"so_chang_bi_doi": 2,

"tom_tat": "Khách đặt xe giường nằm cho 3 người nhưng cả hai chặng đi và về đều bị đổi sang ghế ngồi."

}

```

  

**Link trò chuyện:** https://share.gemini.google/6dFM02O994D5

  

## 4.5. Prompt chấm bài theo Rubric

  

**KET QUA AI**

  

```text

| Tiêu chí | Điểm | Minh chứng | Đề xuất sửa |

| --- | --- | --- | --- |

| **Đúng thông tin** (50% - tối đa 5.0đ) | 0.0 / 5.0 | **1. Sai giá vé:**<br>

  

<br>- *Câu bị lỗi:* "Vé đi Nha Trang bên em 350.000đ nha chị, xe xịn lắm luôn."<br>

  

<br>- *Lý do sai:* Giá vé chuẩn tuyến Sài Gòn – Nha Trang là 380.000 đồng/vé người lớn, nhân viên báo sai thành 350.000đ.<br>

  

<br>

  

<br>**2. Sai chính sách đổi vé:**<br>

  

<br>- *Câu bị lỗi:* "Chị đổi trước 12 tiếng thì đổi free nha chị."<br>

  

<br>- *Lý do sai:* Theo quy định, đổi vé từ 6 đến dưới 24 giờ trước giờ xe chạy chịu phí 20% giá vé (chỉ miễn phí khi đổi từ 24 giờ trở lên). | **1. Sửa giá vé:**<br>

  

<br>"Giá vé tuyến Sài Gòn – Nha Trang hiện tại là 380.000 đồng/vé người lớn ạ."<br>

  

<br>

  

<br>**2. Sửa chính sách đổi vé:**<br>

  

<br>"Nếu chị đổi ngày đi trước giờ xe chạy 12 tiếng (nằm trong khung từ 6 đến dưới 24 giờ) thì sẽ áp dụng mức phí đổi là 20% giá vé ạ." |

| **Đầy đủ** (30% - tối đa 3.0đ) | 1.5 / 3.0 | **Thiếu bước điều hướng đặt vé:**<br>

  

<br>- *Câu bị lỗi:* "Cần gì chị nhắn em liền!" (kết thúc câu trả lời mà chưa xin thông tin đặt vé).<br>

  

<br>- *Lý do sai:* Tuy đã trả lời đủ 2 câu hỏi của khách hàng nhưng thiếu lời mời khách cung cấp ngày đi (hoặc ngày trận đấu theo khung tiêu chí) và số lượng vé để tiến hành đặt chỗ. | "Chị dự định đi vào ngày nào và đặt bao nhiêu vé để em kiểm tra chỗ và hỗ trợ giữ vé cho mình luôn ạ?" |

| **Giọng điệu** (20% - tối đa 2.0đ) | 0.5 / 2.0 | **Dùng từ ngữ suồng sã, thiếu chuyên nghiệp:**<br>

  

<br>- *Câu bị lỗi:* "Vé đi Nha Trang bên em 350.000đ nha chị, xe xịn lắm luôn. Chị đổi trước 12 tiếng thì đổi free nha chị. Cần gì chị nhắn em liền!"<br>

  

<br>- *Lý do sai:* Sử dụng nhiều từ ngữ văn nói thiếu chuẩn mực trong giao tiếp khách hàng như "nha", "xịn lắm luôn", "free", "nhắn em liền". | "Dạ chào chị! Giá vé tuyến Sài Gòn – Nha Trang bên em là 380.000 đồng/vé người lớn ạ. Nếu chị đổi vé trước giờ xe chạy 12 tiếng, phí đổi sẽ là 20% giá vé. Chị vui lòng cho em xin thông tin ngày đi và số lượng vé để em hỗ trợ mình đặt chỗ nhé ạ!" |

  

Tổng điểm: 2.0 / 10

```

  

**Link trò chuyện:** https://share.gemini.google/SsVqjmEFn491
