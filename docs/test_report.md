# BÁO CÁO KIỂM THỬ TRƯỚC BÀN GIAO

## 1. Thông tin chung

| Thông tin | Chi tiết |
| --- | --- |
| Tên dự án | My-CV — Portfolio cá nhân |
| Phiên bản | v1.0 (theo `docs/RELEASENOTE.md`) |
| Ngày kiểm thử | 05/11/2026 |
| Người thực hiện | AI hỗ trợ rà soát mã nguồn |
| Người đánh giá/nghiệm thu | Chưa cung cấp |
| Phạm vi | Rà soát mã nguồn HTML/CSS, liên kết nội bộ, đường dẫn ảnh, cấu trúc repository và tài liệu hiện có |
| Ngoài phạm vi | Kiểm thử trực quan trên trình duyệt/thiết bị thật, kiểm thử tải, kiểm thử bảo mật chuyên sâu và xác nhận nội dung liên hệ với chủ sở hữu |

> **Lưu ý:** Đây là báo cáo rà soát tĩnh dựa trên mã nguồn hiện có, không phải biên bản kiểm thử thủ công trên trình duyệt. Các mục chưa có minh chứng thực thi được ghi rõ là cần cải thiện; không xem là đã kiểm thử đạt.

## 2. Quy ước trạng thái

- **Đạt:** Có đủ cơ sở xác nhận trong phạm vi kiểm tra đã thực hiện.
- **Chưa đạt:** Phát hiện lỗi cụ thể cần khắc phục trước khi bàn giao.
- **Cần cải thiện:** Chưa đủ minh chứng, mới đáp ứng một phần hoặc cần xác nhận thêm.

## 3. Bảng tổng quan trạng thái

| # | Nhóm tiêu chí | Trạng thái | Tóm tắt |
| --- | --- | --- | --- |
| 1 | Tính đúng đắn và mức độ đáp ứng yêu cầu chức năng | Cần cải thiện | Các phần chính của portfolio có trong trang; liên kết liên hệ và liên kết dự án còn lỗi/mẫu. |
| 2 | Giao diện, trải nghiệm người dùng và khả năng tương thích | Cần cải thiện | Có CSS responsive và hỗ trợ focus/reduced-motion; chưa kiểm thử hiển thị thực tế trên trình duyệt và thiết bị. |
| 3 | Khả năng vận hành, xử lý lỗi và hiệu năng cơ bản | Cần cải thiện | Trang tĩnh, không có backend; chưa có kết quả chạy trình duyệt, kiểm tra hiệu năng hoặc xử lý lỗi thực tế. |
| 4 | Bảo mật, quản lý cấu hình và dữ liệu | Đạt | Trong phạm vi rà soát mã nguồn tĩnh, không thấy backend, biểu mẫu thu thập dữ liệu, cấu hình bí mật hoặc thư viện bên thứ ba được nạp. Chưa phải kiểm thử bảo mật chuyên sâu. |
| 5 | Chất lượng mã nguồn, cấu trúc repository và tài liệu bàn giao | Chưa đạt | Cấu trúc dự án gọn và có README/release notes, nhưng phần HTML liên hệ có markup bất thường và một số nội dung/đường dẫn chưa hoàn chỉnh. |
| 6 | Khả năng triển khai, kiểm thử và cung cấp minh chứng | Cần cải thiện | README có hướng dẫn chạy cục bộ/Docker; chưa có kết quả triển khai, biên bản kiểm thử trình duyệt hoặc ảnh minh chứng được xác nhận. |

## 4. Chi tiết kiểm tra

### 4.1. Tính đúng đắn và mức độ đáp ứng yêu cầu chức năng

| Hạng mục kiểm tra | Trạng thái | Ghi chú/Minh chứng |
| --- | --- | --- |
| Trang có các phần giới thiệu, kỹ năng, dự án và liên hệ | Đạt | Các section `about`, `skills`, `projects`, `contact` có trong `index.html`. |
| Điều hướng nội bộ đến các section | Đạt | Đã đối chiếu các đích `#top`, `#about`, `#skills`, `#projects`, `#contact`; các ID tương ứng tồn tại. |
| Các ảnh đại diện và ảnh dự án được tham chiếu | Đạt | Đã kiểm tra 5 đường dẫn ảnh trong `index.html`; các tệp đều tồn tại trong `assets/img/`. |
| Liên kết email mở trình soạn thư | Chưa đạt | Liên kết email đang dùng `href="hvuminh967@gmail.com"` thay vì URI `mailto:` (`index.html`, section Liên hệ). Cần sửa và kiểm tra lại. |
| Liên kết GitHub mở đúng hồ sơ | Chưa đạt | Liên kết GitHub hiện có `href="#"`; nội dung HTML trong liên kết có các thẻ bất thường `<github>` và `<tuyetdoisucvat>`. Cần thay bằng URL hồ sơ chính xác và markup hợp lệ. |
| Liên kết “Xem chi tiết” dẫn đến dự án | Chưa đạt | 4 thẻ dự án dùng `href="#"`; hiện chưa dẫn đến trang hoặc tài liệu dự án. |
| Nội dung và thông tin cá nhân chính xác | Cần cải thiện | Chưa có xác nhận của chủ sở hữu. Cần xác minh tên, chức danh, email, URL GitHub, mô tả và hình ảnh trước khi công khai. |

