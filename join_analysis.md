Giải trình kỹ thuật sử dụng `COUNT(o.order_id)` thay vì `COUNT(*)`:

Khi sử dụng `LEFT JOIN` với khách hàng chưa từng phát sinh giao dịch như Charlie, bảng phụ `Orders` sẽ trả về giá trị `NULL` cho mọi cột kết hợp. 
- Nếu dùng `COUNT(*)`, MySQL sẽ đếm cả dòng chứa toàn giá trị `NULL` đó, khiến kết quả trả về của Charlie bị sai lệch thành `1` đơn hàng thay vì `0`. 
- Ngược lại, khi sử dụng `COUNT(o.order_id)`, hàm `COUNT` chỉ đếm các giá trị không phải `NULL` xuất hiện trong cột `order_id`. Do đó, Charlie được tính chính xác là `0` đơn hàng, đảm bảo tính toàn vẹn cho chiến dịch.
