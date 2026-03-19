# Zalo/Telegram AI Bot Manager

Ứng dụng này là một bộ quản lý chatbot tích hợp AI, cho phép khởi và quản lý nhiều bot (Zalo, Telegram) cùng cấu hình bằng các file `.env` và `config.json`.

**Tổng quan**

- Nhận yêu cầu từ người dùng (text, ảnh, video).
- Gửi dữ liệu tới module xử lý AI (Agent) rồi trả kết quả lại cho người dùng.
- Có Dashboard web để xem/sửa cấu hình và quản lý tài khoản.

## Tính năng chính

- Dashboard quản lý cấu hình và tài khoản (HTTP/HTTPS).
- Khởi nhiều tiến trình bot song song dựa trên file `.env` trong thư mục `env/`.
- Hỗ trợ token cho các dịch vụ: Zalo, Telegram, Gemini (hoặc API tương tự).
- Lưu và chỉnh sửa `config.json`, `env/.env` và `config/.users` từ Dashboard.
- Tự động khởi/khóa các bot dựa trên token hợp lệ (nếu token thiếu/không hợp lệ, tiến trình bot sẽ không chạy).

## Các loại bot ứng dụng hỗ trợ

- ZaloBot (cần `ZALO_BOT_TOKEN` trong file `.env`)
- TeleBot (cần `TELE_TOKEN` trong file `.env`)

> Lưu ý: Kiểm tra token được thực hiện trước khi khởi bot; nếu xác thực token thất bại tiến trình sẽ dừng.

## Tài khoản đăng nhập mặc định

- Username: `admin`
- Password: `admin123`





---

© Dự án Zalo/Telegram AI Bot Manager
