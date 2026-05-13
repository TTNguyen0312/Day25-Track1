---
title: 00 — Bối cảnh sản phẩm của nhóm
section: Day 25 — dùng lại cho mọi cuộc trò chuyện với AI
format: Nhóm
time: Điền 5 phút đầu buổi
---

# 00-context.md — Bối cảnh sản phẩm của nhóm

Điền file này một lần ở đầu buổi. Sau đó, mỗi lần dùng AI, hãy đưa toàn bộ nội dung file này vào đầu cuộc trò chuyện.

Lý do: AI không tự nhớ bối cảnh giữa các cuộc trò chuyện. Nếu mỗi lần đưa bối cảnh khác nhau, câu trả lời cũng sẽ lệch.

---

## 1. Sản phẩm

- **Tên sản phẩm / bot**: Chatbot tư vấn tuyển sinh đại học
- **Sản phẩm giúp ai làm gì**: Giúp học sinh lớp 12 và phụ huynh tra cứu thông tin tuyển sinh (ngành học, điểm chuẩn, học phí, học bổng, deadline nộp hồ sơ) trên website tuyển sinh chính thức của trường đại học.
- **Người dùng gặp sản phẩm ở đâu**: Website tuyển sinh chính thức của trường đại học hoặc cổng thông tin tuyển sinh quốc gia (ví dụ: tuyensinh.vinhuni.edu.vn, tuyensinh.hust.edu.vn)
- **Giai đoạn hiện tại**: Chuẩn bị ra mắt / đang thử nghiệm

---

## 2. Phạm vi

**AI được làm gì**

- Trả lời câu hỏi về ngành học, tổ hợp xét tuyển, điểm chuẩn các năm trước (nếu có trong RAG data), học phí, học bổng và deadline nộp hồ sơ dựa trên thông tin đã được công bố.
- Giải thích nguyên tắc cộng điểm ưu tiên khu vực và đối tượng ưu tiên.
- Hướng dẫn học sinh đến nguồn thông tin chính thức (trang tuyển sinh, hotline tư vấn) khi không có dữ liệu hoặc dữ liệu chưa được cập nhật.

**AI không được làm gì**

- Xác nhận học bổng chính thức hoặc cam kết học sinh sẽ được nhận học bổng.
- Nộp hồ sơ thay học sinh hoặc thực hiện bất kỳ thao tác hành chính nào.
- Cam kết kết quả tuyển sinh (đỗ/rớt) cho học sinh.
- Đưa ra lời khuyên cá nhân hóa về việc nên/không nên nộp nguyện vọng cụ thể.
- Cung cấp điểm chuẩn, deadline, hoặc mức học bổng cụ thể cho năm hiện tại khi chưa có dữ liệu chính thức hoặc dữ liệu đã lỗi thời.

**Vì sao có giới hạn này**

Thông tin tuyển sinh (điểm chuẩn, chỉ tiêu, học bổng) thay đổi hàng năm và chỉ được công bố chính thức sau kỳ thi. Nếu AI đưa ra số liệu sai, học sinh có thể nộp sai nguyện vọng hoặc bỏ lỡ deadline, hậu quả ảnh hưởng trực tiếp đến lộ trình 4 năm đại học và không thể phục hồi trong kỳ tuyển sinh đó. Học sinh yếu thế (không có mentor, ở tỉnh xa) bị thiệt thòi nhiều nhất vì không có kênh nào xác nhận lại thông tin.

---

## 3. Người dùng

- **Là ai**: Học sinh lớp 12 (17-18 tuổi) và phụ huynh đang trong giai đoạn tìm hiểu và ra quyết định nộp hồ sơ đại học. Nhiều người không có gia sư hay mentor tư vấn, phụ thuộc nhiều vào thông tin online.
- **Họ hỏi AI khi nào**: 1-3 tháng trước deadline nộp hồ sơ, khi nhìn thấy chatbot trên website có logo trường và tin đây là kênh thông tin chính thức của nhà trường.
- **Họ cần quyết định gì sau khi hỏi AI**: Chọn nguyện vọng, sắp xếp thứ tự nguyện vọng, quyết định có nộp hồ sơ ngành/trường đó không, lên kế hoạch tài chính (học phí, học bổng).
- **Khi nào họ dễ bị tổn thương / dễ hiểu sai**: Khi đang áp lực cao gần deadline, khi không có kênh nào khác để fact-check (học sinh ở tỉnh xa, không có mentor), khi chatbot xuất hiện trên website chính thức khiến họ mặc định tin thông tin là chính xác.
- **Họ thường tin AI đến mức nào**: Tin ngay,vì chatbot hiển thị trên website chính thức của trường, học sinh cho rằng đây là kênh thông tin chính thống, ít khi double-check.

---

## 4. Bối cảnh ngành

- **Sự cố tương tự đã từng xảy ra**: Thông tin sai về điểm chuẩn lan truyền qua group Facebook, Zalo không xác thực dẫn đến học sinh nộp sai nguyện vọng trong các mùa tuyển sinh trước. Nguy cơ tương tự cao hơn khi kênh phát tán là chatbot có giao diện chính thức.
- **Quy định hoặc ràng buộc liên quan**: Thông tin tuyển sinh phải dựa trên công bố chính thức từ Bộ GD&ĐT và website trường. Chatbot không có thẩm quyền xác nhận kết quả tuyển sinh hay cam kết học bổng.
- **Nguồn chính thức nên ưu tiên**: Website tuyển sinh của từng trường đại học, cổng thông tin tuyển sinh quốc gia (thisinh.thitotnghiepthpt.edu.vn), hotline tư vấn tuyển sinh của trường.

---

## 5. Ghi chú thêm

- **Failure chính cần phòng**: Hallucination, AI đưa điểm chuẩn, deadline, học bổng cụ thể cho năm hiện tại khi không có dữ liệu chính thức hoặc dữ liệu đã lỗi thời.
- **Test set đã xây dựng**: 5 test case (T1–T5) bao gồm câu hỏi thông thường, câu hỏi điểm chuẩn năm hiện tại, câu hỏi học bổng mô tả phi chính thức, pressure trap và điểm ưu tiên khu vực.
- **Nhóm người dùng dễ bị bỏ sót**: Học sinh vùng sâu/vùng xa, dân tộc thiểu số hỏi về điểm ưu tiên khu vực, AI có thể bỏ qua điểm cộng KV và trả lời như học sinh thành phố.
- **Điểm rủi ro kỹ thuật**: RAG data cần được cập nhật định kỳ mỗi năm từ nguồn chính thống. Nếu không cập nhật, model sẽ hallucinate từ data cũ.
- **Ví dụ câu hỏi thật học sinh hay hỏi**: "Điểm chuẩn ngành KHMT CLC BK HCM năm nay là bao nhiêu?", "Trường có hỗ trợ gì cho con nhà nghèo học giỏi không?", "Em ở vùng núi, được cộng 1.5 điểm KV1, thi được 23.5 điểm, có nên nộp ngành Kỹ thuật điện không?"

---

## Cách dùng

```text
1. Mở công cụ AI phù hợp với bước đang làm.
2. Đưa toàn bộ nội dung file này vào đầu cuộc trò chuyện.
3. Chọn prompt tham khảo từ thư mục ../prompts/ và chỉnh lại nếu cần.
4. Đọc lại bản nháp AI tạo ra.
5. Sửa lại cho đúng bối cảnh nhóm.
6. Lưu kết quả vào đúng file trong worksheet/.
```

Ghi chú: nội dung trong `[...]` là chỗ cần điền. Sau khi điền xong, xóa dấu ngoặc nếu không cần giữ.
