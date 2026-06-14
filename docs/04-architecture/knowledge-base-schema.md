# 🗂️ Kiến Trúc Kho Dữ Liệu Tri Thức Nền Tảng (Knowledge Base Schema)

> ***"Dữ liệu thô nạp vào thiết bị biên nếu không có cấu trúc sẽ biến AI thành một cỗ máy vẹt ngữ pháp. Tại RFL, mọi tệp tin tri thức đều phải mang một ADN định danh (Knowledge DNA) để các tác tử nhúng (Embeddings) có thể truy xuất chính xác trên phần cứng siêu tiết kiệm điện (0.1A)."***

Hệ thống quản lý tài sản tri thức trong thư mục `submod-intelligence/knowledge_assets/` được phân tách thành 4 lớp dữ liệu động bám sát tháp DIKW-L, sử dụng định dạng văn bản nhẹ (Markdown/JSON/YAML) để tối ưu hóa không gian lưu trữ Flash tại biên.

---

## 📂 1. Lớp Dữ Liệu Định Danh Tri Thức (Knowledge DNA Matrix)

Mọi tài liệu khi nạp vào hệ thống bắt buộc phải kèm theo một khối siêu dữ liệu (Metadata Header) bằng định dạng YAML ở đầu file. Đây là chìa khóa để Bộ định tuyến ngữ cảnh (Context Router) phân loại người học (F1 hay Mentor).

### Chuẩn Metadata Header (`.md` hoặc `.yaml`):
```yaml
asset_id: RFL-IKB-[TRACK-CODE]-[NUMBER]
title: "Tên tài liệu chuẩn mực"
layer: information | knowledge | wisdom | legacy
domain: embedded_electronics | industrial_robotics | core_philosophy | survival_skills
target_pacing: novice_f1 | mentor_f2 | elder
dependencies: [Danh sách ID tài liệu cần đọc trước]
open_badge_id: [ID chứng chỉ open badge tương ứng nếu có]
```
---

## 🏛️ 2. Cấu Trúc Chi Tiết 4 Tầng Thư Mục Tri Thức

### 📁 Tầng 01: 01_information/ (Thông tin kỹ thuật cấu trúc)

Nơi lưu trữ các tài liệu thô, datasheets, hướng dẫn sử dụng thiết bị và thư viện mã nguồn chuẩn hóa. AI sử dụng tầng này để trả lời các câu hỏi mang tính tra cứu chính xác cao (Fact-retrieval).

Cấu trúc thư mục con:

```yaml
educore_som/: Sơ đồ chân, sơ đồ nguyên lý phần cứng EduCore FC SOM.

industrial_robotics/: Sách hướng dẫn lập trình robot Mitsubishi MELFA/Nachi, mã lệnh điều khiển.

automation_plc/: Tài liệu hướng dẫn lập trình PLC iQ-R, FX series và màn hình HMI Weintek.

iot_edge/: Hướng dẫn thiết lập Docker, Node-RED, Home Assistant và ESP32 module.
```
---

### 📁 Tầng 02: 02_knowledge/ (Phương pháp luận & 18 Bài Lab thực chiến)

Nơi chứa toàn bộ giáo trình chuyển hóa thành năng lực hành động. Điểm cốt lõi là các kịch bản hướng dẫn xử lý lỗi (Troubleshooting) của 18 bài Lab.

Nguyên tắc thiết kế file bài Lab:

Không chứa code giải sẵn.

Chứa sơ đồ khối logic, sơ đồ đi dây mạch in (Altium layout).

Chứa danh mục các "Ảo ảnh cố ý" (Intentional Errors) để AI nạp vào cấu trúc Socratic, bắt học viên phải phản biện để tìm lỗi sai trong code giả (Pseudo-code).

---

### 📁 Tầng 03: 03_wisdom/ (Tri thức ẩn & Nhật ký gỡ lỗi của Mentor)

Tầng quan trọng tạo nên sự khác biệt của RFL. Đây là nơi số hóa các trải nghiệm thực tế, trực giác kỹ thuật và triết lý ứng xử mà sách giáo khoa không bao giờ dạy.

Mẫu cấu trúc dữ liệu Wisdom Tác tử (wisdom_notes):

```yaml
asset_id: RFL-IKB-WISDOM-ROBOT-01
domain: industrial_robotics
layer: wisdom
target_pacing: mentor_f2

---
Kinh nghiệm gỡ lỗi giao tiếp hệ tích hợp Robot - PLC:

Bối cảnh thất bại phổ biến:
Kỹ sư hệ thống thường có thói quen nối tiếp luồng dữ liệu ROS2/AI đi qua PLC rồi mới tới robot. Điều này tạo ra độ trễ (latency) lớn trong xử lý ảnh xử lý 3D bin picking.

Trực giác đúc kết (Wisdom Rule):
Bắt buộc phải thiết lập luồng giao tiếp SONG SONG. ROS2/AI đi một đường mạng độc lập truyền tọa độ trực tiếp vào bộ điều khiển Robot (Robot Controller). PLC chỉ làm nhiệm vụ giữ nhịp an toàn vật lý và điều khiển băng tải. Robot và PLC bắt tay (Handshake) song song.
```

---

### 📁 Tầng 04: 04_legacy/ (Di sản truyền thừa, Bản sắc và Sinh tồn)

Nơi lưu trữ mã gen tinh thần của hệ thống. Tầng này được AI sử dụng để nhúng vào nhân cách (Persona), tạo ra các câu thoại mang tính thấu cảm, giữ chân luồng văn hóa bản địa và xây dựng lòng tự trọng cho người học.

Nội dung cốt lõi:

Các bài viết lịch sử về sự phát triển tự lực cánh sinh (ví dụ: Lịch sử Linux và di sản mã nguồn mở).

Cẩm nang ứng xử "Nghệ thuật không nổi giận" dành cho Mentor khi đối diện với việc học viên làm cháy thiết bị.

Các bài học hiện sinh về trách nhiệm của thế hệ F1 khi thành danh phải quay lại làm Mentor nuôi dưỡng khối 16% cộng đồng.

---

## ⚙️ 3. Quy Trình Cập Nhật Tri Thức Tuần Hoàn (Knowledge Loop)

Để kho dữ liệu này tự tiến hóa liên tục liên thế hệ mà không bị lỗi thời, lõi AI phối hợp cùng con người theo quy trình:

```yaml
[Học viên làm Lab thành công] 
       ↓
[Phát hiện ra cách gỡ lỗi mới (Bug fix)] 
       ↓
[Mentor đánh giá & viết file Wisdom Note (Markdown)] 
       ↓
[AI tự động quét, gán nhãn Metadata & nạp vào Local Vector DB]
```