### 4.2. Giao diện, trải nghiệm người dùng và khả năng tương thích

| Hạng mục kiểm tra | Trạng thái | Ghi chú/Minh chứng |
| --- | --- | --- |
| Có bố cục responsive cho màn hình nhỏ, tablet và desktop | Đạt | CSS dùng mobile-first; breakpoint tại 768px và 1280px trong `assets/css/styles.css`. |
| Bố cục danh sách dự án thích ứng theo kích thước màn hình | Đạt | CSS Grid cấu hình 1 cột mặc định, 2 cột từ 768px và 3 cột từ 1280px. |
| Menu, nút và liên kết có trạng thái tương tác cơ bản | Cần cải thiện | Có hover/focus style trong CSS; chưa thao tác kiểm chứng bằng chuột, bàn phím hoặc thiết bị cảm ứng. |
| Hỗ trợ người dùng giảm chuyển động | Đạt | CSS có media query `prefers-reduced-motion: reduce`. |
| Hiển thị và khả năng đọc trên các trình duyệt/thiết bị mục tiêu | Cần cải thiện | Chưa có kiểm thử trực quan hoặc ảnh chụp trên Chrome, Edge, Firefox, Safari hay thiết bị di động. |
| Văn bản thay thế cho hình ảnh | Cần cải thiện | Các ảnh có `alt`, nhưng nội dung alt hiện mang tính mô tả chung; cần xác nhận nội dung phù hợp với từng ảnh và mục đích ảnh. |

### 4.3. Khả năng vận hành, xử lý lỗi và hiệu năng cơ bản

| Hạng mục kiểm tra | Trạng thái | Ghi chú/Minh chứng |
| --- | --- | --- |
| Có thể phục vụ dưới dạng website tĩnh | Đạt | Dự án gồm HTML/CSS/ảnh; README hướng dẫn mở trực tiếp, dùng Python HTTP server hoặc Docker/Nginx. Chưa xác nhận các cách chạy bằng thực thi thực tế trong đợt rà soát này. |
| Tài nguyên cục bộ được tham chiếu có tồn tại | Đạt | 5/5 ảnh được tham chiếu trong HTML tồn tại; stylesheet được tổ chức tại `assets/css/styles.css`. |
| Hành vi khi thiếu ảnh, CSS hoặc mất kết nối | Cần cải thiện | Chưa thực hiện kiểm thử lỗi tài nguyên trên trình duyệt. |
| Thời gian tải và kích thước trang | Cần cải thiện | Chưa đo bằng công cụ hiệu năng; cần kiểm tra trên môi trường triển khai mục tiêu, đặc biệt với các ảnh. |
| Có xử lý lỗi phía ứng dụng | Cần cải thiện | Trang hiện là website tĩnh, không có luồng nghiệp vụ/backend để kiểm thử xử lý lỗi; chưa có thông báo lỗi hoặc kịch bản phục hồi riêng. |

### 4.4. Bảo mật, quản lý cấu hình và dữ liệu

| Hạng mục kiểm tra | Trạng thái | Ghi chú/Minh chứng |
| --- | --- | --- |
| Có thông tin bí mật hoặc thông tin xác thực trong mã nguồn được rà soát | Đạt | Không thấy khóa/token hoặc thông tin xác thực trong các tệp HTML/CSS đã xem. Đây không thay thế secret scanning toàn repository. |
| Có biểu mẫu thu thập dữ liệu hoặc gửi dữ liệu đến backend | Đạt | Không thấy form, API hoặc backend trong phạm vi trang HTML tĩnh đã rà soát. |
| Có cấu hình môi trường bắt buộc | Đạt | README nêu dự án không có biến môi trường bắt buộc. |
| Có tài nguyên/script bên thứ ba được nạp vào trang | Đạt | Trong phần `<head>` đã rà soát, trang nạp stylesheet cục bộ; không thấy script hoặc dịch vụ bên thứ ba. |
| Đã kiểm thử bảo mật chuyên sâu và quyền riêng tư khi triển khai | Cần cải thiện | Chưa quét phụ thuộc, kiểm tra cấu hình hosting/HTTPS, header bảo mật, quyền truy cập repository hoặc chính sách quyền riêng tư. |

### 4.5. Chất lượng mã nguồn, cấu trúc repository và tài liệu bàn giao

