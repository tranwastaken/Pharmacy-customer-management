# Pharmacy Customer Management

Ứng dụng web quản lý danh sách khách hàng cho cửa hàng thuốc, xây dựng bằng Node.js + Express kết nối với Microsoft SQL Server. Đây là đồ án BTL2 môn Hệ Cơ Sở Dữ Liệu.

---

## Tính năng

- **Quản lý khách hàng:** thêm, sửa, xóa với validate dữ liệu (SĐT trùng, tuổi tối thiểu 16, ngày sinh hợp lệ)
- **Tìm kiếm & sắp xếp:** tìm theo tên, SĐT, email
- **Điểm tích lũy:** xem điểm tích lũy của từng khách hàng theo SĐT
- **Khách hàng trung thành:** lọc theo tổng giá trị mua và số lần mua trong khoảng thời gian
- **Doanh thu:** so sánh doanh thu thực và doanh thu tiềm năng theo tháng/năm
- **Gọi Stored Procedures & Functions** từ SQL Server trực tiếp qua ứng dụng

---

## Cấu trúc thư mục

```
BE_DBS/
├── src/
│   ├── config/
│   │   └── db.js                  # Cấu hình kết nối SQL Server
│   ├── controllers/
│   │   └── customerController.js  # Xử lý logic CRUD & báo cáo
│   ├── routes/
│   │   └── customerRouter.js      # Định nghĩa các route
│   └── views/
│       ├── layouts/
│       │   └── main.ejs           # Layout chính
│       ├── customer-form.ejs      # Form thêm/sửa khách hàng
│       ├── customer-list.ejs      # Danh sách khách hàng
│       ├── dashboard.ejs          # Trang chủ
│       ├── list.ejs               # Danh sách + điểm tích lũy
│       ├── list-one-on-one.ejs    # Danh sách với tìm kiếm & sắp xếp
│       └── revenue.ejs            # Báo cáo doanh thu
├── .env                           # Biến môi trường (không commit)
├── .gitignore
├── package.json
├── package-lock.json
├── README.md
└── test-connect.js                # Script kiểm tra kết nối DB
```

---

## Hướng dẫn cài đặt & chạy

### Yêu cầu
- Node.js >= 16
- SQL Server (MSSQL) đang chạy ở localhost
- Database `BTL_Restore1` đã được restore

### Cài đặt

```bash
# Clone repo
git clone https://github.com/tranwastaken/Pharmacy-customer-management.git

# Di chuyển vào thư mục
cd Pharmacy-customer-management

# Cài dependencies
npm install
```

### Cấu hình

Tạo file `.env` ở thư mục gốc với nội dung:

```env
DB_SERVER=localhost\SQLEXPRESS
DB_NAME=BTL_Restore1
DB_USER=nodeuser
DB_PASSWORD=your_password
PORT=3000
```

### Chạy ứng dụng

```bash
npm start
```

Truy cập tại: `http://localhost:3000`

### Kiểm tra kết nối database

```bash
node test-connect.js
```

---

## Công nghệ sử dụng

- **Runtime:** Node.js
- **Framework:** Express.js
- **Template engine:** EJS
- **Database:** Microsoft SQL Server
- **Driver:** mssql, msnodesqlv8

---

## Thành viên nhóm

| Họ và tên |
|-----------|
| Dương Thị Bảo Trân |
| Huỳnh Lê Phương Linh |
| Phan Cao Thiên Kiều |
