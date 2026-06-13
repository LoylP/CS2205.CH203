# XÂY DỰNG HỆ THỐNG PHÁT HIỆN CHIẾN DỊCH PHISHING VÀ TIN GIẢ TẠI VIỆT NAM

> **A Multi-Agent Large Language Model System with Retrieval-Augmented Generation for Detecting Phishing Campaigns and Fake News in Vietnam**

![Course](https://img.shields.io/badge/Course-CS2205-0D2B6E?style=flat-square)
![Class](https://img.shields.io/badge/Class-CS2205.CH203-163580?style=flat-square)

---

## Thông tin học phần

|  |  |
|--------|-----------|
| **Học viên** | Nguyễn Hoàng Phúc |
| **MSHV** | 250101100 |
| **Lớp** | CS2205.CH203 |
| **Môn học** | CS2205 – Phương pháp luận Nghiên cứu Khoa học |
| **Giảng viên** | PGS.TS. Lê Đình Duy |
| **Trường** | Đại học Công nghệ Thông tin, ĐHQG-HCM |

---

## Tóm tắt

Sự bùng nổ của mạng xã hội tại Việt Nam tạo điều kiện cho các chiến dịch phishing và tin giả ngày càng tinh vi, trong khi các công cụ sinh nội dung AI khiến nội dung độc hại khó phân biệt với thông tin hợp lệ và các hệ thống phát hiện hiện tại thiếu khả năng lý luận theo ngữ cảnh. Đề tài đề xuất hệ thống xác minh tự động dựa trên Mô hình Ngôn ngữ Lớn và kiến trúc Multi-Agent, trong đó mỗi tác tử AI đảm nhận một tác vụ chuyên biệt — phân tích đầu vào, kiểm tra thực thể (URL, số điện thoại, tên miền), tra cứu thời gian thực và truy xuất bằng chứng — nhằm hỗ trợ người dùng phát hiện và xác minh thông tin một cách chính xác, minh bạch.

---

## Mục tiêu nghiên cứu

| # | Mục tiêu | Chỉ tiêu |
|---|----------|----------|
| 1 | Xây dựng bộ dữ liệu tiếng Việt | ~10.000 mẫu gán nhãn, chuẩn hóa train/val/test |
| 2 | Phát triển mô hình phân loại LLM | Accuracy & F1-score ≥ 90%, URC = 0 |
| 3 | Thiết kế hệ thống xác minh đa tác nhân + RAG | Nguyên mẫu web, phán quyết + bằng chứng + TTP mapping |

---

## Kiến trúc hệ thống

```
INPUT (text / URL / image)
        │
        ▼
┌───────────────────────────────────────────┐
│           MULTI-AGENT PIPELINE            │
│                                           │
│  Agent 1 → Tiếp nhận & phân tích đầu vào │
│  Agent 2 → Kiểm tra thực thể (URL/SĐT)   │
│  Agent 3 → Tra cứu trực tuyến             │
│  Agent 4 → Truy xuất RAG                  │
│            (BM25 + Vector Embedding)       │
│  Agent 5 → Phán quyết (Fine-tuned LLM)   │
│  Agent 6 → Trình bày kết quả              │
└───────────────────────────────────────────┘
        │
        ▼
OUTPUT: Nhãn phân loại + Bằng chứng + TTP Mapping + Khuyến nghị
```

**Công nghệ sử dụng:** CrewAI · LLaMA 3 / Qwen 3 / Gemma 3 · LoRA/PEFT · BM25 · Vector Embedding · Next.js · FastAPI

---

## 📊 Kết quả dự kiến

- ✅ Bộ dữ liệu tiếng Việt ~10.000 mẫu, công khai cho cộng đồng nghiên cứu
- ✅ Mô hình LLM tinh chỉnh đạt Accuracy & F1-score ≥ 90%, URC < 10, Latency < 5s
- ✅ Ứng dụng web xác minh thông tin theo thời gian thực
- ✅ Dashboard quản trị theo dõi xu hướng lừa đảo
- ✅ Báo cáo kỹ thuật đầy đủ và mã nguồn mở

---

*CS2205 – Phương pháp luận Nghiên cứu Khoa học · Trường ĐH Công Nghệ Thông Tin, ĐHQG-HCM · 2026*
