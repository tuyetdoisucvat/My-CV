# My-CV | Portfolio cá nhân

## Tên dự án

**My-CV** là website portfolio/CV cá nhân giới thiệu Vũ Minh Hiếu, các kỹ năng, dự án và thông tin liên hệ.

## Mô tả

Đây là website tĩnh, được xây dựng trực tiếp bằng HTML và CSS. Giao diện được thiết kế responsive để hiển thị trên điện thoại, máy tính bảng và máy tính. Dự án không cần cơ sở dữ liệu, không cần cài gói JavaScript và không có bước biên dịch.

## Chức năng

- Giới thiệu cá nhân và định hướng Game Developer/Game Designer.
- Hiển thị các kỹ năng.
- Trình bày một số dự án tiêu biểu.
- Cung cấp khu vực liên hệ.
- Điều hướng đến các phần trong trang và quay lại đầu trang.
- Tương thích với các kích thước màn hình khác nhau.

## Công nghệ

- HTML5
- CSS3, Flexbox, CSS Grid và media queries
- Docker và Nginx (tùy chọn, dùng để chạy website trong container)

## Yêu cầu môi trường

Để mở trực tiếp website, chỉ cần một trình duyệt hiện đại. Để chạy server cục bộ, cần cài Python 3. Để chạy bằng container, cần Docker Engine hoặc Docker Desktop.

| Cách chạy | Yêu cầu |
| --- | --- |
| Mở trực tiếp | Trình duyệt hiện đại |
| Server cục bộ | Python 3.x |
| Docker | Docker Engine/Desktop đang hoạt động |

## Cài đặt

Clone mã nguồn và chuyển vào thư mục dự án:

```bash
git clone <URL-repository>
cd My-CV
```

Nếu đã tải mã nguồn về máy, chỉ cần mở thư mục dự án trong terminal. Thay `<URL-repository>` bằng địa chỉ repository thực tế.

## Cấu hình và tùy chỉnh

Dự án không có file cấu hình riêng hoặc biến môi trường bắt buộc. Có thể cập nhật nội dung trực tiếp trong `index.html`, bao gồm tên, phần giới thiệu, kỹ năng, dự án và liên hệ. Cập nhật giao diện trong `assets/css/styles.css`; thay ảnh trong `assets/img/` và sửa đường dẫn ảnh tương ứng trong HTML.

Trước khi công khai website, hãy kiểm tra lại nội dung mẫu, đường dẫn liên kết, email và các ảnh. Một số liên kết dự án/liên hệ hiện có thể cần được thay bằng URL thực tế.

## Chạy thử

### Windows

**Mở trực tiếp:** mở `index.html` bằng trình duyệt.

**Chạy server cục bộ bằng Python:** mở PowerShell tại thư mục dự án và chạy:

```powershell
py -m http.server 8000
```

Nếu lệnh `py` không có, thử `python -m http.server 8000`. Truy cập <http://localhost:8000>. Dừng server bằng `Ctrl+C`.

### macOS

Mở Terminal tại thư mục dự án. Mở trực tiếp `index.html` bằng trình duyệt, hoặc chạy server:

```bash
python3 -m http.server 8000
```

Truy cập <http://localhost:8000>. Dừng server bằng `Ctrl+C`.

### Linux

Mở terminal tại thư mục dự án. Mở trực tiếp `index.html` bằng trình duyệt, hoặc chạy server:

```bash
python3 -m http.server 8000
```

Truy cập <http://localhost:8000>. Dừng server bằng `Ctrl+C`.

### Docker

Cài và khởi động Docker trước. Các lệnh dưới đây phục vụ thư mục hiện tại bằng Nginx, không yêu cầu tạo Dockerfile.

**Windows PowerShell** (chạy tại thư mục dự án):

```powershell
docker run --rm --name my-cv -p 8080:80 -v "${PWD}:/usr/share/nginx/html:ro" nginx:alpine
```

**macOS/Linux** (chạy tại thư mục dự án):

```bash
docker run --rm --name my-cv -p 8080:80 -v "$PWD:/usr/share/nginx/html:ro" nginx:alpine
```

Mở <http://localhost:8080>. Container chạy ở foreground; dừng bằng `Ctrl+C`. Nếu cổng `8080` đang được sử dụng, đổi phần `8080:80` thành một cổng trống khác, ví dụ `8081:80`, rồi truy cập cổng mới.

## Thông tin liên hệ

- **Tên:** Vũ Minh Hiếu
- **Email:** [hvuminh967@gmail.com](mailto:hvuminh967@gmail.com)
- **GitHub:** [github.com/tuyetdoisucvat](https://github.com/tuyetdoisucvat)

> Hãy xác nhận email và địa chỉ GitHub ở trên trước khi phát hành; thông tin này được lấy từ nội dung hiện có trong trang.
