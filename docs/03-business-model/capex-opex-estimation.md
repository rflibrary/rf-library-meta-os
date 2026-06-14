# 📊 Bảng Dự Toán Khung CAPEX & OPEX (Tiêu Chuẩn)

> *"Công nghệ phải là đòn bẩy, không phải gánh nặng. Nếu chi phí duy trì một hệ thống đắt hơn giá trị tri thức nó tạo ra, hệ thống đó đang đi ngược lại sự khai phóng."* — Lõi triết lý Thư viện RF.

Tài liệu này phác thảo mô hình tài chính tối giản cho một Node Trạm Thư viện RF (vận hành trong container hoặc phòng học cải tạo 15-20m2). Các con số mang tính chất tỷ trọng (tham chiếu) để chứng minh tính khả thi của mô hình so với các thư viện truyền thống.

---

## 1. CAPEX (Chi Phí Đầu Tư Ban Đầu - Capital Expenditure)

Thay vì mua sắm thiết bị công nghiệp nguyên chiếc đắt đỏ, Thư viện RF áp dụng cơ chế lắp ráp module từ linh kiện tái chế và vi điều khiển giá rẻ, giúp **giảm 70% CAPEX** so với thông thường.

| Hạng Mục Hạ Tầng | Thành Phần Cốt Lõi | Chiến Lược Tối Ưu Chi Phí (Core Directives) |
| :--- | :--- | :--- |
| **Không Gian Vật Lý** | Container 20ft / Cải tạo phòng trống | Tận dụng vỏ container hoặc không gian mượn từ đối tác địa phương. Thiết kế module tháo lắp nhanh. |
| **Năng Lượng (Điện)** | Tấm pin Solar + Inverter hòa lưới (Grid-tied) | **Zero-Battery:** Cắt bỏ hoàn toàn hệ thống pin lưu trữ đắt đỏ. Dùng phần mềm Node-RED điều phối tải né giờ cao điểm. |
| **Lõi Trí Tuệ (Edge Server)** | Mini-PC chạy Local RAG & LLM | Tối ưu hóa phần cứng nhúng. Thực tế đo đạc, hệ thống Mini-PC chạy AI Agent chỉ tiêu thụ dòng 0.1A, cực kỳ tiết kiệm điện năng so với máy chủ truyền thống. |
| **Viễn Trắc & IoT** | ESP32, Node-RED, Cảm biến dòng, Đầu đọc RFID | Sử dụng phần cứng mã nguồn mở, chi phí cực thấp (dưới 500k VNĐ/Node) để giám sát toàn bộ sinh cảnh thư viện. |
| **Cơ Điện Tử (Robot)** | Khung gầm cáp kéo, Động cơ xe máy điện tái chế | Tận dụng rác thải điện tử (e-waste). Giữ điều khiển cáp cho động cơ xăng (An toàn cơ học) và phát triển tự hành cho xe điện. |

---

## 2. OPEX (Chi Phí Vận Hành Định Kỳ - Operational Expenditure)

Mục tiêu tối thượng của Định luật RF là ép đường cong OPEX tiệm cận về 0 trong dài hạn thông qua **Trí tuệ Thích ứng** và **Năng lượng tái tạo**.

| Hạng Mục Vận Hành | Chi Phí Truyền Thống | Giải Pháp Của RF Library | Tỷ Lệ Cắt Giảm |
| :--- | :--- | :--- | :--- |
| **Điện Năng** | Rất cao (Máy lạnh, Server chạy 24/7, Đèn) | Điện mặt trời bù lưới. Thuật toán tự động ngắt các Node khi không có học viên quét thẻ RFID. Hệ thống Mini-PC (0.1A) tiêu thụ điện không đáng kể. | **~80%** |
| **Nhân Sự Giảng Dạy** | Phải thuê giáo viên đứng lớp thường xuyên | Tác tử AI (Local RAG) đóng vai trò Trợ giảng 24/7. Mentor con người chỉ điều phối, không đứng lớp. Học viên F1 giỏi lên tự làm Mentor (Lãi kép con người). | **~90%** |
| **Bảo Trì Phần Cứng** | Cao (thay pin mặt trời định kỳ mỗi 3-5 năm) | Áp dụng cấu trúc Zero-Battery (Không pin). Thiết bị hỏng được đưa vào làm module thực hành sửa chữa cho chính học viên. | **~100%** |
| **Phần Mềm / Cloud** | Phí duy trì Server AWS/Google Cloud hàng tháng | Kiến trúc Offline-first. Mọi dữ liệu (RAG, Tokenomics) chạy cục bộ trên Edge Server. Chỉ đồng bộ gói dữ liệu nhỏ lên Cloud khi mạng rỗi. | **~95%** |

---

## 3. Bài Toán Sinh Tồn: Giao Thức Đối Soát 84/16

OPEX hàng tháng (dù đã được ép xuống mức cực thấp) vẫn cần dòng tiền thực tế để duy trì (tiền Internet, hao mòn vật lý, khấu hao thiết bị mới). 

Dòng tiền này được giải quyết bằng **Giao thức Sinh tồn (Điều 4)**:

* **Khối Thương Mại (84% Thời gian/Không gian):** Trạm thư viện cung cấp các module đào tạo thực chiến (Skill Passport, Lập trình ROS2, PLC tích hợp AI) cho sinh viên/kỹ sư có khả năng chi trả. Toàn bộ doanh thu từ đây sẽ thanh toán 100% OPEX của trạm.
* **Khối Cộng Đồng (16% Thời gian/Không gian):** Quỹ thời gian, băng thông và thiết bị dư thừa được "khóa cứng" và cung cấp hoàn toàn miễn phí cho lứa thanh thiếu niên khó khăn. Họ không trả bằng tiền, họ trả bằng **RF Points** (Sự nỗ lực, kết quả làm Lab, và trở thành Mentor thế hệ kế tiếp).

> **Kết luận Tài chính:** Trạm Thư viện RF không phải là một "cỗ máy đốt tiền tài trợ". Nó là một doanh nghiệp xã hội có khả năng tự bù trừ OPEX ngay trong năm đầu tiên và sinh ra lãi kép về mặt nhân sự (Mentor) từ năm thứ hai trở đi.