# AI_LOG.md — Khai báo sử dụng AI (Finance Planner, đồ án cá nhân PHY10615)

Mức AI: **Mức 3** (theo đề bài).


## AI hỗ trợ như thế nào

em dùng trợ lý AI (Muse) gemini, chat gpt, claude để hỗ trợ tài liệu viết hàm code theo đúng yêu cầu em đưa ra.

| Phần | AI hỗ trợ | Tôi làm |
| --- | --- | --- |
| fp1 — Prisma schema, migration, seed  | Viết schema và script seed theo đề tôi đưa | Chạy migration/seed, kiểm tra số dư 24.825.000đ trên Neon, push tag fp1 |
| fp2 — Zod schema, Server Actions CRUD, lọc theo URL | Viết schema, actions, filters, 8 unit test Zod | Chạy test, kiểm chứng lọc (tháng này + Thu = 4 giao dịch, tổng thu 16.500.000đ), push tag fp2 |
| fp3 — Better Auth, DAL `requireUser()` | Viết `auth.ts`, `auth-client.ts`, `dal.ts`, trang login/register, route handler auth, sửa actions lọc theo `userId` | Cài better-auth, tạo `BETTER_AUTH_SECRET`, đăng ký tài khoản thật, chuyển dữ liệu từ demo sang tài khoản thật, push tag fp3 |
| Giao diện (shadcn, neon cyber, gấu trúc) | Viết lại CSS/theme, component auth-card, animation gấu trúc theo ý tôi | Chạy dev server, xem và chỉnh từng chi tiết (màu, gấu, xe, cây) |
| Wishlist CRUD | Viết Zod schema, Server Actions, form/row/delete-button theo mẫu giao dịch | Kiểm tra thêm/sửa/xóa trên giao diện |
| Mốc tiết kiệm | Viết hàm thuần `savingsMilestone` và 8 unit test | Chạy test, kiểm tra thanh tiến độ wishlist |
| Biểu đồ Recharts | Viết component biểu đồ thu/chi | Cài recharts, kiểm tra biểu đồ hiển thị đúng số liệu |
| CI GitHub Actions | Viết workflow `.github/workflows/ci.yml` | Xem kết quả CI chạy trên GitHub |

## phần cải tiếng thêm make by Ân :3
10 tính năng cơ bản đc chia ra làm 7 tính năng ko trực tiếp trên database 3 cái còn lại thì có


## mô tả sơ lược 7 tính năng
- Điểm sức khỏe tài chính 0–100 + xếp hạng
- Dự báo số dư cuối tháng, cảnh báo nếu sẽ âm
- Mô phỏng "cắt X đ/tháng thì 1 năm tiết kiệm được bao nhiêu"
- So sánh thu/chi với tháng trước (% tăng/giảm)
- Top 5 khoản chi lớn nhất tháng
- Streak ghi chép + huy hiệu
- Gợi ý tiết kiệm (chỉ danh mục chi nhiều nhất, gợi ý cắt 10%)

## mô tả sơ lược 3 tính năng cần database
- Ngân sách danh mục (đặt hạn mức/tháng, cảnh báo 80%/vượt)
- Hóa đơn định kỳ (thêm mẫu + nút 1 click tạo hết giao dịch tháng này, không bị trùng)
- Wishlist có deadline (chọn ngày mục tiêu, hiện còn bao nhiêu ngày + cần tiết kiệm bao nhiêu/ngày)