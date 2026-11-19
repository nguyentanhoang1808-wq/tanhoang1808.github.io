# Data & Business — blog nhiều bài trên GitHub Pages

Đây là bộ website tĩnh, sử dụng HTML/CSS/JavaScript, có **trang chủ**, **thư viện bài viết**, **trang giới thiệu** và **một trang riêng cho từng bài**. Phong cách editorial/consulting, minh họa tranh chì theo nội dung. Không phải website chính thức của McKinsey và không sử dụng thương hiệu của họ.

## Xem nhanh

Mở `site/index.html` trên trình duyệt, sau đó chọn **Bài viết** hoặc bài nổi bật. Các file HTML có thể mở trực tiếp, không cần máy chủ.

## Đưa lên GitHub Pages (nhanh nhất)

1. Tạo một repository, chẳng hạn `data-notes`.
2. Upload **toàn bộ nội dung bên trong thư mục `site/`** lên thư mục gốc của repository: `index.html`, `posts.html`, `about.html`, `styles.css`, `script.js`, `posts/`, `assets/`.
3. Vào **Settings → Pages → Deploy from a branch**, chọn `main`, chọn `/(root)` rồi Save.
4. Trang chủ: `https://YOUR-USERNAME.github.io/data-notes/`.
5. Bài viết đã có URL riêng: `https://YOUR-USERNAME.github.io/data-notes/posts/lam-data-co-nhung-huong-di-nao.html`.

> Không upload chỉ mỗi `index.html`. Site có nhiều trang nên cần giữ nguyên cấu trúc file và thư mục.

## Thêm bài viết mới

1. Cài Python 3 (trên máy của bạn).
2. Cài thư viện tạo site một lần: `pip install mistune beautifulsoup4`.
3. Tạo file mới, ví dụ `articles/sql-data-modelling.md`, với format:

```markdown
---
title: "SQL và Data Modelling trong công việc BI"
slug: "sql-data-modelling"
category: "Data & BI"
excerpt: "Mô tả ngắn về bài viết."
cover: "assets/article-library-sketch.webp"
---

# SQL và Data Modelling trong công việc BI

Nội dung bài viết của bạn.

## Một mục nhỏ

Đoạn văn tiếp theo.
```

4. Tại thư mục dự án, chạy: `python build.py`.
5. Upload lại **nội dung thư mục `site/`** lên GitHub. Trang chủ, trang danh sách và trang bài viết riêng sẽ được cập nhật tự động.

Để thêm tranh chì vào bài mới, lưu ảnh vào `site/assets/` rồi trỏ `cover:` tới ảnh tương ứng. `build.py` không yêu cầu truy cập Internet và không cần tải bất kỳ tài nguyên nào khi đọc website.

## Cấu trúc

```text
data-insights-blog/
├── articles/                          # File Markdown gốc — mỗi file = một bài
│   └── lam-data-co-nhung-huong-di-nao.md
├── build.py                            # Render Markdown thành trang tĩnh
└── site/                               # Upload thư mục này lên GitHub Pages
    ├── index.html                      # Trang chủ
    ├── posts.html                      # Danh sách bài, lọc và tìm kiếm
    ├── about.html                      # Giới thiệu
    ├── styles.css
    ├── script.js
    ├── assets/                         # Ảnh pencil sketch
    └── posts/
        └── lam-data-co-nhung-huong-di-nao.html
```

## Chính sách nội dung

Bản mẫu chỉ **xuất bản một bài thật** là bài bạn gửi. Các thẻ bài và bộ lọc được render theo các file `.md` hiện có, không tự bịa các bài viết chưa được cung cấp. Thông tin ngày đăng và tác giả chưa được thêm vào vì bạn chưa cung cấp.
