<div align="center">

# 🍳 BếpAI — Bếp Vị Nhà

### Gợi ý món ăn thông minh bằng AI, dành riêng cho khẩu vị Việt

[![Demo trực tiếp](https://img.shields.io/badge/🔗_Demo_trực_tiếp-GitHub_Pages-FF6B35?style=for-the-badge)](https://venhladamz-star.github.io/Ai_kitchen/)
[![Made with](https://img.shields.io/badge/Made_with-HTML%2FCSS%2FJS-2D9CDB?style=flat-square)](#)
[![AI Layers](https://img.shields.io/badge/AI_Fallback-6_Lớp-27AE60?style=flat-square)](#-kiến-trúc-ai-nhiều-lớp)
[![License](https://img.shields.io/badge/License-Cá_nhân%2FHọc_tập-8888AA?style=flat-square)](#-giấy-phép)

**[👉 Trải nghiệm ngay tại đây](https://venhladamz-star.github.io/Ai_kitchen/)**

</div>

---

## 📖 Giới thiệu

**BếpAI** trả lời câu hỏi muôn thuở *"Hôm nay ăn gì?"* — chỉ cần nhập nguyên liệu đang có, chọn thiết bị nấu, tâm trạng hoặc mục tiêu dinh dưỡng, AI sẽ gợi ý công thức phù hợp kèm hướng dẫn nấu chi tiết từng bước.

Toàn bộ ứng dụng chạy trong **một file HTML duy nhất**, không cần build, không cần cài đặt — mở lên là dùng được ngay.

<div align="center">

|  |  |  |
|:---:|:---:|:---:|
| 🏠 **Trang chủ** | ✨ **Gợi ý món** | 🧊 **Tủ lạnh** |
| 🛒 **Đi chợ** | 📅 **Menu tuần** | 🚴 **Đặt món** |

</div>

## ✨ Tính năng chính

- **✨ Gợi ý món ăn thông minh** — nhập nguyên liệu, dị ứng, sở thích, thiết bị nấu → AI gợi ý công thức phù hợp
- **😊 Gợi ý theo tâm trạng** — trời mưa, mệt mỏi, vui vẻ, có khách, vội vàng...
- **🧊 Quản lý tủ lạnh** — theo dõi nguyên liệu sẵn có, gợi ý món ngay từ đồ trong tủ lạnh, giảm lãng phí
- **🛒 Danh sách đi chợ tự động** — tổng hợp nguyên liệu từ công thức đã chọn, liên kết nhanh tới Tiki Fresh, GrabMart, Baemin, Shopee
- **📅 Thực đơn theo tuần** — lên kế hoạch bữa ăn nhanh (ngẫu nhiên) hoặc thông minh (bằng AI)
- **🚴 Đặt món giao tận nơi** — liên kết nhanh tới GrabFood, ShopeeFood, Baemin, Foody
- **👨‍👩‍👧 Hồ sơ gia đình** — quản lý khẩu phần & sở thích ăn uống riêng cho từng thành viên
- **🧑‍🍳 Nấu rảnh tay** — điều khiển từng bước nấu ăn bằng giọng nói ("tiếp theo", "quay lại", "đóng")
- **🔬 Phân tích dinh dưỡng** — ước tính calo, protein, fat, carb theo từng công thức, ghi vào nhật ký hằng ngày
- **⏱️ Hẹn giờ nấu ăn** — timer tích hợp ngay trong app
- **💸 Chia tiền ăn uống** — tạo mã VietQR chia đều hóa đơn cho cả nhóm
- **▶️ Video hướng dẫn** — tìm nhanh video nấu ăn liên quan tới công thức

## 🧠 Kiến trúc AI nhiều lớp

Trái tim của BếpAI là hệ thống gợi ý món ăn với **6 lớp dự phòng (fallback cluster)** — nếu một lớp bị lỗi hoặc hết quota, hệ thống tự động chuyển sang lớp kế tiếp mà người dùng không hề hay biết. Mỗi kết quả trả về đều gắn **badge nguồn** để minh bạch AI nào đã tạo ra gợi ý đó.

<div align="center">

| Lớp | Nguồn | Vai trò |
|:---:|:---|:---|
| `0` | ✨ **Google Gemini** | AI chính — tốc độ cao, chất lượng tốt nhất |
| `1` | 🌐 **OpenRouter** | Cluster nhiều model miễn phí, tự xoay vòng khi lỗi |
| `1.5` | 🐋 **OrcaRouter** | Cluster dự phòng bổ sung, tự xoay vòng model |
| `2` | 🤖 **Mistral AI** | Dự phòng khi các lớp AI phía trên đều lỗi |
| `3` | 🛡️ **Spoonacular** | Cơ sở dữ liệu công thức quốc tế |
| `4` | 📦 **Dữ liệu tĩnh nội bộ** | Fallback cuối cùng — hoạt động kể cả khi mất mạng |

</div>

> Cơ chế này đảm bảo ứng dụng **luôn phản hồi được**, ngay cả khi một hoặc nhiều nhà cung cấp AI đang gặp sự cố, hết hạn ngạch miễn phí, hoặc bị giới hạn tốc độ.

## 🚀 Bắt đầu sử dụng

### Cách 1 — Dùng ngay bản demo
Không cần cài đặt gì, mở link sau trên trình duyệt (máy tính hoặc điện thoại):

```
https://venhladamz-star.github.io/Ai_kitchen/
```

### Cách 2 — Chạy cục bộ (local)
```bash
git clone https://github.com/venhladamz-star/Ai_kitchen.git
cd Ai_kitchen
```
Mở trực tiếp file `index.html` bằng trình duyệt — không cần server, không cần build.

### Cách 3 — Tự host
Vì là file HTML/CSS/JS thuần, có thể host miễn phí trên **GitHub Pages**, **Netlify**, **Vercel**, hoặc bất kỳ static hosting nào khác.

## 🛠️ Công nghệ sử dụng

<div align="center">

![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=flat-square&logo=html5&logoColor=white)
![CSS3](https://img.shields.io/badge/CSS3-1572B6?style=flat-square&logo=css3&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=flat-square&logo=javascript&logoColor=black)

</div>

- **Frontend**: HTML/CSS/JavaScript thuần — không framework, không dependency ngoài
- **AI Providers**: Google Gemini, OpenRouter, OrcaRouter, Mistral AI
- **Dữ liệu công thức**: Spoonacular API + tập dữ liệu tĩnh nội bộ
- **Giọng nói**: Web Speech API (chế độ nấu rảnh tay)
- **Lưu trữ**: LocalStorage (tủ lạnh, nhật ký dinh dưỡng, danh sách mua sắm)
- **Thanh toán**: VietQR (tạo mã QR chia tiền)

## ⚠️ Lưu ý bảo mật API Key

File hiện tại chứa các API key (Gemini, OpenRouter, OrcaRouter, Mistral, Spoonacular) **hard-code trực tiếp trong mã nguồn phía client**. Điều này đồng nghĩa:

- 🔓 Bất kỳ ai xem source code (View Source / DevTools) đều có thể lấy được các key này
- 🚫 **Không nên** dùng key thật hoặc key trả phí khi repo ở chế độ public
- ✅ Nếu triển khai chính thức, nên chuyển các lệnh gọi API sang một **backend/proxy trung gian** để giấu key, hoặc dùng biến môi trường qua một bước build riêng

## 📄 Giấy phép

Dự án cá nhân / học tập. Cập nhật mục này nếu bạn muốn phát hành chính thức dưới một giấy phép mã nguồn mở (MIT, Apache 2.0,...).

---

<div align="center">

Made with ❤️ và 🍳 tại Việt Nam

</div>
