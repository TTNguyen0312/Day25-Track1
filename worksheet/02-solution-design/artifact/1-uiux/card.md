# card.md — Lớp Giao diện làm nổi bật thông tin & Nút chuyển tuyến khẩn cấp

## 1. Rủi ro xử lý
- **ID tình huống**: T-01.
- **Mẫu lỗi**: AI tự ý bịa đặt hoặc đưa sai mốc thời gian hạn nộp hồ sơ xin học bổng, người dùng tin tưởng hoàn toàn dẫn đến nộp trễ đơn học bổng xét tuyển sớm.
- **Hậu quả**: Thí sinh bị trượt học bổng oan do quá hạn nộp hồ sơ, gia đình thiệt hại tài chính lớn (lên tới hàng tỷ đồng), hình ảnh uy tín tuyển sinh của nhà trường bị khiếu kiện nghiêm trọng.

---

## 2. Tầng giải pháp
- **Lớp thiết kế**: Giao diện người dùng (UI/UX Layer).
- **Vì sao lớp này phù hợp**: Tác động trực tiếp vào tâm lý "Tin AI tuyệt đối" của học sinh và phụ huynh bằng cách trực quan hóa mức độ tin cậy của dữ liệu ngày tháng, đóng khung hộp cảnh báo nổi bật màu sắc tương phản và đưa ra nút bấm thoát chuyển cuộc gọi tới chuyên viên thật của trường khi cận kề deadline hoặc khi thí sinh gặp áp lực quá lớn.
- **Phối hợp**: Đồng bộ nhãn "✓ Đã xác minh chính thức" dựa trên dữ liệu an toàn được Backend xử lý ở Lớp 3 (Kiến trúc dữ liệu), đồng thời kết nối trực tiếp cổng chat với tư vấn viên thật khi người dùng tương tác nút chuyển tuyến trên màn hình.

---

## 3. Bản demo
- **File demo**: [demo.md](./demo.md) (Xem bản phác thảo giao diện ASCII và sơ đồ quy trình Mermaid).
- **Thành phần chính**:
  1. **Verified Source Badge**: Nhãn hiển thị màu xanh lá "✓ Đã xác minh chính thức từ admissions.vinhuni.edu.vn / vinhuni.edu.vn" đi kèm thời điểm cập nhật mới nhất.
  2. **Highlight Date Card**: Hộp thông tin mốc thời gian quan trọng đóng khung nổi bật, phông chữ lớn, màu tương phản đỏ/cam bắt mắt để người dùng không bỏ sót.
  3. **Direct Escalation CTA**: Nút bấm "Hỏi trực tiếp chuyên viên tuyển sinh" để kết nối người thật lập tức khi cần xử lý gia hạn hoặc nộp hồ sơ đặc biệt.

---

## 4. Tác dụng phụ và cách giảm
- **Tác dụng phụ**: Việc lạm dụng quá nhiều thẻ thông báo màu sắc nổi bật và nút chuyển tuyến trên Widget chat nhỏ có thể gây rối mắt (Cognitive overload), làm mất đi tính tự nhiên, thân thiện và linh hoạt của giao diện trò chuyện.
- **Cách giảm giảm**: Chỉ tự động kích hoạt thẻ Highlight khi mô hình phân loại (Intent Router) nhận diện người dùng đang hỏi cụ thể các chủ đề nhạy cảm có mốc thời gian/tiền bạc (Hạn nộp hồ sơ, Học phí, Điểm chuẩn). Các câu hỏi thảo luận chung về cuộc sống sinh viên hoặc mô tả ngành học sẽ chỉ sử dụng định dạng văn bản trơn tối giản.

---

## 5. Hành động phòng vệ
- [ ] Ngăn
- [ ] Phát hiện
- [x] Khắc phục (Cung cấp giải pháp thoát an toàn kết nối chuyên viên thật)
- [x] Thông báo (Trực quan hóa độ tin cậy và nổi bật hóa thông tin hạn chót nhạy cảm)

**Người phụ trách**: Hoàng Văn Bắc