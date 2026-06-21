# ag-skills

Bộ cấu hình không gian làm việc chứa các mẫu AI Agent chuyên biệt, Kỹ năng điều kiện (Skills) và Quy trình tự động (Workflows). Kho lưu trữ này là bản fork kết hợp giữa **antigravity-kit** và **addyosmani/agent-skills**, nhằm bắt buộc AI tuân thủ quy trình kỹ nghệ phần mềm chuyên nghiệp.

🇬🇧 **[English Version (Bản Tiếng Anh)](./README.md)**

---

## 📦 Các thành phần đi kèm

Thư mục `.agents/` đóng gói sẵn các chỉ dẫn để định hình hành vi cho AI:

| Thành phần | Số lượng | Mô tả |
| :--- | :--- | :--- |
| **Agents** | 20 | Các chuyên gia AI độc lập (Frontend, Backend, Security, PM, QA, v.v.) |
| **Skills** | 53 | Các mô-đun tri thức chuyên sâu tải có điều kiện để tối ưu hóa ngữ cảnh |
| **Workflows** | 19 | Quy trình tương tác tự động hóa lập trình viên dạng lệnh Slash (bao gồm `/ship-fast`) |

---

## 🛠️ Hướng dẫn Sử dụng trong IDE (Cursor, Windsurf, Antigravity)

### 1. Liên kết tượng trưng (Symlink - Khuyên dùng)
Để chia sẻ chung một cấu hình cho nhiều dự án cục bộ khác nhau, bạn có thể tạo symlink dẫn đến thư mục `.agents/`:

- **macOS / Linux:**
  ```bash
  ln -s /path/to/ag-skills/.agents /path/to/project/.agents
  ```
- **Windows (PowerShell - Chạy với quyền Administrator):**
  ```powershell
  New-Item -ItemType SymbolicLink -Path "C:\path\to\project\.agents" -Target "C:\path\to\ag-skills\.agents"
  ```

### 2. Hỗ trợ tự động gợi ý lệnh (Autocomplete)
Để giữ thư mục `.agents/` không bị đẩy lên Git remote mà vẫn giữ khả năng gợi ý lệnh của Cursor/Windsurf:
1. Đảm bảo thư mục `.agents/` **KHÔNG** nằm trong file `.gitignore`.
2. Thay vào đó, hãy thêm `.agents/` vào file loại trừ cục bộ của Git: `.git/info/exclude`

---

## 📥 Các lệnh Slash khả dụng

Bạn có thể chạy các quy trình này bằng cách gõ trực tiếp các lệnh slash trong khung chat AI:

| Lệnh | Mô tả chi tiết |
| :--- | :--- |
| `/spec` | Viết tài liệu đặc tả (PRD) cấu trúc trước khi code |
| `/plan` | Lập kế hoạch chi tiết và tạo checklist triển khai công việc |
| `/build` | Triển khai code cuốn chiếu theo TDD (hỗ trợ `/build auto` chạy tự động) |
| `/test` | Tự động tạo và thực thi các bộ kiểm thử (test suite) toàn diện |
| `/verify` | Xác minh code chạy thực tế thông qua checklist và build validation |
| `/code-simplify` | Tối giản hóa code phức tạp dựa trên Chesterton's Fence |
| `/ship-fast` | **MỚI** Kiểm tra phát hành nhanh chỉ trên các thay đổi Git đang Staged |
| `/ship` | Kiểm tra phát hành toàn diện trên toàn bộ dự án |
| `/debug` | Kích hoạt quy trình gỡ lỗi chuyên sâu và có bằng chứng xác thực |
| `/coordinate` | Điều phối song song nhiều Agent chuyên gia cho các tác vụ phức tạp |
| `/remember` | Ghi nhớ các quy chuẩn riêng của dự án vào bộ nhớ dài hạn |
| `/webperf` | Đánh giá hiệu năng Core Web Vitals của trang Web qua Lighthouse |

---

## 📄 Giấy phép

Phát hành dưới [Giấy phép MIT](LICENSE) © [Vudovn](https://github.com/vudovn).
