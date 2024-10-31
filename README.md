# Question-1

Để thiết kế một hệ thống phản hồi truy vấn của người dùng về trạng thái giao hàng của đơn hàng thì có thể xây dựng 1 hệ thống với các thành phần chính như sau:
##	Kiến trúc hệ thống
-	Giao diện người dùng (UI): có thể là web hoặc là ứng dụng chạy trên ứng dụng di động để cho phép người dùng theo dõi và truy vấn đơn hàng của họ
-	Máy chủ (server): Nhận và quản lí yêu cầu, kết nối với database để truy xuất thông tin.
-	Cơ sở dữ liệu (database): lưu trữ và truy xuất thông tin về đơn hàng.
-	Liên kết với bên thứ 3: như là API của các đơn vị dịch vụ giao hàng để truy xuất thông tin về kiện hàng khi giao.
##	Các tính năng của hệ thống
-	Các chức năng như các sàn giao dịch điện tử khác: đặt, cho đơn hàng vào giỏ hàng ảo, xem thông tin về hàng hóa,…
-	Lịch sử giao hàng, thời gian giao hàng,… (có thể tích hợp AI để dự đoán thời gian giao hàng)
-	Support để hỗ trợ khách hàng khi có vấn đề ( có thể tích hợp chatbot tại đây).
-	Thông báo đơn hàng: thông báo đơn hàng qua sms/ thông báo app hoặc có thể là email. Cho phép người dùng có thể theo dõi trạng thái đơn hàng hiện tại.
##	Công nghệ đề xuất
-	Frontend: React, Angular hoặc Vue.js.
-	Backend: Node.js, Django hoặc Ruby , radius server cho máy chủ
-	Database: MySQL, PostgreSQL hoặc MongoDB 
-	API: RESTful API hoặc GraphQL 
-	Kết hợp thêm xác thực 2 lớp  (2FA) và mã hóa dữ liệu quan trọng của người dùng.
-	Sử dụng thêm các kĩ thuật Load balancing và Caching để phân phối lưu lượng truy cập tránh quá tải và tăng tốc độ truy xuất dữ liệu.
##	Hệ thống database
-	Một hệ thống database đơn giản đề xuất như sau bao gồm user, product, order, delivery. Cụ thể như sau:
 ![image](https://github.com/user-attachments/assets/65223939-7ea1-4211-98e2-1c7588e707bd)
 
 
 
![image](https://github.com/user-attachments/assets/31b4a01a-1517-4a49-858f-01e673b2b590)
![image](https://github.com/user-attachments/assets/0999ae87-a0bc-4c09-8b43-4c017c69ff71)
![image](https://github.com/user-attachments/assets/2aebf7e4-268c-47d9-b7bf-60829f58ee5d)

 
 
 
-	Từ đó, ta có thể truy xuất thông tin đơn hàng bằng cách sau khi liên kết hết các bảng bằng JOIN thì truy xuất bằng các câu lệnh WHERE hoặc LEFT JOIN, … để hệ thống có thể truy xuất thông tin đơn hàng.
5.	Hệ thống chatbot hỗ trợ khách hàng.
-	Ta cần xây dựng thêm một hệ thống chatbot để hỗ trợ khách hàng trong việc nếu không truy vấn được dữ liệu về trạng thái vận chuyển đơn hàng.
-	Xây dựng chatbot để có thể hỗ trợ về các câu hỏi như: 
o	Kiểm tra trạng thái đơn hàng.
o	Xem chi tiết sản phẩm trong đơn hàng.
o	Cập nhật trạng thái giao hàng.
…
-	Sử dụng công nghệ như NLP để chatbot có thể nhận diện và đưa ra thông tin về trạng thái mà người dùng muốn biết khi nó kết hợp với database của hệ thống. 
-	Workflow có thể như sau:
 
![image](https://github.com/user-attachments/assets/d4d9244d-e834-4422-9d88-14b3d911ccde)


