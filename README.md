# TeleChat Project

Dự án TeleChat là một ứng dụng nhắn tin thời gian thực hiện đại, được xây dựng với mục tiêu cung cấp trải nghiệm mượt mà và giao diện đẹp mắt.
Tập trung vào tốc độ, tính bảo mật và trải nghiệm người dùng mượt mà. Dự án được xây dựng theo mô hình Client-Server sử dụng WebSocket để đảm bảo độ trễ thấp nhất.

🚀 Tính Năng Chính
Dựa trên yêu cầu hiện đại của các ứng dụng nhắn tin, TeleChat cung cấp:

💬 Nhắn tin cơ bản & Nâng cao
Chat 1-1 & Group Chat: Trò chuyện riêng tư hoặc tạo nhóm chat không giới hạn.

Lịch sử tin nhắn: Lưu trữ và đồng bộ tin nhắn qua PostgreSQL.

Gửi tệp tin: Hỗ trợ chia sẻ file đa phương tiện (ảnh, tài liệu).

Tương tác tin nhắn: Thả cảm xúc (Message Reactions) cho từng tin nhắn.

⚡ Trải nghiệm Thời gian thực (Real-time)
WebSocket: Nhận tin nhắn ngay lập tức không cần tải lại trang.

Typing Indicator: Hiển thị trạng thái "đang gõ..." của đối phương.

Online Status: Biết khi nào bạn bè đang hoạt động.

Read Receipts: Hiển thị trạng thái "Đã xem" tin nhắn.

🔒 Bảo mật (Security)
Xác thực: Sử dụng JWT (JSON Web Tokens) an toàn.

Mã hóa: Tích hợp CryptoJS để mã hóa dữ liệu phía Client.

🛠 Công Nghệ Sử Dụng

### Backend
- **Ngôn ngữ:** Python
- **Framework:** FastAPI
- **Database:** PostgreSQL (sử dụng SQLAlchemy & AsyncPG)
- **Websocket:** Hỗ trợ nhắn tin thời gian thực

### Frontend
- **Framework:** React (Vite)
- **Styling:** TailwindCSS
- **Ngôn ngữ:** TypeScript
- **CryptoJS:** Thư viện mã hóa

🛠 Cấu Trúc Thư Mục

```
TeleChat/
├── Backend/                # Mã nguồn Backend (FastAPI)
│   ├── app/                # Logic chính của ứng dụng
│   │   ├── api/            # API Endpoints
│   │   ├── core/           # Cấu hình core (DB, Security)
│   │   ├── models/         # Database Models
│   │   ├── schemas/        # Pydantic Schemas (DTOs)
│   │   └── services/       # Business Logic
│   ├── main.py             # Entry point của Backend
│   ├── pyproject.toml      # Quản lý dependencies Poerty/UV
│   └── ...
├── Frontend/               # Mã nguồn Frontend (React + Vite)
│   ├── src/                # Source code React
│   │   ├── components/     # UI Components tái sử dụng
│   │   ├── pages/          # Các trang chính của ứng dụng
│   │   ├── services/       # API Calls & Services
│   │   ├── hooks/          # Custom Hooks
│   │   ├── contexts/       # React Contexts (Global State)
│   │   ├── utils/          # Utility functions
│   │   └── types/          # TypeScript Types/Interfaces
│   ├── public/             # Static assets
│   ├── package.json        # Quản lý dependencies
│   └── ...
├── DataBase/               # Scripts và cấu hình Database
│   └── init_db.sh          # Script khởi tạo DB
└── README.md               # Tài liệu dự án
```

⚙️ Yêu Cầu Hệ Thống

- Python >= 3.14
- Node.js & npm (phiên bản mới nhất)
- PostgreSQL

🛠 Hướng Dẫn Cài Đặt

1. Backend Setup (cài đặt môi trường)
Di chuyển vào thư mục Backend:
cd Backend

Cài đặt các thư viện phụ thuộc (khuyến nghị sử dụng `uv` nếu có, hoặc pip):
pip install -e .

# Tạo môi trường ảo (nếu chưa có)
python -m venv venv
source venv/bin/activate  # Trên Windows: venv\Scripts\activate

# Cài đặt thư viện
pip install -e . (nếu dùng pip)
uv sync (nếu dùng trình quản lý gói uv)

Cấu hình môi trường:

Copy file .env.example thành .env (nếu có) hoặc tạo mới file .env.

Điền thông tin Database URL và Secret Key.

2. Khởi tạo cơ sở dữ liệu:

cd DataBase

```bash
./init_db.sh
```
Lưu ý: Trong dự án này chúng tôi sử dụng file init_db.sh để khởi tạo cơ sở dữ liệu bởi vì dự án được code trên Linux và dùng docker để chạy môi trường, nếu bạn muốn chạy dự án trên Windows hãy tạo một file mới và thêm các câu lệnh SQL cần thiết để tạo cơ sở dữ liệu.

3. Frontend Setup (cài đặt môi trường)

Di chuyển vào thư mục Frontend:
cd Frontend

Cài đặt dependencies:
npm install

4. Run the Application (khởi động ứng dụng)

Backend:
cd Backend
uvicorn main:app --reload

Frontend:
cd Frontend
npm run dev

Truy cập ứng dụng tại địa chỉ hiển thị trên terminal (thường là http://localhost:5173).

### Link deloy của chúng tôi
- Truy cập địa chỉ tại: https://web-chat-lemon.vercel.app/