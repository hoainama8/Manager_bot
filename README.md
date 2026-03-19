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

## Yêu cầu

- Python 3.10+ (hoặc phiên bản tương thích với các thư viện trong `requirements.txt`)
- Các gói trong `requirements.txt` (cài qua `pip`)

## Cách tải từ GitHub và chạy

1. Clone repo:

```bash
git clone <repository-url>
cd <repo-folder>
```

2. Tạo virtual environment và cài dependencies:

```bash
python -m venv .venv
source .venv/bin/activate    # Linux/macOS
.
.venv\Scripts\Activate.ps1  # Windows PowerShell
pip install -r requirements.txt
```

3. Cấu hình token

- Tạo/ sửa file `env/.env` hoặc các file bắt đầu bằng `.env` trong thư mục `env/`.
- Ví dụ nội dung tối thiểu của `env/.env`:

```
ZALO_BOT_TOKEN=
TELE_TOKEN=
FB_TOKEN=
GEMINI_API_KEY=
```

Điền token tương ứng nếu muốn khởi bot đó. Nếu để trống thì bot sẽ không khởi.



---

© Dự án Zalo/Telegram AI Bot Manager
