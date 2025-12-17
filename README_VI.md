# Mô hình Chấm điểm Tín dụng Thích ứng (Adaptive Credit Scoring)

## 📌 Tổng quan Dự án
Dự án này giải quyết một hạn chế lớn trong tín dụng tiêu dùng truyền thống: khả năng phát hiện hành vi **"Vay chồng chéo" (Loan Stacking)**. Những người vay liên tục vay khoản mới để trả nợ cũ thường có lịch sử trả nợ hoàn hảo cho đến khi họ mất khả năng thanh toán hoàn toàn.

Dự án so sánh hai phương pháp tiếp cận:
1.  **Model A (Truyền thống):** Dựa trên lịch sử trả nợ quá khứ (Phản ứng).
2.  **Model B (Thích ứng):** Dựa trên khả năng chi trả và dòng tiền thực tế (Dự báo).

## ⚠️ Vấn đề
Các mô hình chấm điểm truyền thống thường phân loại nhầm "Người vay chồng chéo" là khách hàng tốt vì:
* Lịch sử trả nợ của họ rất sạch (được trả bằng nợ mới).
* Rủi ro vỡ nợ bị trì hoãn chứ không biến mất.

**Mục tiêu:** Xây dựng mô hình cảnh báo sớm sự tích tụ nợ không bền vững trước khi nợ xấu xảy ra.

## 🛠️ Công nghệ sử dụng
* **Ngôn ngữ:** Python
* **Môi trường:** Google Colab / Jupyter Notebook
* **Thư viện:** Pandas, NumPy, Scikit-learn, Matplotlib, Seaborn

## 📂 Phương pháp thực hiện

### Giai đoạn 1: Giả lập Dữ liệu & Feature Engineering
* Tạo bộ dữ liệu quan hệ giả lập (Khách hàng, Khoản vay, Giao dịch).
* Mô phỏng hồ sơ "Rủi ro tiềm ẩn": Người có thu nhập biến động và hành vi vay nợ tích lũy.
* **Các chỉ số chính:** `DSR` (Tỷ lệ nợ/thu nhập), `Thu nhập thặng dư`, `Tốc độ tăng trưởng nợ`.

### Giai đoạn 2: Xây dựng Mô hình (Random Forest)
* **Model A:** Chỉ học từ thông tin nhân khẩu học và nợ xấu quá khứ.
* **Model B:** Học từ sức khỏe tài chính (DSR, số khoản vay đồng thời).
* **Kết quả:** Model A không phát hiện được rủi ro (AUC ~0.5), trong khi Model B đạt độ chính xác cao (AUC > 0.9).

### Giai đoạn 3: Mô phỏng Chính sách
* Giả lập kết quả kinh doanh trên danh mục 2,000 khách hàng.
* So sánh **Chiến lược A** (Tăng trưởng nóng) vs **Chiến lược B** (Tín dụng bền vững).

## 📊 Kết quả Chính
| Chỉ số | Chiến lược Truyền thống | Chiến lược Thích ứng |
| :--- | :--- | :--- |
| **Phát hiện rủi ro** | Thụ động (Bỏ sót rủi ro ẩn) | Chủ động (Dựa trên DSR) |
| **Tăng trưởng** | Cao | Trung bình (Từ chối hồ sơ xấu) |
| **Rủi ro nợ xấu** | **Nghiêm trọng (Lỗ lớn)** | **Tối thiểu (An toàn)** |

> **Kết luận:** Bằng cách chấp nhận giảm bớt doanh số từ nhóm khách hàng rủi ro cao, Mô hình Thích ứng giúp ngăn chặn các khoản lỗ lớn trong dài hạn, đảm bảo tính bền vững cho danh mục đầu tư.

## 📝 Tác giả
* **Đoàn Nguyên Trí. Email: doantri12343@gmail.com**
* *Lưu ý: Dự án sử dụng dữ liệu giả lập nhằm mục đích nghiên cứu và phân tích.*
