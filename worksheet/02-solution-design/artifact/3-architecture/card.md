# Lớp kiến trúc dữ liệu

## 1. Rủi ro xử lý
- **ID tình huống**: T-01.
- **Mẫu lỗi**: AI tự ý bịa đặt hoặc đưa sai mốc thời gian hạn nộp hồ sơ xin học bổng, người dùng tin tưởng hoàn toàn dẫn đến nộp trễ đơn học bổng xét tuyển sớm.
- **Hậu quả**: Thí sinh bị trượt học bổng oan do quá hạn nộp hồ sơ, gia đình thiệt hại tài chính lớn (lên tới hàng tỷ đồng), hình ảnh uy tín tuyển sinh của nhà trường bị khiếu kiện nghiêm trọng.
---

## 1. Giải pháp là gì?

> Hệ thống cần tra cứu các nguồn dữ liệu chính thức như trang web tuyển sinh hoặc tài liệu từ các tổ chức chính thức trước khi AI trả lời các câu hỏi liên quan đến thông tin quan trọng. Nếu không có dữ liệu hoặc nguồn có lỗi, AI sẽ không đưa ra câu trả lời và chuyển câu hỏi đến tư vấn viên.

---

## 2. Vì sao sửa ở lớp kiến trúc dữ liệu?

- Nguyên nhân chính là AI đang phải tự dựa vào thông tin, dẫn đến việc bịa thông tin hoặc không có dữ liệu chính thức.
- Cần có cơ chế kiểm tra dữ liệu trước khi trả lời để đảm bảo tính chính xác và độ tin cậy.
- Việc ghi lại lỗi sẽ giúp nhóm phát hiện những lỗi thường gặp và cải thiện hệ thống.

**Hành động phòng vệ chính**:
- [x] Ngăn lỗi bằng nguồn dữ liệu chính thức.
- [x] Phát hiện khi nguồn thiếu hoặc lỗi.
- [x] Khắc phục bằng cách chuyển sang người thật.
- [x] Ghi lại lỗi để cải thiện sau.

---

## 3. Demo nằm ở đâu?

**File demo**: [demo.md](./demo.md)

**Demo cần có**:
- Sơ đồ cách dữ liệu đi qua hệ thống
- Nguồn dữ liệu chính thức
- Bước kiểm tra trước khi AI trả lời
- Cách xử lý khi nguồn thiếu, lỗi hoặc quá cũ
- Cách ghi lại hoặc theo dõi lỗi

---

## 4. Tác dụng phụ

**Có thể gây vấn đề gì?**
> Việc truy cập và kiểm tra dữ liệu từ các nguồn chính thức có thể làm cho hệ thống trở nên chậm hơn, phụ thuộc vào nguồn và tốn công duy trì.

**Nhóm giảm vấn đề đó bằng cách nào?**
> Lưu trữ tạm dữ liệu phổ biến và thông báo khi nguồn dữ liệu có lỗi, có kế hoạch để người phụ trách cập nhật nguồn thông tin chính thức thường xuyên.

---

## 5. Checklist trước khi nộp

- [x] Sơ đồ cho thấy dữ liệu đi từ đâu đến đâu.
- [x] Có bước kiểm tra nguồn trước khi AI trả lời.
- [x] Có cách xử lý khi không có dữ liệu.
- [x] Có cách chuyển sang người thật với tình huống rủi ro cao.
- [x] Có cách biết lỗi này có đang lặp lại không.

**Người phụ trách**: Nguyễn Trọng Tiến