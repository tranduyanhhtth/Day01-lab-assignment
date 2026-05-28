# Ngày 1 — Bài Tập & Phản Ánh

## Nền Tảng LLM API | Phiếu Thực Hành

**Thời lượng:** 1:30 giờ  
**Cấu trúc:** Lập trình cốt lõi (60 phút) → Bài tập mở rộng (30 phút)

---

## Phần 1 — Lập Trình Cốt Lõi (0:00–1:00)

Chạy các ví dụ trong Google Colab tại: https://colab.research.google.com/drive/172zCiXpLr1FEXMRCAbmZoqTrKiSkUERm?usp=sharing

Triển khai tất cả TODO trong `template.py`. Chạy `pytest tests/` để kiểm tra tiến độ.

**Điểm kiểm tra:** Sau khi hoàn thành 4 nhiệm vụ, chạy:

```bash
python template.py
```

Bạn sẽ thấy output so sánh phản hồi của GPT-4o và GPT-4o-mini.

---

## Phần 2 — Bài Tập Mở Rộng (1:00–1:30)

### Bài tập 2.1 — Độ Nhạy Của Temperature

Gọi `call_openai` với các giá trị temperature 0.0, 0.5, 1.0 và 1.5 sử dụng prompt **"Hãy kể cho tôi một sự thật thú vị về Việt Nam."**

**Bạn nhận thấy quy luật gì qua bốn phản hồi?** (2–3 câu)

> Nhiệt độ càng cao thì câu trả lời càng đa dạng và sáng tạo hơn, có thể thêm chi tiết ngoài prompt. Nhiệt độ thấp (0.0) thường cho phản hồi ổn định, ít biến thiên và bám sát sự thật hơn. Ở 1.5, độ ngẫu nhiên tăng, đôi khi suy diễn rộng hơn.

**Bạn sẽ đặt temperature bao nhiêu cho chatbot hỗ trợ khách hàng, và tại sao?**

> Mình sẽ đặt khoảng 0.2–0.4 để đảm bảo câu trả lời nhất quán, chính xác và ít bịa đặt, đồng thời vẫn đủ linh hoạt để diễn đạt tự nhiên.

---

### Bài tập 2.2 — Đánh Đổi Chi Phí

Xem xét kịch bản: 10.000 người dùng hoạt động mỗi ngày, mỗi người thực hiện 3 lần gọi API, mỗi lần trung bình ~350 token.

**Ước tính xem GPT-4o đắt hơn GPT-4o-mini bao nhiêu lần cho workload này:**

> Khoảng 16–17 lần (0.010 / 0.0006 ≈ 16.7), số lượng token như nhau nên tỷ lệ chi phí giữ nguyên.

**Mô tả một trường hợp mà chi phí cao hơn của GPT-4o là xứng đáng, và một trường hợp GPT-4o-mini là lựa chọn tốt hơn:**

> GPT-4o xứng đáng khi cần chất lượng reasoning cao, tóm tắt tài liệu phức tạp hoặc hỗ trợ ra quyết định quan trọng. GPT-4o-mini phù hợp cho tác vụ lặp lại, trả lời FAQ, phân loại đơn giản, hoặc khối lượng lớn cần tối ưu chi phí.

---

### Bài tập 2.3 — Trải Nghiệm Người Dùng với Streaming

**Streaming quan trọng nhất trong trường hợp nào, và khi nào thì non-streaming lại phù hợp hơn?** (1 đoạn văn)

> Streaming quan trọng nhất khi người dùng cần cảm giác phản hồi ngay lập tức, ví dụ chat hỗ trợ khách hàng hoặc các tác vụ dài cần “đang trả lời”. Nó giúp giảm cảm nhận độ trễ và cho phép người dùng đọc dần khi câu trả lời còn đang sinh. Non-streaming phù hợp hơn khi cần một phản hồi hoàn chỉnh để xử lý hậu kỳ, lưu log, hoặc khi hệ thống chỉ hiển thị kết quả cuối cùng như báo cáo hay batch processing.

## Danh Sách Kiểm Tra Nộp Bài

- [ ] Tất cả tests pass: `pytest tests/ -v`
- [ ] `call_openai` đã triển khai và kiểm thử
- [ ] `call_openai_mini` đã triển khai và kiểm thử
- [ ] `compare_models` đã triển khai và kiểm thử
- [ ] `streaming_chatbot` đã triển khai và kiểm thử
- [ ] `retry_with_backoff` đã triển khai và kiểm thử
- [ ] `batch_compare` đã triển khai và kiểm thử
- [ ] `format_comparison_table` đã triển khai và kiểm thử
- [ ] `exercises.md` đã điền đầy đủ
- [ ] Sao chép bài làm vào folder `solution` và đặt tên theo quy định
