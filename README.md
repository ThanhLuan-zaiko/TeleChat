# TeleChat Project

Dự án TeleChat là một ứng dụng nhắn tin thời gian thực hiện đại, được xây dựng với mục tiêu cung cấp trải nghiệm mượt mà và giao diện đẹp mắt.

## Công Nghệ Sử Dụng

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

## Cấu Trúc Thư Mục

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

## Yêu Cầu Hệ Thống

- Python >= 3.14
- Node.js & npm (phiên bản mới nhất)
- PostgreSQL

## Hướng Dẫn Cài Đặt

### 1. Backend

Di chuyển vào thư mục Backend:
```bash
cd Backend
```

Cài đặt các thư viện phụ thuộc (khuyến nghị sử dụng `uv` nếu có, hoặc pip):
```bash
# Nếu dùng pip
pip install -e .
```

Tạo file `.env` và cấu hình các biến môi trường cần thiết (tham khảo code hoặc file mẫu nếu có).

### 2. Frontend

Di chuyển vào thư mục Frontend:
```bash
cd Frontend
```

Cài đặt dependencies:
```bash
npm install
```

### 3. Database

Khởi tạo cơ sở dữ liệu (đảm bảo PostgreSQL đã chạy):
```bash
# Từ thư mục gốc hoặc thư mục chứ script
./DataBase/init_db.sh
```

## Hướng Dẫn Chạy Ứng Dụng

### Khởi chạy Backend
```bash
cd Backend
# Chạy với uvicorn (hoặc lệnh tương tự trong script nếu có)
uvicorn main:app --reload
```

### Khởi chạy Frontend
```bash
cd Frontend
npm run dev
```

Truy cập ứng dụng tại địa chỉ hiển thị trên terminal (thường là `http://localhost:5173`).
