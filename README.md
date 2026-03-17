# 📊 Big Data Project – Hybrid RAG for Coffee Price Intelligence

## 1. 📄 Bài báo nền tảng (Base Paper)

**Tiêu đề:** RAG+: Enhancing Retrieval-Augmented Generation with Application-Aware Reasoning
**Hội nghị:** EMNLP 2025 (CORE A)
**Link:** [https://aclanthology.org/2025.emnlp-main.1630.pdf](https://aclanthology.org/2025.emnlp-main.1630.pdf)

---

## 2. 🧠 Động lực nghiên cứu

Các hệ thống RAG hiện tại:

* Phụ thuộc vào dữ liệu tĩnh
* Không xử lý tốt dữ liệu thời gian thực
* Chưa tổng hợp thông tin từ nhiều nguồn

Đồ án này mở rộng RAG để:

* Hỗ trợ **dữ liệu thời gian thực**
* Thực hiện **tổng hợp đa nguồn**
* Tăng độ tin cậy thông qua **trích xuất có cấu trúc**

---

## 3. 🎯 Bài toán

Xây dựng hệ thống trả lời câu hỏi như:

> “Giá cà phê hôm nay là bao nhiêu?”

Thông qua:

* Truy xuất nhiều nguồn dữ liệu
* Trích xuất thông tin giá có cấu trúc
* Tổng hợp thành khoảng giá cuối cùng

---

## 4. 🏗️ Kiến trúc hệ thống

### Pipeline:

1. Thu thập dữ liệu (historical + realtime)
2. Tiền xử lý (làm sạch, chia đoạn)
3. Lập chỉ mục Vector DB
4. Xử lý truy vấn
5. Truy xuất lai (Hybrid Retrieval):

   * Vector DB nội bộ
   * Tìm kiếm web (khi cần)
6. Tổng hợp & suy luận
7. Sinh câu trả lời

---

## 5. ⚡ Thiết kế Hybrid RAG

### Phân loại truy vấn

* Truy vấn tĩnh → dùng Vector DB
* Truy vấn thời gian thực → gọi Web Search

### Nguồn dữ liệu

* Cơ sở dữ liệu lịch sử (báo đã crawl)
* Dữ liệu web thời gian thực

---

## 6. 🔄 Xử lý dữ liệu thời gian thực

* Crawl định kỳ (10–60 phút)
* Lập chỉ mục tăng dần (incremental indexing)
* Dữ liệu mới được sử dụng ngay

---

## 7. 🧩 Trích xuất & tổng hợp thông tin

Ví dụ dữ liệu trích xuất:

[
{"location": "Lâm Đồng", "price": 118000},
{"location": "Đắk Lắk", "price": 120000}
]

Tổng hợp:

* Giá nhỏ nhất
* Giá lớn nhất
* Trung bình (tuỳ chọn)

Kết quả:

> “Giá cà phê hôm nay dao động từ 118,000 đến 120,000 VND/kg tùy khu vực.”

---

## 8. 📊 Dữ liệu

### Nguồn:

* Báo chí Việt Nam
* Website theo dõi giá nông sản

### Loại dữ liệu:

* Raw HTML (theo yêu cầu môn)
* Văn bản đã xử lý
* Dữ liệu có cấu trúc

---

## 9. ⚙️ Đánh giá tính khả thi

### Dữ liệu

* Public
* Cập nhật thường xuyên

### Phần cứng

* Chạy được trên máy cá nhân
* Không cần huấn luyện mô hình lớn

### Độ phức tạp

* Trung bình
* Dùng công cụ có sẵn

---

## 10. 🚀 Đóng góp đề xuất

So với bài báo nền tảng:

* Áp dụng vào bài toán thực tế
* Kết hợp **truy xuất lai (local + web)**
* Thực hiện **tổng hợp đa nguồn**
* Tăng độ tin cậy bằng **hiển thị nguồn**

---

## 11. 🧪 Kịch bản demo

### Case 1: Truy vấn tĩnh

> “Giá cà phê là gì?”
> → Trả lời từ database

### Case 2: Truy vấn realtime

> “Giá cà phê hôm nay?”
> → Lấy dữ liệu mới từ web + tổng hợp

---

## 12. 📌 Kết luận

Đồ án thể hiện:

* Mở rộng RAG sang dữ liệu động
* Kết hợp realtime trong hệ thống Big Data
* Tăng độ tin cậy bằng tổng hợp đa nguồn

---

## 13. 📎 Hướng phát triển

* Dùng LLM để phân loại truy vấn
* Đánh giá độ tin cậy nguồn
* Mở rộng với Spark/Kafka

---

**Trạng thái:** Sẵn sàng nộp proposal ✅
