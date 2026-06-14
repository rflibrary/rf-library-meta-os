# 📘 Hướng Dẫn & Bản Đồ Kiến Trúc Vĩ Mô (Macro-Architecture & Routing Guide)

> ***"Sự rành mạch của tài liệu quyết định sự sống còn của một hệ thống phức tạp. Tại RFL Meta-OS, chúng ta phân định rạch ròi giữa Bản quy hoạch thành phố (Vĩ mô) và Bản vẽ thi công tòa nhà (Vi mô)."***

Thư mục này là trung tâm điều phối toàn bộ **Kiến trúc Vĩ mô (Macro-Architecture)** của hệ thống Thư viện RF. Đây là nơi gác cổng, định hướng cấu trúc tích hợp giữa phần cứng, năng lượng, mạng lưới phân tán và luồng dữ liệu trước khi chúng được triển khai chi tiết ở biên (Submodules).

---

## 🗺️ Danh Mục Văn Kiện Kiến Trúc Hệ Thống

Để nắm bắt toàn diện siêu cấu trúc Thực - Ảo (Cyber-Physical System) của RFL, các kỹ sư và điều phối viên cần đọc các văn kiện cốt lõi theo lộ trình logic dưới đây:

1. **[Kiến Trúc Kỹ Thuật RFL OEA](oea-technical-architecture.md) (Open Edge AI Core):**
   * *Nội dung:* Bản đồ thiết kế 3 lớp (Thiết bị Biên NPU 0.1A - Lõi suy luận Offline RAG/SLM - Giao diện nhẹ PWA) và cơ chế đồng bộ dữ liệu vật lý qua USB (Sneakernet).
2. **[Kiến Trúc Kho Dữ Liệu Tri Thức Nền Tảng](knowledge-base-schema.md) (DIKW-L Schema):**
   * *Nội dung:* Quy chuẩn ma trận ADN dữ liệu (Knowledge DNA Matrix), cấu trúc phân tách 4 tầng tài sản thông tin từ thô đến di sản, và giao thức đóng gói tri thức tuần hoàn.

---

## 🧭 Quy Tắc Tối Thượng: "Vĩ mô ở Gốc - Vi mô ở Biên"

Trước khi khởi tạo hoặc commit một tài liệu kiến trúc mới, bắt buộc phải tự vấn: 
**"Tài liệu này mô tả sự kết nối giữa các phân hệ (A kết nối B), hay mô tả cấu trúc logic bên trong của một phân hệ (Ruột của A)?"**

### 1. Nếu là "Sự kết nối" ➔ Lưu tại đây (`docs/04-architecture/`)
Mô tả toàn cảnh cách các Trụ cột (Submodules) giao tiếp, tương tác vật lý hoặc trao đổi giao thức với nhau.
* **Tài liệu hợp lệ:** Bản vẽ cơ khí mặt bằng khối container, sơ đồ mạng LAN nội bộ, kiến trúc điện mặt trời hòa lưới (Zero-Battery) cấp nguồn cho hệ thống tính toán biên.

### 2. Nếu là "Cấu trúc bên trong" ➔ Lưu tại Biên (`submod-[tên-phân-hệ]/docs/`)
Mô tả chi tiết kỹ thuật chuyên biệt. Nếu tách riêng Submodule này ra khỏi dự án tổng, phân hệ đó vẫn phải đủ tài liệu để tự vận hành độc lập như một kho mã nguồn mở riêng lẻ.
* **Tài liệu hợp lệ:** Sơ đồ chân vi điều khiển, bản vẽ mạch in Altium (Carrier Board), sơ đồ thuật toán Python (`persona_agent.py`), API endpoint cục bộ của FastAPI.

---

## ⚖️ Bảng Đối Chiếu Nhanh Quyết Định Lưu Trữ

| Loại tài liệu thiết kế | Vị trí lưu trữ chuẩn xác | Ghi chú kiểm soát |
| :--- | :--- | :--- |
| **Sơ đồ tích hợp liên phân hệ (≥ 2 Trụ cột)** | `docs/04-architecture/` | Ví dụ: Luồng đối soát Giao thức 84/16 toàn trạm. |
| **Cấu trúc thư mục mã nguồn / File code** | `submod-*/docs/` | Ví dụ: Cơ chế bóc tách chunking của file RAG. |
| **Giao thức mạng, bảo mật, đồng bộ chung** | `docs/04-architecture/` | Ví dụ: Quy trình nén và phân phối dữ liệu diện rộng. |
| **Sơ đồ nguyên lý mạch in (Schematics)** | `submod-*/docs/` | Ví dụ: Layout Altium tối ưu viễn trắc cảm biến AMR. |

> **⚠️ CẢNH BÁO TỪ KIẾN TRÚC SƯ TRƯỞNG:** Tuyệt đối không lưu các đoạn mã mẫu (code snippets), tài liệu sửa lỗi phần mềm cục bộ hoặc hướng dẫn cài đặt thư viện vào thư mục này. Hãy trả tài liệu về đúng hộp kỹ thuật của Submodule tương ứng để bảo vệ tính đóng gói hệ thống.