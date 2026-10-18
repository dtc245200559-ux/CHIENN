# BÀI THỰC HÀNH: TẠO BẢNG TRONG MYSQL WORKBENCH

---

## I. MỤC TIÊU
- Luyện tập và thành thạo các thao tác giao diện để tạo bảng (Table) trong **MySQL Workbench**.
- Nắm rõ cách khai báo tên trường (column), chọn kiểu dữ liệu (data type) và các thuộc tính cơ bản như **PK** (Khóa chính), **NN** (Không rỗng), **AI** (Tự động tăng).

---

## II. MÔ TẢ YÊU CẦU

Tiếp tục sử dụng CSDL `student-management` đã tạo ở bài thực hành trước. Thực hiện tạo 2 bảng dữ liệu sau:

### 1. Bảng `Class`
| Tên trường (Column Name) | Kiểu dữ liệu (Datatype) | Thuộc tính (Attributes) |
| :--- | :--- | :--- |
| `id` | `INT` | Primary Key (**PK**), Not Null (**NN**), Auto Increment (**AI**) |
| `name` | `VARCHAR(45)` hoặc `VARCHAR(255)` | Not Null (**NN**) |

### 2. Bảng `Teacher`
| Tên trường (Column Name) | Kiểu dữ liệu (Datatype) | Thuộc tính (Attributes) |
| :--- | :--- | :--- |
| `id` | `INT` | Primary Key (**PK**), Not Null (**NN**), Auto Increment (**AI**) |
| `name` | `VARCHAR(45)` hoặc `VARCHAR(255)` | Not Null (**NN**) |
| `age` | `INT` | Khuyết (cho phép NULL) |
| `country` | `VARCHAR(45)` hoặc `VARCHAR(255)` | Khuyết (cho phép NULL) |

---

## III. HƯỚNG DẪN CHI TIẾT CÁC BƯỚC THỰC HIỆN

### **Phần 1: Tạo Bảng `Class`**

* **Bước 1:** Khởi động MySQL Workbench, kết nối tới Database Server. Ở bảng điều khiển **Navigator** (cột bên trái), click chuột phải vào schema `student-management` và chọn **Create Table...**
* **Bước 2:** 
  * Tại mục **Table Name**, nhập: `Class`.
  * Tại phần bảng cấu hình các cột (**Columns**), nhập thông tin lần lượt:
    * Cột 1: **Column Name** = `id` | **Datatype** = `INT` | Tích chọn các ô **PK**, **NN**, **AI**.
    * Cột 2: **Column Name** = `name` | **Datatype** = `VARCHAR(45)` | Tích chọn ô **NN**.
* **Bước 3:** Nhấp nút **Apply** ở góc dưới bên phải. Cửa sổ hiển thị câu lệnh SQL xem trước sẽ hiện ra, nhấp **Apply** một lần nữa rồi chọn **Finish** để hoàn tất.

---

### **Phần 2: Tạo Bảng `Teacher`**

* **Bước 1:** Tiếp tục click chuột phải vào schema `student-management` ở giao diện bên trái và chọn **Create Table...**
* **Bước 2:**
  * Tại mục **Table Name**, nhập: `Teacher`.
  * Tại phần bảng cấu hình các cột (**Columns**), nhập thông tin lần lượt:
    * Cột 1: **Column Name** = `id` | **Datatype** = `INT` | Tích chọn **PK**, **NN**, **AI**.
    * Cột 2: **Column Name** = `name` | **Datatype** = `VARCHAR(45)` | Tích chọn **NN**.
    * Cột 3: **Column Name** = `age` | **Datatype** = `INT` | Không tích chọn thuộc tính bắt buộc.
    * Cột 4: **Column Name** = `country` | **Datatype** = `VARCHAR(45)` | Không tích chọn thuộc tính bắt buộc.
* **Bước 3:** Nhấp nút **Apply**, xác nhận câu lệnh SQL bằng cách chọn **Apply** và chọn **Finish**.

---

## IV. BÀI TẬP BỔ SUNG: CÂU LỆNH SQL TƯƠNG ĐƯƠNG (NẾU DÙNG SCRIPT)

Nếu không sử dụng giao diện, bạn cũng có thể mở một tab SQL Editor mới và chạy đoạn mã sau để tạo hai bảng trên:

```sql
USE `student-management`;

-- Tạo bảng Class
CREATE TABLE IF NOT EXISTS `Class` (
    `id` INT NOT NULL AUTO_INCREMENT,
    `name` VARCHAR(255) NOT NULL,
    PRIMARY KEY (`id`)
);

-- Tạo bảng Teacher
CREATE TABLE IF NOT EXISTS `Teacher` (
    `id` INT NOT NULL AUTO_INCREMENT,
    `name` VARCHAR(255) NOT NULL,
    `age` INT NULL,
    `country` VARCHAR(255) NULL,
    PRIMARY KEY (`id`)
);
```