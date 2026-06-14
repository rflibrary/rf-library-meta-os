# ADR 0002: Giao thức Đồng bộ Tri thức Ngoại tuyến (Offline Knowledge Sync)

**Trạng thái:** Được chấp nhận (Accepted)
**Ngày:** 2026-06-14
**Người đề xuất:** Trần Nguyên Hải

## 1. Bối cảnh (Context)
Các trạm RFL hoạt động trong môi trường không có internet (Offline-first). Để đảm bảo tính thống nhất của tri thức (Vector DB) và lộ trình học tập trên toàn hệ thống, chúng ta không thể dựa vào việc tải xuống dữ liệu từ Cloud. Chúng ta cần một quy trình vật lý hóa việc cập nhật tri thức.

## 2. Quyết định (Decision)
Áp dụng **Giao thức "Sneakernet" (Đồng bộ qua phương tiện lưu trữ vật lý)** làm tiêu chuẩn cập nhật tri thức chính:
* **Đơn vị truyền tải:** Sử dụng USB Flash Drive (hoặc ổ cứng di động) làm thiết bị vận chuyển dữ liệu (Data Shuttle).
* **Cơ chế:** Mỗi trạm sẽ có một thư mục `/knowledge_assets/sync` để kiểm tra các tệp Delta (dữ liệu thay đổi) từ USB.
* **Cấu trúc dữ liệu:** Sử dụng định dạng `tar.gz` chứa các tệp Vector DB đã được đóng gói từ "Trạm Tri Thức Gốc".
* **Xác thực:** Mỗi gói dữ liệu cập nhật phải đi kèm file `checksum.sha256` để đảm bảo tính toàn vẹn của tri thức trước khi nạp vào bộ nhớ biên.

## 3. Hệ quả (Consequences)
* **Ưu điểm:**
    * Đảm bảo tính chủ quyền tri thức (không phụ thuộc internet).
    * Giảm băng thông tối đa và tránh rủi ro bảo mật từ các API công cộng.
* **Nhược điểm:**
    * Phụ thuộc vào yếu tố vật lý (con người phải cắm USB để cập nhật).
    * Độ trễ của tri thức (tri thức mới không thể cập nhật tức thời trên toàn mạng lưới).

## 4. Ghi chú vận hành
* Khi một trạm biên cập nhật tri thức thành công, hệ thống sẽ tự động ghi nhật ký vào `submod-process/sync_log.csv` để đối soát phiên bản dữ liệu (Version Control).
* Trạm nào có phiên bản tri thức cũ hơn 3 tháng sẽ tự động báo động trên bảng điều khiển để ưu tiên cập nhật trong đợt tiếp theo.