Nhật ký tương tác AI (AI Prompt Log):

- Câu hỏi 1 (Brainstorm): "Trong cơ sở dữ liệu MySQL, mặc định từ khóa JOIN (khi không ghi rõ LEFT hay RIGHT) hoạt động như thế nào?"
  -> Phản hồi: Mặc định là INNER JOIN, chỉ giữ lại các bản ghi có sự khớp dữ liệu ở cả hai bảng.
- Câu hỏi 2 (Logic Check): "Khi sử dụng LEFT JOIN và đếm số lượng đơn hàng, nên dùng COUNT() hay COUNT(cột)?"
  -> Phản hồi: Nên dùng COUNT(cột khóa chính bảng phụ) để bỏ qua giá trị NULL, giúp bản ghi mồ côi hiển thị đúng số lượng là 0.
- Câu hỏi 3 (Performance): "Phân tích hiệu năng LEFT JOIN kết hợp IS NULL so với subquery NOT IN."
  -> Phản hồi: Kỹ thuật Anti-Join được tối ưu hóa rất tốt qua thuật toán Nested-Loop Join và an toàn hơn khi gặp giá trị NULL.
