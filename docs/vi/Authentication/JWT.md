# Tổng quan

JWT authentication là một dạng token base authentication.
Dựa trên tiêu chuẩn Open Standard (RFC 7519).

# How does it work?

Giống với cách hoạt động của token base authentication.
Chỉ khác ở cách tạo ra token.

Token sẽ được tạo tự động có sử dụng secret key.

Khi client gửi token kèm trong server trong mỗi request, Phía server sẽ validate JWT với secret key.

![alt text](/docs/sources/JWT-work.png)

# Đặc trưng của JWT

là normal URL-safe string
chứa carries the data
Bất kì ai cũng có thể view được nội dung bên trong JWT
Được phân làm 3 thành phần, phân cách nhau bơi dấu chấm "."
Header: chuỗi base64 được generated, gọi là tokenMeta. chưa token type, và loại hashing được áp dụng cho Signature, ví dụ SHA256
Payload: còn gọi là ourDâta, là chuỗi base64, chứa các thông tin như userID, ngày hết hạn token, v.v
Signature: được tạo ra bơi hashing ở header, giúp cho server verify tokens

ref: https://roadmap.sh/guides/jwt-authentication.png
