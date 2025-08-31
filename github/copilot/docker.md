# Instructions cho Docker

- Tạo một `Dockerfile` để đóng gói toàn bộ ứng dụng ETL và các dependencies của nó.
- `Dockerfile` cần sử dụng một image cơ sở phù hợp, ví dụ như `python:3.9-slim-buster`.
- Sao chép các tệp mã nguồn vào container.
- Cài đặt các thư viện Python cần thiết (`requirements.txt`).
- Thiết lập một `ENTRYPOINT` hoặc `CMD` để chạy DAG Airflow hoặc các script khởi động.
- Tạo một `docker-compose.yml` để định nghĩa và chạy các dịch vụ cần thiết (ví dụ: Apache Airflow, PostgreSQL).
- Cấu hình các volume để lưu trữ dữ liệu và logs của PostgreSQL một cách bền vững.
