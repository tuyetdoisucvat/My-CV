# AI Change Log

Ghi lại các thay đổi lớn về chức năng, giao diện, cấu trúc dự án, phát hành
hoặc cấu hình triển khai. Không ghi các chỉnh sửa nhỏ như sửa lỗi chính tả.

## 2026-11-05 — Bổ sung báo cáo kiểm thử trước bàn giao

- Tạo `docs/test_report.md` với sáu nhóm tiêu chí, trạng thái, minh chứng và đề xuất nghiệm thu.
- Ghi nhận đây là rà soát tĩnh; các lỗi liên kết và phần kiểm thử trực quan còn thiếu cần được xử lý trước khi công khai.

## 2026-11-05 — Hoàn thiện và phát hành portfolio v1.0

- Hoàn thiện website portfolio cá nhân bằng HTML và CSS, gồm phần giới thiệu,
  kỹ năng, dự án, liên hệ và điều hướng trong trang.
- Hỗ trợ bố cục responsive cho điện thoại, máy tính bảng và máy tính.
- Ghi nhận phát hành v1.0 trong `docs/RELEASENOTE.md`.
- Liên kết repository Git với remote `origin` và sử dụng nhánh `main`.

### Quy ước cập nhật

Khi thực hiện thay đổi lớn tiếp theo, thêm mục mới lên đầu nhật ký theo mẫu:

```text
## YYYY-MM-DD — Tên thay đổi
- Nội dung thay đổi chính.
- Tác động hoặc lưu ý liên quan (nếu có).
```