| Hạng mục kiểm tra | Trạng thái | Ghi chú/Minh chứng |
| --- | --- | --- |
| Cấu trúc tách HTML, CSS và hình ảnh | Đạt | Trang tại `index.html`; stylesheet tại `assets/css/styles.css`; hình ảnh nằm trong `assets/img/`. |
| README có mô tả dự án và hướng dẫn chạy | Đạt | `README.md` mô tả chức năng, yêu cầu môi trường, cách chạy local và Docker. |
| Có release notes cho phiên bản | Đạt | `docs/RELEASENOTE.md` ghi nhận phiên bản v1.0 và các hạn chế còn tồn tại. |
| Markup HTML hợp lệ tại khu vực liên hệ | Chưa đạt | Đoạn GitHub chứa thẻ `<github>`/`<tuyetdoisucvat>` bất thường; cần sửa và chạy HTML validator. |
| Liên kết và nội dung mẫu đã được hoàn thiện | Chưa đạt | Có 5 liên kết dùng `href="#"` (4 liên kết dự án và 1 liên kết GitHub). Một số tên/mô tả dự án cần được chủ sở hữu xác nhận. |
| Chính tả và tính nhất quán nội dung | Cần cải thiện | Cần rà soát chính tả tiếng Việt, cách viết tên/chức danh và sự nhất quán giữa tiêu đề trang, phần giới thiệu và README trước phát hành. |

### 4.6. Khả năng triển khai, kiểm thử và cung cấp minh chứng

| Hạng mục kiểm tra | Trạng thái | Ghi chú/Minh chứng |
| --- | --- | --- |
| Có hướng dẫn chạy cục bộ | Đạt | README có hướng dẫn mở trực tiếp và chạy HTTP server bằng Python trên Windows/macOS/Linux. |
| Có hướng dẫn triển khai bằng Docker | Đạt | README mô tả chạy Nginx container; chưa xác nhận lệnh Docker trên môi trường bàn giao. |
| Đã xác nhận triển khai lên môi trường đích | Cần cải thiện | Chưa cung cấp URL môi trường staging/production hoặc kết quả xác minh triển khai. |
| Có biên bản kiểm thử chức năng/giao diện thực thi | Chưa đạt | Báo cáo này ghi nhận rà soát tĩnh; chưa có test run trên trình duyệt, ma trận thiết bị hoặc kết quả tự động hóa. |
| Có ảnh chụp/minh chứng kết quả | Cần cải thiện | Chưa có ảnh chụp màn hình hoặc minh chứng triển khai được xác nhận kèm theo báo cáo. |
| Có thể tái thực hiện kiểm thử | Cần cải thiện | Cần bổ sung URL/môi trường, trình duyệt và phiên bản, thiết bị/viewport, ngày chạy và các bước kiểm thử thực tế. |

## 5. Vấn đề cần khắc phục trước bàn giao

| Mức ưu tiên | Vấn đề | Hành động đề xuất |
| --- | --- | --- |
| Cao | Liên kết email chưa dùng `mailto:`; GitHub chưa có URL đích và chứa markup bất thường. | Sửa liên kết, làm sạch HTML và kiểm tra thao tác mở email/hồ sơ. |
| Cao | Bốn liên kết dự án đang là placeholder `href="#"`. | Thay bằng đường dẫn dự án hợp lệ hoặc trình bày rõ dự án chưa có trang chi tiết, không để liên kết giả. |
| Cao | Chưa kiểm thử trực quan trên trình duyệt/thiết bị mục tiêu và chưa có minh chứng. | Chạy checklist trên ít nhất một desktop và một viewport di động; ghi trình duyệt, kết quả và ảnh chụp. |
| Trung bình | Chưa xác nhận độ chính xác của nội dung, thông tin liên hệ và hình ảnh. | Chủ sở hữu duyệt nội dung trước khi công khai. |
| Trung bình | Chưa có số liệu hiệu năng hoặc xác nhận triển khai. | Kiểm tra trang trên môi trường đích, ghi thời gian tải cơ bản và xác minh tài nguyên. |

## 6. Đánh giá tổng kết và đề xuất

**Kết luận:** Sản phẩm đã có khung portfolio tĩnh, các khu vực nội dung chính, CSS responsive, hướng dẫn chạy và release notes. Tuy nhiên, tại thời điểm rà soát, sản phẩm **chưa sẵn sàng bàn giao để công khai** do các liên kết liên hệ/dự án chưa hoàn chỉnh, markup khu vực GitHub bất thường và chưa có kết quả kiểm thử trực quan cũng như minh chứng trên môi trường mục tiêu.

**Điều kiện đề xuất để nghiệm thu:**

1. Khắc phục các lỗi liên kết và markup được nêu trong báo cáo.
2. Xác nhận nội dung, email, hồ sơ GitHub, hình ảnh và đường dẫn dự án với chủ sở hữu.
3. Kiểm thử lại điều hướng, liên hệ và hiển thị responsive trên trình duyệt/thiết bị đã thống nhất; lưu ảnh chụp hoặc kết quả chạy.
4. Xác nhận website hoạt động trên môi trường triển khai dự kiến và cập nhật trạng thái/minh chứng vào báo cáo.

Sau khi hoàn tất các bước trên và cập nhật kết quả kiểm thử thực tế, người phụ trách nghiệm thu có thể đánh giá lại trạng thái bàn giao.