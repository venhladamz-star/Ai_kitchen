# 🍳 BếpAI - Gợi Ý Món Ăn Thông Minh

Ứng dụng web gợi ý món ăn bằng AI, tối ưu cho tiếng Việt. Nhập nguyên liệu đang có, chọn thiết bị nấu, tâm trạng hoặc mục tiêu dinh dưỡng — BếpAI sẽ gợi ý công thức phù hợp kèm hướng dẫn nấu chi tiết.

Toàn bộ ứng dụng nằm trong **một file HTML duy nhất** (`index.html`), không cần build hay cài đặt gì thêm.

## ✨ Tính năng chính

- 🏠 **Trang chủ** — gợi ý nhanh theo tâm trạng, thời tiết
- ✨ **Gợi ý món ăn** — nhập nguyên liệu, dị ứng, sở thích, thiết bị nấu để AI gợi ý công thức
- 🧊 **Tủ lạnh** — quản lý nguyên liệu sẵn có, gợi ý món từ đồ trong tủ lạnh
- 🛒 **Đi chợ** — danh sách mua sắm tự động từ công thức, liên kết ứng dụng đi chợ
- 📅 **Thực đơn tuần** — lên kế hoạch bữa ăn theo ngày
- 🚴 **Đặt món** — liên kết nhanh tới các app giao đồ ăn
- 👤 **Hồ sơ gia đình** — quản lý thành viên, khẩu phần, sở thích riêng từng người
- 🧑‍🍳 **Nấu rảnh tay** — chế độ điều khiển bằng giọng nói khi đang nấu
- 🔬 **Phân tích dinh dưỡng** — tính calo/protein/fat/carb theo nguyên liệu
- 💰 **Chia tiền hóa đơn** — tạo mã VietQR chia tiền ăn nhóm
- ▶️ Tìm video hướng dẫn nấu ăn liên quan

## 🧠 Kiến trúc AI nhiều lớp (Fallback Cluster)

Hệ thống gợi ý món ăn được thiết kế với **6 lớp dự phòng**, tự động chuyển sang lớp kế tiếp nếu lớp hiện tại lỗi hoặc hết quota — đảm bảo ứng dụng luôn trả về kết quả:

| Lớp | Nguồn | Ghi chú |
|-----|-------|---------|
| 0 | **Google Gemini** | AI chính, tốc độ cao |
| 1 | **OpenRouter** | Cluster nhiều model free, tự xoay vòng model |
| 1.5 | **OrcaRouter** | Cluster dự phòng thêm, tự xoay vòng model |
| 2 | **Mistral AI** | Dự phòng khi các lớp AI trên lỗi |
| 3 | **Spoonacular** | CSDL công thức quốc tế |
| 4 | **Dữ liệu tĩnh nội bộ** | Fallback cuối cùng, hoạt động offline |

Mỗi công thức trả về đều hiển thị **badge nguồn** để người dùng biết kết quả đến từ lớp nào.

## 🚀 Cách chạy

Không cần server hay cài đặt:

1. Tải file `index.html`
2. Mở trực tiếp bằng trình duyệt

Hoặc host tĩnh bằng GitHub Pages, Netlify, Vercel,... vì đây là file HTML/CSS/JS thuần.

## ⚠️ Lưu ý về API Key

File hiện chứa các API key (Google Gemini, OpenRouter, OrcaRouter, Mistral, Spoonacular) **hard-code trực tiếp trong mã nguồn phía client**. Điều này có nghĩa là:

- Bất kỳ ai xem source code (View Source / DevTools) đều có thể lấy được các key này
- **Không nên** dùng key thật/trả phí trong file public trên GitHub
- Nếu public repo, cân nhắc chuyển các lệnh gọi API sang một backend/proxy để giấu key, hoặc dùng biến môi trường qua một bước build

## 🛠️ Công nghệ sử dụng

- HTML/CSS/JavaScript thuần (không framework)
- Web Speech API (chế độ nấu rảnh tay bằng giọng nói)
- LocalStorage (lưu tủ lạnh, nhật ký dinh dưỡng, v.v.)
- Google Gemini API, OpenRouter, OrcaRouter, Mistral AI, Spoonacular API
- VietQR (tạo mã QR chia tiền)

## 📄 Giấy phép

Dự án cá nhân/học tập. Cập nhật giấy phép nếu bạn muốn public chính thức.
