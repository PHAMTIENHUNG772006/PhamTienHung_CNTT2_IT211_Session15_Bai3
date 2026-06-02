Phần 1 – Phân tích logic

- Dựa vào đoạn code thì chưa có đoạn code logic để kiểm tra quyền xác thực tài khoản nên mới có thể trực tiếp vào trang "/products"
- khi không tích hợp bảo mật thì chỉ cần người dùng lên các trình duyện và gõ đường dẫn của trang mà không cần đăng nhập cũng có thể vào trang
  Phân tích logic
  Spring Boot mặc định không chặn request  
  Nếu bạn chưa cấu hình Spring Security, mọi request HTTP đến các endpoint đều được xử lý bình thường bởi các controller. Không có lớp filter nào kiểm tra quyền truy cập hay yêu cầu xác thực.

Controller trả về dữ liệu trực tiếp  
Ví dụ, bạn có một ProductController với phương thức @GetMapping("/products") trả về danh sách sản phẩm. Vì không có bảo mật, bất kỳ ai gọi URL này đều nhận được dữ liệu.

Nguyên nhân gốc rễ

Spring Boot chỉ cung cấp cơ chế khởi tạo ứng dụng web và mapping request → controller.

Bảo mật (authentication, authorization) không phải là mặc định, mà là tùy chọn thông qua Spring Security hoặc các giải pháp khác.

Khi chưa tích hợp, ứng dụng hoạt động như một REST API mở, không có rào cản truy cập.