# 🔧 Phân Hệ Công Nghệ & Cơ Điện Tử (submod-engineering)

> ⚠️ **TRẠNG THÁI DỰ ÁN: PHIÊN BẢN THỬ NGHIỆM (BETA) - CHƯA PHÁT HÀNH CHÍNH THỨC**
> *Hệ điều hành Meta-OS hiện đang trong giai đoạn xây dựng kiến trúc lõi (Macro-Architecture) và thử nghiệm giao thức sinh tồn (Proof of Concept). Các phân hệ (Submodules) đang trong quá trình lắp ráp và cấu trúc có thể thay đổi liên tục trước khi đạt bản Release v1.0.0. Hiện tại chưa khuyến nghị triển khai vào môi trường thực tế (Production). Mọi đóng góp mã nguồn (Pull Requests) và ý tưởng kiến trúc ở giai đoạn này đều được chào đón!*

> ***"Công nghệ tại Thư viện RF không được đo đạc bằng sự phức tạp phô trương, mà bằng khả năng sinh tồn. Một bo mạch vĩ đại không phải là bo mạch nhồi nhét nhiều tính năng nhất, mà là bo mạch tiêu thụ dòng điện thấp nhất, dễ tái chế nhất, và hoạt động bền bỉ nhất ở những nơi khắc nghiệt nhất."***

---

## 🌍 Tổng Quan & Sứ Mệnh

Phân hệ `submod-engineering` chịu trách nhiệm thực thi chữ **'E' (Engineering)** trong mô hình nền tảng H.E.I. Đây là khung xương vật lý của toàn bộ hệ sinh thái RFL Meta-OS. 

Nhiệm vụ của phân hệ này không phải là chạy đua vũ trang phần cứng, mà là thiết lập một **Hạ tầng Tối giản (Minimalist Infrastructure)**. Chúng ta kiến tạo các thiết bị vật lý, trạm phát sóng Edge AI và nền tảng Robot để tạo ra lớp năng lượng **[NL Hạ Tầng]**, làm bệ phóng vững chắc cho sự tiến hóa của Trí tuệ (Intelligence) và Con người (Humanity).

---

## 📂 Bản Đồ Thư Mục (Directory Structure)

Cấu trúc phần cứng được chia thành 3 mảng trọng yếu, phân tách rõ ràng giữa cấp nguồn, lõi xử lý và cơ cấu chấp hành:

```text
submod-engineering/
│
├── 📂 infrastructure/             # ☀️ HẠ TẦNG NĂNG LƯỢNG & KHÔNG GIAN
│   └── 📂 solar-grid-tied/        # Tiêu chuẩn điện mặt trời hòa lưới (Triệt tiêu rủi ro/chi phí Pin lưu trữ)
│
├── 📂 edge-nodes/                 # 🖥️ TRẠM XỬ LÝ BIÊN & PHẦN CỨNG NHÚNG
│   ├── 📂 ai-carrier-board/       # Bản vẽ Altium thiết kế bo mạch tối ưu Sensor Fusion
│   └── 📂 educore-fc-som/         # Hệ sinh thái phần cứng phục vụ lộ trình 18 bài Lab thực chiến
│
├── 📂 robotics-automation/        # 🤖 ĐIỀU KHIỂN & CƠ ĐIỆN TỬ
│   ├── 📂 autonomous-electric/    # Cấu trúc xe điện phục vụ nghiên cứu tự hành (AMR / ROS2)
│   ├── 📂 manual-petrol/          # Cấu trúc xe động cơ xăng (Bắt buộc điều khiển bằng tay cầm/cáp)
│   └── 📂 robot-plc-handshake/    # Giao thức truyền thông song song cho tay máy công nghiệp
│
└── 📄 README.md                   # 📘 Mặt tiền điều phối phân hệ (Tài liệu này)

```

---

## ⚠️ 3 Giới Hạn Kỹ Thuật Cốt Lõi (Core Technical Directives)
Để đảm bảo hệ thống vận hành theo đúng Tuyên ngôn của RFL, mọi kỹ sư đóng góp vào phân hệ này phải tuân thủ tuyệt đối 3 giới hạn vật lý sau. Bất kỳ thiết kế nào vi phạm sẽ bị Hệ Miễn Dịch Đạo Đức từ chối Merge.

