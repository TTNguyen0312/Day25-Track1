---
artifact: 2 — Lớp chỉ dẫn AI
bai-tap: 2 — Thiết kế giải pháp
demo: ./demo.md
---

# card.md — Lớp chỉ dẫn AI

**Tình huống xử lý**: T-01, T-02, T-10 
Xem `../../1-map-and-format.md` Phần A.

---

## 1. Giải pháp là gì?

Khi người dùng hỏi deadline, học phí, học bổng, điểm chuẩn và quy đổi điểm thì AI chỉ được đưa thông tin cụ thể khi có dữ liệu chính thức từ website tuyển sinh hoặc RAG data đã xác minh. Khi trả lời, AI cũng cần trích dẫn nguồn để người dùng có thể nhanh chóng tự check lại.

Nếu không tìm thấy nguồn phù hợp hoặc confidence thấp, AI phải:
- nói rõ chưa có thông tin xác minh,
- không tự suy đoán theo dữ liệu cũ,
- hướng người dùng sang website chính thức hoặc tư vấn viên thật.

Ngoài ra, nhóm thêm luật chống “pressure-trap” và “sycophancy”, ví dụ khi người dùng nói: “Em chỉ cần ước chừng thôi” hoặc “Chắc chắn em đậu đúng không?” thì AI phải giữ nguyên giới hạn an toàn, không chiều theo người dùng.


Ví dụ:

> Khi người dùng hỏi ngày, số tiền hoặc chính sách tuyển sinh, AI chỉ được trả lời nếu có nguồn chính thức. Nếu thiếu nguồn, AI phải nói rõ là chưa xác minh được và chuyển cho tư vấn viên.

---

## 2. Vì sao sửa ở lớp chỉ dẫn AI?

- AI đang chiều theo giả định sai của người dùng.
- AI cần luật rõ: khi nào trả lời, khi nào từ chối, khi nào chuyển sang người thật.

**Hành động phòng vệ chính**:

- [x] Ngăn câu trả lời sai ngay từ đầu
- [x] Bắt buộc nêu nguồn khi nói về thông tin quan trọng
- [x] Từ chối trả lời khi thiếu căn cứ
- [x] Chuyển người thật khi vượt phạm vi

---

## 3. Demo nằm ở đâu?

**File demo**: [`demo.md`](./demo.md)

Demo cần có:

- Luật chính cho AI
- Mẫu câu khi thiếu nguồn
- Mẫu câu khi cần chuyển sang người thật
- 2-3 ví dụ hỏi đáp để kiểm tra luật
- Kết quả thử lại với vài tình huống từ Bài 1

---

## 4. Tác dụng phụ

**Có thể gây vấn đề gì?**

- AI có thể từ chối quá nhiều nếu dữ liệu chưa cập nhật.
- Câu trả lời có thể dài và cứng hơn vì phải kèm nguồn và cảnh báo.
- Trải nghiệm chậm hơn do phải kiểm tra RAG source và confidence.
- Người dùng có thể khó chịu khi AI không “đoán giúp”.

**Nhóm giảm vấn đề đó bằng cách nào?**

- Chỉ bắt buộc source-check với thông tin rủi ro cao (deadline, học phí, học bổng, điểm chuẩn).
- Dùng “từ chối mềm” thay vì block hoàn toàn:
  > “Hiện mình chưa có dữ liệu xác minh cho năm 2026.”
- Nếu có dữ liệu năm trước, AI được phép đưa để tham khảo nhưng phải gắn nhãn:
  > “Thông tin năm trước — chưa phải công bố chính thức năm nay.”
- Kết hợp escalation sang tư vấn viên khi confidence thấp.
- Kiểm thử lại bằng bộ test T-01 → T-10 để tránh over-refusal.

---

## 5. Checklist trước khi nộp

- [x] Luật viết đủ cụ thể để AI làm theo.
- [x] Có mẫu câu khi AI không có đủ thông tin.
- [x] Có ví dụ cho tình huống dễ sai.
- [x] Có thử lại bằng tình huống trong Bài 1.
- [x] Không dùng prompt như cách duy nhất nếu lỗi nằm ở dữ liệu hoặc quy trình.

**Người phụ trách**: Hoàng Đức Nghĩa
