---
artifact: 1 — FINAL kế hoạch giải pháp
bai-tap: 2 — Thiết kế giải pháp
phase: Chọn rủi ro + chọn tầng + chọn demo + chốt 3 lớp giải pháp
time: 11:00-11:55
input: 00-context.md + 01-test-set-review/3-FINAL-test-set-eval-plan.md
nop-cuoi: Có — file cuối Bài 2
---

# 1. Kế hoạch giải pháp

File này ghi lại quyết định chính của Bài 2:

- **Rủi ro**: Khi AI bịa đặt thông tin hoặc cung cấp mốc thời gian sai cho hồ sơ xin học bổng, người dùng có thể tin tưởng hoàn toàn, dẫn đến việc nộp hồ sơ trễ.
- **Nguyên nhân gốc**: AI đang tự đưa ra thông tin mà không kiểm tra nguồn, gây ra việc cung cấp dữ liệu không chính xác.
- **Lớp giải pháp**: Xây dựng ba lớp giải pháp: Giao diện người dùng, Chỉ dẫn AI, và Kiến trúc dữ liệu.

Ba lớp này bổ sung cho nhau, giúp giảm thiểu rủi ro từ mọi hướng.

## Phần A — Chọn rủi ro và tầng giải pháp

### Rủi ro chính được chọn
- **ID tình huống**: T-01
- **Mô tả ngắn**: AI bịa đặt hoặc đưa sai mốc thời gian nộp hồ sơ học bổng, gây thiệt hại tài chính cho người dùng và uy tín cho trường.
- **Mức độ**: Nặng
- **Điểm rủi ro**: 9/10
- **Vì sao chọn tình huống này**: Lỗi này có thể dẫn đến hậu quả nghiêm trọng, ảnh hưởng trực tiếp đến học sinh và cả thương hiệu tuyển sinh của trường.

### Tìm nguyên nhân gốc
- **Nguyên nhân gốc**:
    - Thiếu nguồn dữ liệu chính thức.
    - AI đoán thông tin khi không có dữ liệu chính thức.
    - Giao diện không cảnh báo mức độ tin cậy của thông tin.
    - Quy trình thiếu bước chuyển sang người thật khi gặp rủi ro cao.

| Nguyên nhân gốc | Tầng ưu tiên sửa | Lớp giải pháp liên quan |
|-----------------|------------------|-------------------------|
| Thiếu nguồn đúng | Dữ liệu / tra cứu nguồn (RAG) | `3-architecture` là chính |
| AI đoán bừa | Chỉ dẫn hệ thống / quy tắc từ chối | `2-prompt` là chính |
| Người dùng tin quá mức | Giao diện cảnh báo / cách viết mức tin cậy | `1-uiux` là chính |

### 10 tầng giải pháp tham khảo
| Tầng | Khi nào dùng |
|---|---|
| Giao diện | Người dùng tin AI quá mức, thiếu cảnh báo, thiếu nguồn, thiếu nút chuyển sang người thật |
| Chỉ dẫn AI | AI đoán khi không biết, không hỏi lại, không từ chối |
| Quy trình xử lý | Cần phân loại ý định, chuyển đúng nơi xử lý, có cách xử lý khi AI không nên trả lời |

---

## Phần B — Chọn định dạng demo

| Lớp | Thư mục | Định dạng demo chọn | Thời gian dự kiến |
|---|---|---|---|
| Giao diện | `1-uiux` | [ASCII Mockup] | 15 phút |
| Chỉ dẫn AI | `2-prompt` | [Markdown + ví dụ prompt] | 10 phút |
| Kiến trúc dữ liệu | `3-architecture` | [Mermaid / Sơ đồ hộp-mũi tên] | 10 phút |

---

## Phần C — Ba lớp giải pháp

### Lớp 1 — Giao diện (`artifact/1-uiux/`)

- **Cách tiếp cận**: Sử dụng màu sắc nổi bật để cảnh báo người dùng khi thông tin có nguy cơ sai lệch hoặc chưa được xác minh. Cung cấp nút bấm chuyển sang người thật khi cần thiết.
- **Hành động phòng vệ bao phủ**: Thông báo, Phát hiện, Khắc phục
- **Demo**: ASCII mockup, mô phỏng giao diện chat tuyển sinh với thẻ Highlight
- **Trạng thái**: Xong

### Lớp 2 — Chỉ dẫn AI (`artifact/2-prompt/`)

- **Cách tiếp cận**: Áp dụng quy tắc rõ ràng cho AI để từ chối hoặc yêu cầu xác nhận thêm từ người dùng khi không đủ dữ liệu.
- **Hành động phòng vệ bao phủ**: Ngăn, Từ chối, Dẫn nguồn
- **Demo**: Bản Markdown mô phỏng các prompt cùng ví dụ
- **Trạng thái**: Đang làm

### Lớp 3 — Kiến trúc dữ liệu (`artifact/3-architecture/`)

- **Cách tiếp cận**: Kiểm tra nguồn dữ liệu chính thức trước khi trả lời, và chuyển câu hỏi đến người thật nếu nguồn không có dữ liệu hợp lệ.
- **Hành động phòng vệ bao phủ**: Ngăn, Phát hiện, Khắc phục
- **Demo**: Sơ đồ quy trình dữ liệu sử dụng Mermaid
- **Trạng thái**: Xong

---

## Tổng kiểm tra

| Câu hỏi | Trả lời |
|---|---|
| Rủi ro chính đã chọn là gì? | T-01 |
| Nguyên nhân gốc là gì? | Thiếu nguồn dữ liệu chính thức, AI đoán bừa |
| 3 lớp giải pháp đã đủ chưa? | Giao diện: Xong / Chỉ dẫn AI: Đang làm / Kiến trúc: Xong |
| 4 hành động đã bao phủ chưa? | Ngăn: Đủ / Phát hiện: Đủ / Khắc phục: Đủ / Thông báo: Đủ |

---

## Phản biện chéo

| Góc phản biện | Câu hỏi |
|---|---|
| Đúng tầng | Giải pháp có sửa đúng nguyên nhân gốc không? |
| Cụ thể | Demo có đủ rõ để hiểu cách vận hành không? |
| Đủ lớp | 3 lớp có bổ sung cho nhau không, hay đang lặp cùng một ý? |
| Tác dụng phụ | Giải pháp có làm chậm, tốn kém, rối giao diện, hoặc gây hiểu nhầm mới không? |