1. **Chuẩn Sinh Tồn Năng Lượng:** Giới Hạn 0.1A & Zero-Battery

Hệ thống trạm thư viện RFL khước từ việc sử dụng các hệ thống lưu trữ bằng Pin/Ắc quy đắt đỏ và độc hại.

Hệ thống năng lượng sử dụng kiến trúc Hòa lưới (Grid-tied) để tối ưu CAPEX/OPEX.

Lõi xử lý biên (Edge Mini-PC) phải được tinh chỉnh phần cứng và hệ điều hành sao cho dòng điện tiêu thụ thực tế đo được qua ampe kế chỉ dao động ở mức 0.1A (chứ không phải các mức tính toán lý thuyết hay thông số ảo từ nền tảng IoT). Năng lượng phải được chắt chiu đến từng miliampe để phục vụ khối 16% cộng đồng.

2. **Định Luật An Toàn Cơ Điện Tử:** Phân Định Nền Tảng Động Cơ
An toàn là lằn ranh đỏ không thể vượt qua. Tự động hóa phải gắn liền với khả năng kiểm soát động năng.

Đối với nền tảng xe động cơ xăng: Mang rủi ro cháy nổ và động năng mất kiểm soát cao, tuyệt đối không được áp dụng các module tự hành. Bắt buộc phải duy trì cơ chế điều khiển thủ công qua tay cầm và cáp kết nối (Cable-controlled).

Đối với nền tảng xe điện (AMR): Được cấp phép tích hợp cảm biến, bo mạch AI Carrier Board để phát triển và nghiên cứu tự hành (Autonomous Navigation) phục vụ lộ trình học tập.

3. **Cấu Trúc Luồng Dữ Liệu:** Giao Tiếp Song Song (Parallel Handshake)
Trong tự động hóa công nghiệp (ví dụ: tay máy Mitsubishi/Nachi kết hợp hệ thống iQ-R/FX), các thiết kế truyền thống thường mắc sai lầm khi cho luồng dữ liệu AI đi nối tiếp qua PLC, gây độ trễ và nghẽn cổ chai.

Tại RFL, kiến trúc điều khiển yêu cầu ROS2 và AI không đi qua PLC.

Hệ thống phải được thiết kế theo giao thức: Robot ↔ PLC = Song song. Luồng xử lý thị giác máy tính và AI biên sẽ giao tiếp trực tiếp với bộ điều khiển tay máy, trong khi PLC chỉ giám sát các trạng thái I/O ngoại vi.

---

## 🛡️ Tấm Khiên Pháp Lý Phần Cứng (Hardware License)
Toàn bộ các thiết kế nguyên lý (Schematics), bản vẽ mạch in (PCB Layout), sơ đồ đấu nối và thiết kế cơ khí trong phân hệ submod-engineering được phân phối dưới giấy phép [CERN-OHL-S v2.0] (CERN Open Hardware Licence Version 2 - Strongly Reciprocal).

Ý nghĩa: Bạn hoàn toàn có quyền sao chép, sản xuất thương mại các bo mạch và khung gầm robot của RFL cho dự án của bạn. Tuy nhiên, nếu bạn chỉnh sửa bản vẽ để tạo ra một phiên bản tốt hơn, bạn bắt buộc phải công bố lại bản vẽ cải tiến đó cho cộng đồng dưới cùng một giấy phép mở.

---

## 🛠️ Hướng Dẫn Đóng Góp (Contributors Guide)
Nếu bạn là một kỹ sư Altium, chuyên gia ROS2 hoặc một chuyên viên Tự động hóa muốn đóng góp vào hệ sinh thái vật lý của RFL:

Đảm bảo bản vẽ thiết kế của bạn tuân thủ chuẩn năng lượng và an toàn.

Với các cập nhật liên quan đến giao thức điều khiển, yêu cầu phải đi kèm một bản ADR (Architecture Decision Record) lưu trong thư mục docs/adrs/ của Meta-Repo gốc.

Tạo Pull Request với mô tả chi tiết: feat(hardware): [Tên bo mạch/Giao thức].
