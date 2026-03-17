# 📊 Optimizing Data Pipeline for RAG-based Question Answering on Vietnamese News Data

---

## 🎯 1. Giới thiệu

Dự án này tập trung xây dựng một hệ thống hỏi đáp (Question Answering) dựa trên mô hình Retrieval-Augmented Generation (RAG), với trọng tâm là **tối ưu hóa pipeline xử lý dữ liệu lớn** từ các nguồn báo chí tiếng Việt.

Khác với các nghiên cứu chỉ tập trung vào mô hình ngôn ngữ, dự án này nhấn mạnh vào:

* Thu thập dữ liệu quy mô lớn
* Xử lý dữ liệu nhiễu (raw HTML)
* Tối ưu truy xuất thông tin
* Đánh giá hiệu năng hệ thống

---

## 🧠 2. Bài báo nền tảng

* **RAG+: Enhancing Retrieval-Augmented Generation with Application-Aware Reasoning (EMNLP 2025)**

### 📌 Tóm tắt

Bài báo đề xuất cải tiến RAG bằng cách bổ sung cơ chế reasoning theo ngữ cảnh ứng dụng, giúp nâng cao chất lượng câu trả lời.

### 🎯 Hạn chế

* Chưa tập trung vào dữ liệu thực tế (noisy data)
* Chưa tối ưu pipeline xử lý dữ liệu lớn
* Chưa đánh giá ảnh hưởng của preprocessing

---

## 🔍 3. Research Gap

Hiện tại, các hệ thống RAG:

* Chưa xử lý tốt dữ liệu HTML nhiễu
* Chưa tối ưu pipeline cho dữ liệu lớn và đa nguồn
* Chưa đánh giá sâu về hiệu năng truy xuất (latency, scalability)

👉 Dự án này nhằm giải quyết các vấn đề trên.

---

## 🚀 4. Kiến trúc hệ thống

### 🔹 4.1 Data Ingestion

* Crawl dữ liệu từ các trang báo
* Lưu trữ raw HTML

### 🔹 4.2 Data Processing

* Làm sạch HTML
* Loại bỏ noise
* Chuẩn hóa văn bản
* Deduplicate dữ liệu

### 🔹 4.3 Indexing & Storage

* Chia nhỏ văn bản (chunking)
* Tạo embedding
* Lưu trữ:

  * Vector Database (FAISS / Chroma)
  * Document Store

### 🔹 4.4 Retrieval

* BM25
* Vector Search
* Hybrid Search

### 🔹 4.5 RAG QA System

* Nhận câu hỏi từ người dùng
* Truy xuất tài liệu liên quan
* Sinh câu trả lời

---

## 📊 5. Thực nghiệm

### 🔬 So sánh phương pháp truy xuất

| Method | Accuracy | Latency |
| ------ | -------- | ------- |
| BM25   | TBD      | TBD     |
| Vector | TBD      | TBD     |
| Hybrid | TBD      | TBD     |

---

### 🧪 Các yếu tố đánh giá

* Ảnh hưởng của cleaning
* Chunk size
* Top-k retrieval

---

## 💾 6. Dataset

* Dữ liệu báo chí tiếng Việt
* Dạng: raw HTML
* Nguồn: nhiều website khác nhau

### 📌 Đặc điểm

* Dữ liệu nhiễu (noisy)
* Không đồng nhất
* Quy mô lớn

---

## ⚙️ 7. Công nghệ sử dụng

* Python
* FAISS / ChromaDB
* BM25 (rank_bm25)
* LLM API / local model

---

## 🎯 8. Mục tiêu

* Xây dựng pipeline xử lý dữ liệu lớn
* Tối ưu hiệu năng truy xuất
* Đánh giá hệ thống RAG trên dữ liệu thực tế

---

## 📌 9. Kết luận kỳ vọng

* Hiểu rõ ảnh hưởng của pipeline dữ liệu
* Đề xuất phương pháp tối ưu retrieval
* Áp dụng hiệu quả RAG trong bối cảnh dữ liệu lớn

---

## 👨‍💻 10. Thành viên

* (Điền tên nhóm)

---

## 📅 11. Tiến độ dự kiến

| Giai đoạn | Nội dung             |
| --------- | -------------------- |
| Week 1-2  | Crawl dữ liệu        |
| Week 3-4  | Processing           |
| Week 5-6  | Indexing + Retrieval |
| Week 7-8  | Evaluation           |

---

## 🔥 12. Điểm nổi bật

* Kết hợp Big Data + RAG
* Dữ liệu thực tế (không phải benchmark sạch)
* Có experiment rõ ràng

---

**Project này hướng tới việc xây dựng một hệ thống xử lý dữ liệu lớn hoàn chỉnh, không chỉ dừng lại ở mô hình AI.**
