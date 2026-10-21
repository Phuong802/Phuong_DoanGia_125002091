# NHẬT KÝ PROMPT ENGINEERING (VIBE CODING LOG)

- **Họ và tên:** Đoàn Gia Phương
- **MSSV:** 125002091
- **Tên đề tài Website:** Shop hoa của Phương – Tiệm hoa tươi giao trong ngày
- **Công cụ AI đã sử dụng:** Claude (Anthropic)

## 1. Yêu cầu ban đầu (System/Initial Prompt)

> Prompt tổng quan ban đầu dùng để khởi tạo khung website.

Mình dán toàn bộ đề bài cho AI, gồm các yêu cầu kỹ thuật:
- Semantic HTML5 tối thiểu 5 thẻ: `<header>`, `<nav>`, `<main>`, `<section>`/`<article>`, `<footer>`.
- CSS Variables trong `:root` để quản lý màu, font, spacing; layout bằng Flexbox hoặc Grid.
- Tích hợp Animate.css và AOS, kèm hiệu ứng `:hover`, `:focus` tự viết cho nút và card.

Sau đó mình yêu cầu ngắn gọn: **"thiết kế một website chủ đề bán hoa"**.

## 2. Quá trình tinh chỉnh & Giải quyết sự cố (Iteration)

### Lần 1: Dựng khung Semantic HTML & CSS Variable

- **Prompt đã dùng:** Thiết kế một website chủ đề bán hoa, đáp ứng đủ yêu cầu Semantic HTML5, CSS Variables, Flexbox/Grid, Animate.css và AOS như đề bài.
- **Kết quả AI tạo ra:** AI tạo 2 file `index.html` và `style.css` cho tiệm hoa "Hoa Tơ", gồm header + nav, hero, 4 card sản phẩm, phần dịch vụ, câu chuyện, form liên hệ và footer. Có khối `:root` với biến màu (`--plum`, `--peony`, `--sage`...), font và spacing.
- **Nhận xét & Tinh chỉnh của SV:**kiểm tra xem AI có dùng đúng `<header>`, `<nav>`, `<main>`, `<section>`, `<article>`, `<footer>` không; có dùng `<div>` vô nghĩa chỗ nào không; CSS Variables đã được dùng thật hay chỉ khai báo.

### Lần 2: Tích hợp thư viện Animate.css & AOS

-- **Prompt đã dùng:** Không có prompt riêng. Yêu cầu tích hợp Animate.css và AOS nằm sẵn trong đề bài ở prompt ban đầu, nên AI tích hợp luôn ở lần 1. Mình chỉ mở trình duyệt để kiểm tra hiệu ứng có chạy mượt không.
- **Kết quả AI tạo ra:** Animate.css áp dụng cho tiêu đề hero (`fadeInUp`), đoạn mô tả, nhóm nút và nút CTA (`pulse`). AOS áp dụng cho các section bên dưới (`fade-up`, `zoom-in`, `fade-right/left`), cấu hình `once: true` để chỉ chạy một lần.
- **Thách thức gặp phải:**
- **Cách sửa prompt (Debug prompt):**  "AOS không chạy, kiểm tra xem đã gọi AOS.init() chưa và link CDN có đúng không".

### Lần 3: Chia website thành nhiều commit

- **Prompt đã dùng:** "bài làm ít nhất 10 commit"
- **Kết quả AI tạo ra:** AI chia website thành 12 giai đoạn (khung HTML, CSS variables, header, hero, card, hover, section, form + footer, Animate.css, AOS, responsive), mỗi giai đoạn là một thư mục `commit_01` đến `commit_12` kèm message commit gợi ý.
- **Nhận xét & Tinh chỉnh của SV:** 


## ## 3. Đánh giá cá nhân về quá trình Vibe Coding

- **AI đã giúp bạn tiết kiệm thời gian ở phần nào nhất?**
  AI giúp mình tiết kiệm thời gian nhất ở phần dựng khung HTML/CSS ban đầu. Chỉ với một prompt có đề bài, mình đã có sẵn cấu trúc semantic, bảng màu bằng CSS Variables và nội dung mẫu cho website. AI cũng giúp mình chia code thành nhiều bước để làm đủ số commit mà đề bài yêu cầu.

- **Bài học rút ra khi đặt câu hỏi (Prompt) cho AI trong thiết kế web?**
  Khi mình nêu rõ yêu cầu kỹ thuật cụ thể (tên thẻ, thư viện, kiểu layout) thì kết quả đúng ý hơn nhiều. Mình cũng rút ra rằng phải tự kiểm tra lại code AI viết thay vì tin hoàn toàn, và nên yêu cầu sửa từng phần nhỏ thay vì bắt AI viết lại cả trang.
