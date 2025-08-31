# Instructions cho Python

- Viết các hàm Python cho từng bước trong quy trình ETL.
- Tạo một hàm để trích xuất dữ liệu từ Open-Meteo API. Hàm này cần xử lý các tham số như vị trí (vĩ độ, kinh độ) và trả về dữ liệu JSON thô.
- Viết một hàm để chuyển đổi dữ liệu JSON thô thành một định dạng có cấu trúc, ví dụ như một DataFrame của Pandas hoặc một dictionary chuẩn.
- Viết một hàm để tải dữ liệu đã xử lý vào cơ sở dữ liệu PostgreSQL. Hàm này cần kết nối với DB và thực hiện các câu lệnh INSERT/UPDATE.
- Luôn thêm docstrings cho các hàm để mô tả chức năng, tham số và giá trị trả về.
- Xử lý lỗi: Xử lý các lỗi HTTP, lỗi kết nối cơ sở dữ liệu và các lỗi khác một cách tường minh (sử dụng khối `try...except`).
