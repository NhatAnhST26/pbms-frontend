# PBMS — Parking Building Management System (Frontend)

Giao diện người dùng cho hệ thống quản lý bãi đỗ xe nhiều tầng: theo dõi chỗ trống
theo thời gian thực, đặt chỗ trước, vé tháng, và check-in/check-out bằng mã QR.

🔗 **Live demo:** https://pbms-dev.vercel.app/

## Về dự án

Đồ án môn học tại Đại học FPT — nhóm 6 thành viên.
Hệ thống phục vụ 5 nhóm người dùng: Admin, Manager, Staff, Customer và Guest.

> Đây là repo **chỉ chứa phần frontend**, tách ra từ repo monorepo của nhóm.
> Lịch sử commit được giữ nguyên cho riêng thư mục frontend.

## Phần tôi phụ trách

<!-- Liệt kê các màn hình/tính năng tự code ở đây -->
- [Liệt kê các màn hình/tính năng tôi tự code]
- Biên soạn tài liệu đặc tả yêu cầu (SRS) của dự án

**Đóng góp:** 87/188 commit trên repo này (~6.800 dòng thêm mới) —
xem [danh sách commit của tôi](https://github.com/NhatAnhST26/pbms-frontend/commits?author=NhatAnhST26).

## Công nghệ

- **ReactJS 19** + React Router 7
- **Tailwind CSS 4**
- **Vite** (dev server chạy HTTPS qua mkcert — cần cho camera quét QR)
- JavaScript (ES modules)
- axios · lucide-react · sonner · html5-qrcode · qrcode.react

## Tính năng chính

| Nhóm người dùng | Màn hình |
|---|---|
| **Guest** | Xem chỗ trống, bảng giá, thông tin bãi xe |
| **Customer** | Đặt chỗ, vé tháng, xe đang gửi, thanh toán, hồ sơ cá nhân |
| **Staff** | Check-in/check-out, tra cứu vé bằng QR, xem trước phí, tất toán tiền mặt |
| **Manager** | Quản lý tầng/khu/chỗ đỗ/cổng, loại xe, quy tắc giá, báo cáo |
| **Admin** | Quản lý người dùng, nhật ký kiểm toán, hoàn tiền, sự cố |
| **Kiosk** | Màn hình cổng tự động quét QR cho xe vào/ra |

## Chạy thử

```bash
npm install
cp .env.example .env   # điền config
npm run dev            # HTTPS tại https://localhost:5173
npm run dev:http       # hoặc HTTP nếu không cần camera
```

Frontend gọi API qua `/api`, được proxy sang backend ở `http://localhost:5000`
(cấu hình trong [vite.config.js](vite.config.js)). Backend nằm ở repo riêng của nhóm.

## Cấu trúc thư mục

```
src/
├── api/          # lớp gọi API (axios instance + interceptor gắn token)
├── components/   # component dùng chung (ui/, parking/)
├── context/      # React context (auth, ...)
├── hooks/        # custom hooks
├── layouts/      # layout theo vai trò người dùng
├── lib/          # tiện ích
└── pages/        # màn hình, chia theo vai trò: admin/ manager/ staff/ user/ guest/ kiosk/
```

## Ảnh màn hình

<!-- Bỏ ảnh vào docs/screenshots/ rồi bỏ comment các dòng dưới -->
<!-- ![Trang chủ](docs/screenshots/01-home.png) -->
<!-- ![Đặt chỗ](docs/screenshots/02-reserve.png) -->
<!-- ![Màn hình Staff](docs/screenshots/03-staff.png) -->
<!-- ![Báo cáo Manager](docs/screenshots/04-reports.png) -->
