# 🧠 Submodule: Intelligence (Trí Tuệ Thích Ứng & Lõi RAG Cục Bộ)

> ***"Đưa tri thức vào thiết bị biên không chỉ là một giải pháp công nghệ, đó là hành động phá bỏ rào cản độc quyền internet và địa lý. Tri thức không còn nằm xa xôi trên đám mây, mà thở cùng nhịp với cộng đồng ngay trong những chiếc máy tính nhúng tại các bản làng xa xôi."***

Đây là kho lưu trữ lõi của **Trụ cột I (Intelligence)** trong hệ sinh thái RF Library Meta-OS. Phân hệ này chịu trách nhiệm vận hành "Trạm Tri Thức Biên" (Local Knowledge Station), biến các thiết bị phần cứng giá rẻ thành những "Gia sư tri thức cộng đồng" hoàn toàn tự chủ.

---

## 🗺️ Mô Hình Hạ Tầng: Trạm Tri Thức Biên Phi Tập Trung

Hạ tầng Intelligence vận hành theo cơ chế phi tập trung (Decentralized). Một "Trạm Tri Thức gốc" được xây dựng và sau đó nhân bản ra hàng ngàn thiết bị Edge Nodes chạy offline với chi phí biên tiệm cận 0.

### 1. Phần Lõi Tri Thức (Local Knowledge Base)
Từ chối sự phụ thuộc vào dữ liệu đám mây chung chung, cơ sở dữ liệu (Vector DB) tại biên được nạp chuyên biệt các tài sản "Di sản" (Legacy) và "Trí tuệ" (Wisdom):
* Lịch sử, địa lý, văn hóa dân gian bản địa.
* Kỹ năng STEM, tài liệu kỹ thuật cơ điện tử, tự động hóa chuẩn công nghiệp.
* Bài giảng tư duy logic và kỹ năng sinh tồn.

### 2. Động Cơ Suy Luận (Edge Inference Engine)
Sử dụng kiến trúc **Local RAG (Retrieval-Augmented Generation)** kết hợp tối ưu hóa vi kiến trúc:
* **Small Language Models (SLMs):** Tận dụng mã nguồn mở như Gemma-2-2B-IT hoặc Qwen-2.5-1.5B đã được lượng tử hóa (INT8/INT4) để chạy nhẹ nhàng trên các Mini-PC tiêu thụ dòng siêu thấp.
* **Vector DB Cục bộ:** Tích hợp FAISS hoặc ChromaDB chạy trực tiếp trên bộ nhớ flash (thẻ nhớ/SSD) của thiết bị biên.

---

## 🛠️ Kiến Trúc Khởi Tạo "Người Truyền Tri Thức" (Persona Agent)

Dưới đây là mô hình mã nguồn lõi (`persona_agent.py`) sử dụng Google AI Edge (LiteRT/MediaPipe) để thiết lập Bộ lọc Socrates ngay tại biên:

```python
import os
from mediapipe.tasks import python
from mediapipe.tasks.python import genai

# 1. Tải mô hình SLM lượng tử hóa (Offline Model)
# Đặt file mô hình trực tiếp trên thiết bị biên để tối ưu I/O
model_path = "models/gemma-2b-it-cpu-int4.bin"

# 2. Cấu hình bộ não AI tại biên (Tối ưu RAM & Nhiệt độ)
options = genai.LLMInferenceOptions(
    model_asset_path=model_path,
    max_tokens=512,       # Giới hạn token để tiết kiệm RAM trên các bo mạch nhúng
    temperature=0.7,      # Cân bằng giữa tính chính xác và sự thấu cảm sư phạm
    top_k=40
)

# 3. Khởi tạo Tác tử Kích hoạt Tư duy (Maieutic Agent)
with genai.LLMInference.create_from_options(options) as llm:
    print("🤖 Trạm Tri Thức Biên RFL đã sẵn sàng (Chế độ Offline Tự Chủ)!\n")
    
    # Thiết lập System Prompt - Bộ lọc Đạo đức và Khai phóng
    context = """Bạn là một người dẫn dắt (Mentor) thông thái, tuân thủ 'Nghệ thuật không nổi giận'.
    Nhiệm vụ của bạn là truyền dạy tri thức lịch sử, khoa học và công nghệ cho thế hệ trẻ Việt Nam.
    Nguyên tắc: Không bao giờ làm thay bài tập hay đưa code hoàn chỉnh. Hãy gợi ý, đặt câu hỏi phản biện 
    để kích thích tư duy tự chủ của học sinh. Trả lời ngắn gọn, súc tích và bao dung."""
    
    while True:
        user_input = input("🧒 Học viên: ")
        if user_input.lower() in ['thoát', 'exit', 'quit']: break
        
        prompt = f"{context}\n\nCâu hỏi của học viên: {user_input}\nTrả lời:"
        
        # Suy luận hoàn toàn trên CPU/Edge TPU nội bộ
        print("\n📚 Đang truy xuất DIKW-L...")
        response = llm.generate_response(prompt)
        
        print(f"\n👴 Mentor AI: {response}\n")
        print("-" * 50)
```
---

## 💎 Giá Trị Lãi Kép Cốt Lõi (Ecosystem ROI)

Zero Digital Divide: Xóa nhòa khoảng cách số. Một đứa trẻ ở vùng cao không có 4G vẫn có thể tiếp cận sự dẫn dắt tư duy đỉnh cao ngay trên một trạm container thư viện.

Bảo Tồn Bản Sắc: Tri thức được phản hồi 100% bằng tiếng Việt chuẩn mực, không bị pha loãng bởi các thuật toán thương mại đám mây.

Chi Phí Biên Bằng 0: Hạ tầng (CAPEX) chỉ đầu tư một lần. Càng nhiều người dùng, mô hình càng tối ưu. Dễ dàng nhân bản hàng vạn trạm từ thành thị đến bản làng thông qua tệp ảnh Docker tinh gọn.

---

## 🏗️ Kiến Trúc Cốt Lõi

Phân hệ AI của RFL không thiết kế để trả lời hộ, mà để định tuyến tư duy. Vui lòng nắm vững cấu trúc 4 tầng của lõi trí tuệ trước khi đóng góp mã nguồn:

👉 **[Đọc Kiến Trúc Lõi Trí Tuệ Thích Ứng (Adaptive Intelligence Core)](adaptive-intelligence-core.md)**