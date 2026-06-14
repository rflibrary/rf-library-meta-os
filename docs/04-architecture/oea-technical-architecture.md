# 🏗️ Kiến Trúc Kỹ Thuật RFL OEA: Trạm Trí Tuệ Bản Địa

> *"Đưa tri thức vào thiết bị biên không chỉ là tối ưu hóa phần mềm. Đó là nghệ thuật ép một hệ sinh thái điện toán khổng lồ vào những bo mạch chỉ tiêu thụ 0.1A, hoạt động kiên cường giữa những nơi không có Internet và lưới điện chập chờn."*

Kiến trúc hệ thống RFL OEA (Open Edge AI) được thiết kế theo mô hình 3 lớp cốt lõi, tập trung tối đa vào sự sinh tồn vật lý và hiệu năng suy luận cục bộ:

---

## 💻 Lớp 1: Thiết Bị Edge (Edge AI Node) - "Trái Tim Vật Lý"

Đây là các thiết bị phần cứng được triển khai trực tiếp tại các vùng sâu vùng xa, đóng vai trò là một "trạm trí tuệ bản địa" khép kín.

* **Phần cứng Xử lý Tối ưu (NPU/GPU):** Khước từ các CPU truyền thống ngốn điện. Ưu tiên các dòng Single Board Computer (SBC) tích hợp NPU (Neural Processing Unit) như Orange Pi 5 (Rockchip RK3588) hoặc các nền tảng ARM tối giản. 
* **Giới hạn Sinh tồn 0.1A & Zero-Battery:** Thực nghiệm đo lường bằng ampe kế xác nhận hệ thống có thể duy trì dòng tiêu thụ ở mức cực thấp **0.1A**. Tuân thủ tuyệt đối kiến trúc năng lượng mặt trời hòa lưới (Grid-tied). **Loại bỏ hoàn toàn UPS/Pin lưu trữ truyền thống** để triệt tiêu OPEX. Chỉ sử dụng Tụ siêu điện dung (Supercapacitors) làm bộ đệm nhỏ đủ để hệ thống thực hiện lệnh *Safe Shutdown* khi mất điện đột ngột.
* **Lưu trữ Bền bỉ:** Sử dụng ổ cứng SSD M.2 (NVMe/SATA) thay cho thẻ MicroSD để chịu tải cường độ đọc/ghi liên tục của cơ sở dữ liệu Vector, đảm bảo tuổi thọ lên tới hàng chục năm.
* **Mạng Lưới Nội Bộ (Intranet):** Thiết bị tự phát sóng Wi-Fi (Hotspot) cực nhẹ, cho phép các thiết bị cũ (điện thoại, máy tính bảng nhận tài trợ) xung quanh kết nối vào hệ sinh thái mà không cần bất kỳ trạm BTS nào.

---

## 🧠 Lớp 2: AI & Tri Thức Bản Địa (Inference Layer) - "Bộ Não Khai Phóng"

Lớp cốt lõi biến các tệp văn bản vô tri thành một "Người thầy" có khả năng tương tác.

* **Công Nghệ Lượng Tử Hóa (SLM Quantization):** Sử dụng các mô hình ngôn ngữ nhỏ gọn tối ưu cho tiếng Việt (Qwen-1.5/2.5, Gemma-2B) được lượng tử hóa xuống định dạng 4-bit/8-bit (.gguf / .bin).
* **Động Cơ Suy Luận (Inference Engine):** Triển khai LiteRT (MediaPipe), `llama.cpp` hoặc `Ollama` viết bằng C/C++ thuần. Cắt giảm toàn bộ overhead (tài nguyên dư thừa), ép mô hình chạy trực tiếp trên NPU/CPU nội bộ để triệt tiêu độ trễ.
* **RAG Cục Bộ (Offline Vector DB):** Nạp toàn bộ kho tàng văn học, lịch sử, kỹ năng sinh tồn vào cơ sở dữ liệu Vector (FAISS, ChromaDB). Khi người dùng hỏi, AI lục tìm bối cảnh từ Vector DB để trả lời, loại bỏ hoàn toàn hiện tượng "ảo giác" (Hallucination) và giữ vững bản sắc địa phương.
* **Tương Tác Đa Phương Thức (Voice-first):** Tích hợp Whisper.cpp (Speech-to-Text) và Coqui TTS (Text-to-Speech) tiếng Việt. Trẻ em chưa thạo gõ phím hoàn toàn có thể trò chuyện bằng giọng nói với AI.

---

## 🌐 Lớp 3: Giao Diện & Vận Hành (App & UI Layer) - "Cầu Nối Thấu Cảm"

Tuân thủ triết lý *Thiết kế Vị Nhân* và *Giao diện Tàng hình (Invisible UI)*, công nghệ lùi lại để nhường chỗ cho sự tương tác tự nhiên.

* **Ứng Dụng Web-based Nhẹ Nhàng (PWA):** Giao diện chạy trực tiếp trên trình duyệt web, không cần cài đặt app. Thiết kế biểu tượng lớn, màu sắc ấm áp, tập trung vào khung hội thoại.
* **Cơ Chế Cập Nhật "Sinh Tồn" (Offline Sync):** 
    * **Cập nhật Vật lý (Sneakernet):** Phương thức chủ đạo. Cán bộ hoặc Mentor mang theo một chiếc USB chứa tệp cập nhật dữ liệu Vector mới. Chỉ cần cắm vào Edge Node, hệ thống tự động mount, đồng bộ khối lượng tri thức mới và ngắt kết nối.
    * **Intermittent OTA (Tùy chọn):** Ở những điểm có sóng 4G chập chờn, thiết bị tự thức dậy vào khung giờ đêm tĩnh lặng nhất (khi băng thông rảnh), tải các bản vá Docker siêu nhỏ gọn và tự động ngủ lại.

---

## 🚀 Lộ Trình Triển Khai Thực Chiến (OEA Roadmap)

1. **Giai đoạn PoC (Proof of Concept):** Triển khai thử nghiệm mô hình Qwen-1.5 (hoặc Gemma) trên nền tảng Orange Pi 5 / Mini-PC. Đo đạc bằng ampe kế để khóa cứng định mức 0.1A. Tích hợp RAG offline bằng FAISS.
2. **Giai đoạn Đóng gói Tri thức (Knowledge Curation):** Số hóa và nạp toàn bộ giáo trình 18 bài Lab EduCore, truyện dân gian, kỹ năng sinh tồn vào Vector DB. Tối ưu hóa System Prompts để định hình nhân cách "Mentor".
3. **Giai đoạn Thực địa (Field Deployment):** Triển khai thực tế tại một vùng lõm sóng (ví dụ: các trạm thư viện container RF). Đánh giá khả năng tản nhiệt thụ động, độ bền của SSD và mức độ tương tác bằng giọng nói của học viên.