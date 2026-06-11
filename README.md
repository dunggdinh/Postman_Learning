# BÁO CÁO KIỂM THỬ API

**Tên Dự Án:** API Testing with Postman

**Ngày Kiểm Thử:** [2/6/2026]

---

# 1. Mục Tiêu Kiểm Thử

Sử dụng công cụ Postman để thực hiện kiểm thử các API RESTful, đánh giá khả năng phản hồi của hệ thống thông qua các phương thức GET, POST, PUT và DELETE.

---

# 2. Môi Trường Kiểm Thử

- Công cụ: Postman
- API sử dụng: JSONPlaceholder
- URL gốc:

```text
https://jsonplaceholder.typicode.com
```

---

# 3. Phương Pháp Kiểm Thử

- Kiểm thử thủ công bằng Postman.
- Kiểm thử tự động bằng Test Script.
- Kiểm tra:
  - HTTP Status Code
  - Response Body
  - Thời gian phản hồi
  - Kết quả trả về của API

---

# 4. Kịch Bản Kiểm Thử

## Kịch Bản Kiểm Thử Lần 1

### Tên Kịch Bản

Lấy danh sách người dùng

### Mục Đích

Kiểm tra API có trả về danh sách người dùng hay không.

### Phương Thức HTTP

```http
GET
```

### URL

```http
https://jsonplaceholder.typicode.com/users
```

### Kết Quả Mong Đợi

- Trả về HTTP Status Code 200.
- Trả về danh sách người dùng dưới dạng JSON.

### Kết Quả Thực Tế

- API trả về thành công.
- Danh sách người dùng được hiển thị đúng định dạng JSON.

### Trạng Thái

Thành công

### Kiểm thử

<img width="1920" height="1080" alt="Test_1" src="https://github.com/user-attachments/assets/ca2c2b49-53d4-4fbc-bcda-8adfbbb30969" />

---

## Kịch Bản Kiểm Thử Lần 2

### Tên Kịch Bản

Lấy thông tin người dùng theo ID

### Mục Đích

Kiểm tra khả năng truy xuất dữ liệu của một người dùng cụ thể.

### Phương Thức HTTP

```http
GET
```

### URL

```http
https://jsonplaceholder.typicode.com/users/1
```

### Kết Quả Mong Đợi

- Status Code = 200
- Trả về thông tin người dùng có ID = 1

### Kết Quả Thực Tế

```json
{
  "id": 1,
  "name": "Leanne Graham"
}
```

### Trạng Thái

Thành công

### Kiểm thử

<img width="1920" height="1080" alt="Test_2" src="https://github.com/user-attachments/assets/1bc4b9ea-0f68-4bfc-87bf-96a994d1e04a" />

---

## Kịch Bản Kiểm Thử Lần 3

### Tên Kịch Bản

Tạo mới người dùng

### Mục Đích

Kiểm tra API xử lý yêu cầu POST.

### Phương Thức HTTP

```http
POST
```

### URL

```http
https://jsonplaceholder.typicode.com/users
```

### Request Body

```json
{
  "name": "Dung",
  "email": "lmao@example.com"
}
```

### Kết Quả Mong Đợi

- Status Code = 201 hoặc 200
- Trả về dữ liệu vừa được tạo

### Kết Quả Thực Tế

```json
{
  "name": "Dung",
  "email": "lmao@example.com",
  "id": 11
}
```

### Trạng Thái

Thành công

### Kiểm thử

<img width="1920" height="1080" alt="Test_3" src="https://github.com/user-attachments/assets/870d3769-c0b9-4b3f-88bb-7d3cd6115d13" />

---

## Kịch Bản Kiểm Thử Lần 4

### Tên Kịch Bản

Cập nhật thông tin người dùng

### Mục Đích

Kiểm tra API xử lý yêu cầu PUT.

### Phương Thức HTTP

```http
PUT
```

### URL

```http
https://jsonplaceholder.typicode.com/users/1
```

### Request Body

```json
{
  "name": "Dung Updated",
  "email": "updated@example.com"
}
```

### Kết Quả Mong Đợi

Trả về dữ liệu đã được cập nhật.

### Kết Quả Thực Tế

API trả về dữ liệu cập nhật thành công.

### Trạng Thái

Thành công

### Kiểm thử

<img width="1920" height="1080" alt="Test_4" src="https://github.com/user-attachments/assets/092e5c38-1ab3-4535-b2fb-661cc921cea5" />

---

## Kịch Bản Kiểm Thử Lần 5

### Tên Kịch Bản

Xóa người dùng

### Mục Đích

Kiểm tra API xử lý yêu cầu DELETE.

### Phương Thức HTTP

```http
DELETE
```

### URL

```http
https://jsonplaceholder.typicode.com/users/1
```

### Kết Quả Mong Đợi

Status Code = 200

### Kết Quả Thực Tế

API trả về thành công.

### Trạng Thái

Thành công

### Kiểm thử

<img width="1920" height="1080" alt="Test_5" src="https://github.com/user-attachments/assets/b22c0d59-2d4f-4d32-a382-fd26ccc5be7b" />

---

# 5. Kiểm Thử Tự Động Bằng Test Script

### Mã Kiểm Thử

```javascript
pm.test("Status code is 200", function () {
    pm.response.to.have.status(200);
});
```

### Kết Quả

```text
✓ Status code is 200
```

### Kiểm thử

<img width="1920" height="1080" alt="Automated Testing " src="https://github.com/user-attachments/assets/2de6de90-361d-4930-bab5-0e3138723e0b" />

---

# 6. Kết Quả Kiểm Thử

| Nội dung | Số lượng |
|-----------|-----------:|
| Tổng số kịch bản | 5 |
| Thành công | 5 |
| Thất bại | 0 |
| Tỷ lệ thành công | 100% |

---

# 7. Kết Luận

Qua quá trình kiểm thử bằng Postman:

- Thực hiện thành công các phương thức GET, POST, PUT và DELETE.
- Hiểu cách gửi dữ liệu JSON thông qua Request Body.
- Viết được Test Script kiểm tra Status Code.
- Hiểu cách xử lý và kiểm tra lỗi HTTP.
- Làm quen với quy trình kiểm thử API trong thực tế.

---

# Tài Liệu Đính Kèm

## Collection Postman

```text
postman/API_Test.postman_collection.json
```

## Thư Mục Hình Ảnh

```text
screenshots/
```
