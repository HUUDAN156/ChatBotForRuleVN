HƯỚNG DẪN CÀI ĐẶT VÀ CHẠY ỨNG DỤNG CHATBOT LUẬT VIỆT NAM

1. Yêu cầu hệ thống:
- Node.js phiên bản 18 trở lên
- MySQL Server
- Git

2. Các bước cài đặt:

a. Clone repository (Nếu đã có source thì bỏ qua bước này):
bash
git clone https://gitlab.duthu.net/S52000642/52000642_52000747.git
cd DACNTT_ChatBotForRuleVN

b. Cài đặt các dependencies:

c. Cấu hình database:
- Tạo database MySQL mới tên "chatbot_v2"
- Import file SQL từ src/config/chatbox.sql vào database vừa tạo
- Cập nhật thông tin kết nối database trong file src/config/database.js

d. Cấu hình biến môi trường (Nếu đã có source thì bỏ qua bước này):
- Tạo file .env trong thư mục gốc
- Thêm các biến môi trường sau:

================
host = localhost
port = 3000

GOOGLE_CLIENT_ID=42832101393-bovnvb80f3ovo4ejphpqng0e55rdt5q6.apps.googleusercontent.com
GOOGLE_CLIENT_SECRET=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

MAIL_HOST=smtp.gmail.com
MAIL_PORT=587
MAIL_USERNAME=vinhdatgg07@gmail.com
MAIL_PASSWORD=znqekblximnppqno
MAIL_FROM_ADDRESS=vinhdatgg07@gmail.com

JWT_SECRET=your-super-secret-key
JWT_EXPIRES_IN=24h

APP_URL=http://localhost:3000

GOOGLE_CALLBACK_URL=http://localhost:3000/auth/google/callback

GOOGLE_API_KEY=AIzaSyAu1x03jVf1QExJOf72vLpm-vpBnD_Uvog
PINECONE_API_KEY=pcsk_22uVWy_CFCtmBjGR5gtgWymdMbf7t6DRr7sY1bxXEY5jVHw273v4LtxmKYTQujtEw1Rybm

VNPAY_TMN_CODE=PWY1QUTB
VNPAY_HASH_SECRET=MWD9D1LUT12WZ5WWF5ZOW9N7REN9T0R5
VNPAY_URL=https://sandbox.vnpayment.vn/paymentv2/vpcpay.html
VNPAY_API=https://sandbox.vnpayment.vn/merchant_webapi/api/transaction
VNPAY_RETURN_URL=http://localhost:3000/api/payment/vnpay_return
================

3. Chạy ứng dụng:

a. Chạy trong môi trường development:

npm run dev

b. Chạy trong môi trường production:

npm start

Ứng dụng sẽ chạy tại http://localhost:3000

4. Sử dụng Docker (tùy chọn):

a. Build Docker image:

docker build -t chatbot-law .

b. Chạy container:

docker run -p 3000:3000 chatbot-law

5. Các tính năng chính:
- Đăng nhập/đăng ký tài khoản
- Chat với bot về luật Việt Nam
- Tìm kiếm văn bản luật
- Quản lý gói dịch vụ
- Thanh toán qua VNPAY
- Quản lý profile người dùng
- Dashboard admin

6. Lưu ý:
- Đảm bảo MySQL Server đang chạy trước khi khởi động ứng dụng
- Kiểm tra các thông tin kết nối trong file .env
- Cấp đủ quyền cho database user
- Backup database thường xuyên





