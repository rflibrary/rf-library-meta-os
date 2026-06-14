# ⚙️ Phân Hệ Quy Trình & Thuật Toán Sinh Tồn (submod-process)

> ⚠️ **TRẠNG THÁI DỰ ÁN: PHIÊN BẢN THỬ NGHIỆM (BETA) - CHƯA PHÁT HÀNH CHÍNH THỨC**
> *Hệ điều hành Meta-OS hiện đang trong giai đoạn xây dựng kiến trúc lõi (Macro-Architecture) và thử nghiệm giao thức sinh tồn (Proof of Concept). Các phân hệ (Submodules) đang trong quá trình lắp ráp và cấu trúc có thể thay đổi liên tục trước khi đạt bản Release v1.0.0. Hiện tại chưa khuyến nghị triển khai vào môi trường thực tế (Production). Mọi đóng góp mã nguồn (Pull Requests) và ý tưởng kiến trúc ở giai đoạn này đều được chào đón!*

> ***"Lòng tốt không có hệ thống quản trị sẽ nhanh chóng biến thành sự ban phát kiệt quệ. Tại RFL, chúng tôi không để sự sống còn của thư viện phụ thuộc vào cảm xúc của một nhà tài trợ hay sự hy sinh tùy hứng của một Mentor. Chúng tôi giao phó nó cho Toán học."***

---

## 🌍 Tổng Quan & Sứ Mệnh

Phân hệ `submod-process` là "Bộ máy Tiêu hóa" và "Hệ Tuần hoàn" của RFL Meta-OS. Nó đảm nhiệm Trụ cột Quy trình, biến các triết lý vĩ mô thành những dòng code logic và hợp đồng đối soát tự động (Smart Logic/Contracts).

Nhiệm vụ tối thượng của phân hệ này là tạo ra và nuôi dưỡng hai lớp năng lượng sống còn:
* 🟢 **[NL Xúc Tác]:** Hệ thống Tokenomics (RF Points) định lượng hóa sự cống hiến, biến mọi nỗ lực của Mentor và học viên thành tài nguyên hữu hình có thể giao dịch trong hệ sinh thái.
* 🟢 **[NL Tái Tạo]:** Khóa chặt và điều phối dòng vốn/tài nguyên phần cứng theo một tỷ lệ vàng bất di bất dịch, đảm bảo hệ thống tự nuôi sống chính nó xuyên thập kỷ.

---

## 📂 Bản Đồ Thư Mục (Directory Structure)

Cấu trúc của phân hệ tập trung hoàn toàn vào luồng xử lý (Flows) và thuật toán phân bổ (Algorithms):

```text
submod-process/
│
├── 📂 84-16-allocation/           # ⚖️ TRÁI TIM DÒNG TIỀN (Giao Thức Sinh Tồn)
│   ├── 📄 algorithm-logic.md      # Đặc tả thuật toán khóa/mở băng thông và phân bổ tài nguyên
│   └── 📄 execution-scripts/      # Mã nguồn tự động đối soát (Cronjobs, Logic tính toán)
│
├── 📂 tokenomics-rf-points/       # 🪙 HỆ THỐNG ĐIỂM XÚC TÁC
│   ├── 📄 point-calculation.md    # Công thức quy đổi: Giờ dạy Mentor, Hoàn thành Lab -> RF Points
│   └── 📄 reward-punishment.md    # Cơ chế khuyến khích và giới hạn (Tự động khóa thiết bị khi điểm âm)
│
└── 📄 README.md                   # 📘 Mặt tiền điều phối phân hệ (Tài liệu này)

```

---

## ⚠️ 2 Định Luật Vận Hành Cốt Lõi (Core Process Directives)

Mọi thuật toán, mọi file thực thi bash script hay Python được viết trong phân hệ này phải tuyệt đối trung thành với 2 định luật sau:

**1. Định Luật Vàng:** Giao Thức Đối Soát Tự Động 84/16
Tỷ lệ thương mại/cộng đồng không phải là một con số để tham khảo; nó là một hằng số toán học được hard-code vào hệ thống.

Thuật toán phải tự động tính toán và tách bạch: 84% năng lực thiết bị, thời gian và doanh thu được dùng để duy trì thương mại và tái đầu tư hạ tầng.

Đúng 16% tài nguyên hệ thống (thiết bị rảnh rỗi, băng thông AI, ngân quỹ) phải được thuật toán tự động đóng băng (lock) và chỉ có thể được mở khóa (unlock) cho các hoạt động phục vụ cộng đồng phi lợi nhuận.

Con người (kể cả ban quản trị) không có quyền can thiệp tay để phá vỡ tỷ lệ 84/16 này.

**2. Sự Vô Cảm Công Bằng (Automated Objectivity)**

Không có ngoại lệ trong hệ thống quản trị năng lượng.

Hệ thống tokenomics-rf-points hoạt động như một quan tòa vô hình. Nếu một học viên khối thương mại hết hạn mức truy cập, hệ thống tự động khóa băng thông (API Rate Limiting) mà không cần sự can thiệp của con người.

Việc đánh giá cấp chứng chỉ (Open Badges) phải được đối soát chéo (Cross-check) thông qua quy trình: Học viên nộp sản phẩm thực tế ➔ AI chấm sơ bộ (Intelligence) ➔ Mentor xác nhận (Humanity). Thiếu một trong ba node, quy trình tự động từ chối cấp chứng chỉ.

---

## 🛡️ Tấm Khiên Pháp Lý Logic (Logic License)

Toàn bộ các thuật toán đối soát dòng tiền, luồng quản trị RF Points và các đoạn mã tự động hóa trong submod-process được phân phối dưới giấy phép [GNU AGPL v3.0].

Ý nghĩa: Việc kiểm soát tài nguyên phải minh bạch đến tận cùng. Bất kỳ thực thể nào muốn sử dụng "Giao thức 84/16" của chúng tôi để vận hành một hệ thống lưu trữ qua mạng (dù không phân phối trực tiếp mã nguồn), đều bắt buộc phải mở mã nguồn những tùy chỉnh của họ để cộng đồng cùng giám sát.

---

## 🛠️ Hướng Dẫn Đóng Góp (Contributors Guide)
Phân hệ này chào đón các kỹ sư Hệ thống, chuyên gia Smart Contract và Data Analysts:

Mọi đề xuất thay đổi công thức tính RF Points hoặc quy trình tính toán 84/16 phải được chứng minh bằng một bản mô phỏng toán học (Simulation).

Viết ADR cho mọi thay đổi logic cốt lõi.

Tạo Pull Request với cấu trúc: feat(process): [Tên thuật toán/Luồng xử lý].
