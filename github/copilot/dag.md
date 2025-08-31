# Instructions cho Apache Airflow & Astro

- Tạo một DAG (Directed Acyclic Graph) Airflow để tự động hóa quy trình ETL.
- DAG cần có lịch chạy hàng ngày (`schedule_interval='@daily'`).
- Sử dụng các operators thích hợp, chẳng hạn như `PythonOperator`, để gọi các hàm ETL đã tạo.
- Định nghĩa các tasks rõ ràng: một task cho Extract, một cho Transform và một cho Load.
- Đảm bảo các tasks được sắp xếp theo đúng thứ tự (`task_extract >> task_transform >> task_load`).
- Cấu hình các kết nối Airflow đến Open-Meteo API và PostgreSQL. Lưu trữ các thông tin nhạy cảm như khóa API và thông tin đăng nhập DB dưới dạng Airflow Connections.
- Hỗ trợ các chức năng giám sát: Viết code để dễ dàng theo dõi trạng thái chạy và log của từng task.
