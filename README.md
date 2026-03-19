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

4. Chạy ứng dụng (server + bot manager):

```bash
python main.py
```

Sau khi chạy, Dashboard sẽ khởi trên:

- HTTPS: `https://localhost:8443` (nếu `cert.pem` và `key.pem` có sẵn)
- HTTP: `http://localhost:8449` (nếu không có `*.pem`)

## Các chức năng chi tiết

- Dashboard:
  - Quản lý tài khoản đăng nhập (`config/.users`).
  - Chỉnh sửa và lưu `config/config.json` (JSON).
  - Thêm / sửa / xóa biến môi trường trong file `.env` (lưu bằng `KEY=VALUE`).
  - Tạo file `.env` mặc định lần đầu chạy nếu chưa tồn tại.

- Bot manager:
  - Quét thư mục `env/` để tìm các file `.env` và khởi tiến trình bot tương ứng.
  - Tránh khởi bot nếu token thiếu hoặc xác thực thất bại.
  - Tự động khởi lại bot khi file `.env` thay đổi.

## Ghi chú & Troubleshooting

- Nếu gặp lỗi liên quan `Event loop is closed`, cập nhật code để dùng kiểm tra token đồng bộ trước khi chạy `app.run_polling()` (đã áp dụng trong `telebot.py`).
- Kiểm tra kỹ đường dẫn `env/` và tên file `.env` — chương trình chỉ đọc các file bắt đầu bằng `.env` theo mặc định.
- Kiểm tra file `config/config.json` nếu bot AI cần cấu hình thêm (model, temperature,...).

## Muốn tôi làm gì tiếp theo?

- Tôi có thể: thêm ví dụ `env/.env.example`, thêm script khởi nhanh `run.sh`/`run.bat`, hoặc cập nhật README theo yêu cầu.

---

© Dự án Zalo/Telegram AI Bot Manager
