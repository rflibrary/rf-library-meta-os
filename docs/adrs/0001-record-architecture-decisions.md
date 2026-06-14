# ADR 0001: Sử dụng Architecture Decision Record để lưu vết thay đổi

**Trạng thái:** Được chấp nhận (Accepted)
**Ngày:** 2026-06-14
**Người đề xuất:** Trần Nguyên Hải

## 1. Bối cảnh (Context)
Hệ thống RFL Meta-OS đang ở giai đoạn phát triển Beta. Với cấu trúc gồm 4 trụ cột (Engineering, Humanity, Intelligence, Process) và bản chất phi tập trung, chúng ta cần một cơ chế lưu trữ lịch sử ra quyết định để tránh việc "quên" lý do tại sao một kỹ thuật được chọn hoặc một cấu trúc được thiết lập.

## 2. Quyết định (Decision)
Kể từ thời điểm này, mọi thay đổi mang tính kiến trúc (thay đổi cấu trúc file, chọn Framework mới, thay đổi giao thức truyền thông) đều bắt buộc phải được ghi lại dưới dạng file `.md` trong thư mục `docs/adrs/`.

## 3. Hệ quả (Consequences)
* **Ưu điểm:** Tạo ra nhật ký kiến trúc minh bạch. Giúp các thành viên mới hiểu được "lý do" thay vì chỉ nhìn thấy "kết quả".
* **Nhược điểm:** Tăng khối lượng công việc hành chính nhỏ cho các kỹ sư (cần dành 5-10 phút để viết file ADR).

## 4. Trạng thái các quyết định
* **Proposed:** Đang đề xuất.
* **Accepted:** Đã được đồng thuận áp dụng.
* **Superseded:** Đã bị thay thế bằng một quyết định mới (cần trỏ link tới ADR mới).

## 💡 Hướng dẫn vận hành ADR cho RFL Meta-OS
Để file ADR thực sự có giá trị, mỗi khi bạn định làm điều gì đó quan trọng, hãy tuân theo quy trình "Kiến trúc sư":

Đánh số thứ tự: File tiếp theo sẽ là 0002-....md, cứ thế tăng dần.

Đặt tiêu đề: Ngắn gọn, súc tích (Ví dụ: 0002-su-dung-docker-cho-deployment.md).

Quy tắc "Không ADR, không thay đổi": Nếu quyết định ảnh hưởng đến toàn bộ 4 trụ cột, hãy bắt buộc tạo ADR. Nếu chỉ là sửa lỗi (bugfix) nhỏ, không cần.