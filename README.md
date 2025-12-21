<p align="center">
  <img src="telechat_banner.png" alt="TeleChat Banner" width="100%">
</p>

# 🚀 TeleChat Project

[![FastAPI](https://img.shields.io/badge/FastAPI-005571?style=for-the-badge&logo=fastapi)](https://fastapi.tiangolo.com/)
[![React](https://img.shields.io/badge/React-20232A?style=for-the-badge&logo=react&logoColor=61DAFB)](https://reactjs.org/)
[![PostgreSQL](https://img.shields.io/badge/PostgreSQL-316192?style=for-the-badge&logo=postgresql&logoColor=white)](https://www.postgresql.org/)
[![TailwindCSS](https://img.shields.io/badge/Tailwind_CSS-38B2AC?style=for-the-badge&logo=tailwind-css&logoColor=white)](https://tailwindcss.com/)
[![TypeScript](https://img.shields.io/badge/TypeScript-007ACC?style=for-the-badge&logo=typescript&logoColor=white)](https://www.typescriptlang.org/)

Dự án **TeleChat** là một ứng dụng nhắn tin thời gian thực hiện đại, được xây dựng với mục tiêu cung cấp trải nghiệm mượt mà và giao diện đẹp mắt. Tập trung vào tốc độ, tính bảo mật và trải nghiệm người dùng mượt mà. Dự án được xây dựng theo mô hình Client-Server sử dụng WebSocket để đảm bảo độ trễ thấp nhất.

---

## ✨ Tính Năng Chính

Dựa trên yêu cầu hiện đại của các ứng dụng nhắn tin, TeleChat cung cấp:

### 💬 Nhắn tin cơ bản & Nâng cao
-   **Chat 1-1 & Group Chat:** Trò chuyện riêng tư hoặc tạo nhóm chat không giới hạn.
-   **Lịch sử tin nhắn:** Lưu trữ và đồng bộ tin nhắn qua PostgreSQL.
-   **Gửi tệp tin:** Hỗ trợ chia sẻ file đa phương tiện (ảnh, tài liệu).
-   **Tương tác tin nhắn:** Thả cảm xúc (Message Reactions) cho từng tin nhắn.

### ⚡ Trải nghiệm Thời gian thực (Real-time)
-   **WebSocket:** Nhận tin nhắn ngay lập tức không cần tải lại trang.
-   **Typing Indicator:** Hiển thị trạng thái "đang gõ..." của đối phương.
-   **Online Status:** Biết khi nào bạn bè đang hoạt động.
-   **Read Receipts:** Hiển thị trạng thái "Đã xem" tin nhắn.

### 🔒 Bảo mật (Security)
-   **Xác thực:** Sử dụng JWT (JSON Web Tokens) an toàn.
-   **Mã hóa:** Tích hợp CryptoJS để mã hóa dữ liệu phía Client.

---

## 🛠 Công Nghệ Sử Dụng

### Backend
-   **Ngôn ngữ:** ![Python](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white)
-   **Framework:** ![FastAPI](https://img.shields.io/badge/FastAPI-005571?style=flat-square&logo=fastapi)
-   **Database:** ![PostgreSQL](https://img.shields.io/badge/PostgreSQL-316192?style=flat-square&logo=postgresql) (SQLAlchemy & AsyncPG)
-   **Websocket:** Nhắn tin thời gian thực.

### Frontend
-   **Framework:** ![React](https://img.shields.io/badge/React-20232A?style=flat-square&logo=react&logoColor=61DAFB) (Vite)
-   **Styling:** ![TailwindCSS](https://img.shields.io/badge/Tailwind_CSS-38B2AC?style=flat-square&logo=tailwind-css&logoColor=white)
-   **Ngôn ngữ:** ![TypeScript](https://img.shields.io/badge/TypeScript-007ACC?style=flat-square&logo=typescript&logoColor=white)
-   **CryptoJS:** Mã hóa dữ liệu.

---

## 📂 Cấu Trúc Thư Mục

```bash
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

---

## ⚙️ Yêu Cầu Hệ Thống

-   **Python** >= 3.14
-   **Node.js & npm** (mới nhất)
-   **PostgreSQL**

---

## 🚀 Hướng Dẫn Cài Đặt

### 1. Backend Setup
```bash
cd Backend
# Tạo môi trường ảo
python -m venv venv
source venv/bin/activate  # Windows: venv\Scripts\activate

# Cài đặt dependencies
pip install -e .
# Hoặc dùng uv
uv sync
```
> [!NOTE]
> Tạo file `.env` từ `.env.example` và điền `DATABASE_URL` và `SECRET_KEY`.

### 2. Khởi tạo Cơ sở dữ liệu
```bash
cd DataBase
./init_db.sh
```
> [!IMPORTANT]
> `init_db.sh` dành cho Linux/Docker. Trên Windows, hãy chạy câu lệnh SQL thủ công.

### 3. Frontend Setup
```bash
cd Frontend
npm install
```

### 4. Khởi động Ứng dụng
-   **Backend:** `uvicorn main:app --reload`
-   **Frontend:** `npm run dev`
-   **Truy cập địa chỉ:** `http://localhost:5173`

---

## 🌐 Deployment

Dự án hiện đang được triển khai tại:
👉 **[TeleChat Live Demo](https://web-chat-lemon.vercel.app/)**
