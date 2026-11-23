# BÀI LÀM PHA 2 (ĐỀ LUYỆN TẬP CHỦ ĐỀ TÀI CHÍNH CÁ NHÂN)

- **Họ tên:** Đào Tuấn Đạt
- **Lớp:** HNKS26CNTT3
- **Link repository Pha2:** [GitHub](https://github.com/tuandatdzquatroihihi/HNKS26CNTT3_KNPromptAI_LT)
- **Công cụ AI đã dùng (ChatGPT/Claude/Gemini):** Gemini

> Pha 2 (20 phút cuối). Mỗi mục: mở cuộc trò chuyện mới, gửi nguyên văn prompt đã viết trong bai_lam_pha1.md, dán câu trả lời và link chia sẻ vào đây. Xong, kéo thả file này vào repository Pha2.

## 4.2. Trích xuất tin nhắn đăng ký hội thảo ra JSON

**KET QUA AI**

```json
[
  {
    "ma_goi": "DT",
    "ngay_hoi_thao": "2026-12-20",
    "nguoi_lon": 2,
    "tre_em": 1,
    "hang_ve": "thuong",
    "ghi_chu": null
  },
  {
    "ma_goi": "CB",
    "ngay_hoi_thao": "2027-01-10",
    "nguoi_lon": 3,
    "tre_em": 0,
    "hang_ve": "thuong",
    "ghi_chu": "một người dùng xe lăn cần lối đi riêng"
  },
  {
    "ma_goi": "VIP",
    "ngay_hoi_thao": null,
    "nguoi_lon": 4,
    "tre_em": 0,
    "hang_ve": "vip",
    "ghi_chu": "một anh mắt kém cần ngồi bàn đầu gần màn hình chiếu"
  }
]
```

**Link trò chuyện:** https://share.gemini.google/gE8A6hZcCGIZ

## 4.3. Báo giá vé hội thảo bằng Chain-of-Thought

**KET QUA AI**

```text
Dưới đây là bảng tính chi tiết báo giá chi phí tham dự hội thảo tài chính cho nhóm của bạn:

1. **Tiền người lớn:**
Nhóm chọn gói DT (Gói Đầu Tư) với đơn giá 1.500.000 đồng/người lớn cho 4 người lớn:

$$4 \times 1.500.000 = 6.000.000\text{ đồng}$$


2. **Tiền trẻ em:**

* 2 trẻ em (8 tuổi và 11 tuổi) thuộc nhóm từ 6 đến 12 tuổi nên tính 50% giá người lớn ($1.500.000 \times 50\% = 750.000\text{ đồng/bé}$).
* 1 bé 4 tuổi thuộc nhóm dưới 6 tuổi nên được miễn phí ($0\text{ đồng}$).

$$(2 \times 1.500.000 \times 50\%) + (1 \times 0) = 1.500.000\text{ đồng}$$



3. **Tiền vé (trước giảm giá):**
Tổng tiền vé bao gồm tiền vé người lớn và tiền vé trẻ em:

$$6.000.000 + 1.500.000 = 7.500.000\text{ đồng}$$


4. **Giảm giá nhóm:**
Vì nhóm có đủ 4 người lớn trở lên nên được áp dụng mức giảm 10% trên tổng tiền vé:

$$7.500.000 \times 10\% = 750.000\text{ đồng}$$



*(Tiền vé sau giảm giá: $7.500.000 - 750.000 = 6.750.000\text{ đồng}$)*
5. **Phụ thu sổ tay:**
Nhóm đặt mua thêm 2 bộ sổ tay lập kế hoạch tài chính cá nhân với đơn giá 200.000 đồng/bộ (không áp dụng giảm giá):

$$2 \times 200.000 = 400.000\text{ đồng}$$


6. **Tổng tiền:**
Tổng số tiền thanh toán bằng tiền vé sau giảm cộng với khoản phụ thu sổ tay:

$$(7.500.000 - 750.000) + 400.000 = 7.150.000\text{ đồng}$$



[RESULT: 7.150.000 đồng]
```

**Link trò chuyện:** https://share.gemini.google/iai0ylPBIWOz

### b) Kiểm tra kết quả AI
Đúng
## 4.4. Dây chuyền xử lý khiếu nại – kết quả Trạm 1

**KET QUA AI**

```text
{
  "loai_su_co": "sai_khu_vuc",
  "so_khach": 2,
  "so_phien_bi_anh_huong": 2,
  "tom_tat": "Khách mua gói DT bị xếp ngồi ghế phụ thiếu bàn viết như cam kết trong 2 phiên học đầu."
}
```

**Link trò chuyện:**  https://share.gemini.google/u5gI1yYuox6o

## 4.5. Prompt chấm bài theo Rubric

**KET QUA AI**

```text
| Tiêu chí | Điểm | Minh chứng | Đề xuất sửa |
| --- | --- | --- | --- |
| **Đúng thông tin (50%)** | 5.0 / 5.0 | **Minh chứng:** Đã cung cấp thông tin về giá vé (*"1.000.000đ/người"*) và chính sách hủy (*"huỷ trước 3 ngày thì được hoàn tiền đầy đủ"*).<br>

<br>**Lý do:** Dữ liệu đầu vào không cung cấp thông tin chuẩn để đối chiếu sai lệch nên ghi nhận đủ điểm cho phần cung cấp thông tin này. | Không cần sửa (Giữ nguyên thông tin nếu đã khớp với quy định của công ty). |
| **Đầy đủ (30%)** | 1.5 / 3.0 | **Câu bị lỗi:** *"Anh cần gì cứ nhắn em nhé!"*<br>

<br>**Lý do sai:** Đã trả lời được 2 ý hỏi về giá và chính sách hủy, nhưng thiếu bước kêu gọi hành động (CTA) mời khán giả cung cấp ngày diễn ra trận đấu và số lượng vé cần đặt. | *"Anh vui lòng cho em biết ngày diễn ra trận đấu và số lượng vé cần đặt để em hỗ trợ giữ chỗ cho mình nhé ạ."* |
| **Giọng điệu (20%)** | 1.0 / 2.0 | **Câu bị lỗi:** *"xem rất đã luôn ạ."*, *"nha anh."*<br>

<br>**Lý do sai:** Sử dụng từ ngữ mang tính văn nói, suồng sã (*"rất đã"*, *"nha"*), chưa đảm bảo tính chuyên nghiệp trong giao tiếp với khách hàng. | Thay *"xem rất đã luôn ạ"* bằng *"vị trí ngồi có tầm nhìn rất tốt ạ"*.<br>

<br>Thay *"nha anh"* bằng *"ạ"* (VD: *"...được hoàn tiền đầy đủ ạ."*). |
| **Tổng điểm** | **7.5 / 10** |  |  |
```

**Link trò chuyện:** https://share.gemini.google/I58N2tK7wEgO
