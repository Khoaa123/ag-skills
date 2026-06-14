# AG KIT & AGENT-SKILLS

Bộ template AI Agent đi kèm Skills, Agents, và Workflows — kết hợp giữa Antigravity-Kit và addyosmani/agent-skills. Tích hợp sẵn Coordinator Mode, Bộ nhớ Dài hạn (Persistent Memory), và Nén Ngữ cảnh (Context Compression).

🇬🇧 **[English Version (Bản Tiếng Anh)](./README.md)**

---

## ⚡ Bắt đầu nhanh

Cài đặt và khởi tạo AG Kit để tích hợp thư mục cấu hình chuyên sâu `.agents/` trực tiếp vào dự án cục bộ của bạn.

### Cách 1: Chạy trực tiếp (Khuyên dùng)

```bash
npx @vudovn/ag-kit init
```

### Cách 2: Cài đặt toàn cục (Global)

```bash
npm install -g @vudovn/ag-kit
ag-kit init
```

---

## 🌍 Cấu hình Symlink Toàn cục (Global Shared Setup)

Nếu bạn làm việc trên nhiều dự án khác nhau và muốn tránh sao chép thư mục `.agents/` lặp đi lặp lại, bạn có thể tập trung hóa cấu hình AG Kit và sử dụng các liên kết tượng trưng (Symbolic Links).

1. **Cài đặt tập trung** (ví dụ: tạo thư mục toàn cục tại `~/.ag-kit`):
   ```bash
   mkdir -p ~/.ag-kit && cd ~/.ag-kit
   npx @vudovn/ag-kit init
   ```

2. **Liên kết cục bộ** từ thư mục gốc của dự án bạn đang làm việc:
   - **macOS / Linux:**
     ```bash
     ln -s ~/.ag-kit/.agents .agent
     ```
   - **Windows (CMD - Chạy với quyền Administrator):**
     ```cmd
     mklink /D .agents "%USERPROFILE%\.ag-kit\.agents"
     ```
   - **Windows (PowerShell - Chạy với quyền Administrator):**
     ```powershell
     New-Item -ItemType SymbolicLink -Path ".agents" -Target "$env:USERPROFILE\.ag-kit\.agents"
     ```

---

## ⚠️ Lưu ý Quan trọng về `.gitignore`

Nếu bạn đang sử dụng các trình soạn thảo mã nguồn tích hợp sẵn AI (như **Cursor** hoặc **Windsurf**), việc thêm thư mục `.agents/` vào file `.gitignore` sẽ khiến trình phân tích ngôn ngữ của trình soạn thảo không thể lập chỉ mục (index) các workflow. Điều này sẽ làm mất tính năng gợi ý tự động (autocomplete) cho các lệnh slash (ví dụ: `/plan`, `/debug`).

### Giải pháp tối ưu:
Để thư mục `.agents/` vừa không bị đẩy lên Git remote, vừa giữ nguyên khả năng hỗ trợ đắc lực từ AI editor:
1. Đảm bảo thư mục `.agents/` **KHÔNG** nằm trong file `.gitignore` của dự án.
2. Thay vào đó, hãy thêm `.agents/` vào file loại trừ cục bộ của Git: `.git/info/exclude`

---

## 📦 Các thành phần đi kèm

AG Kit đóng gói sẵn kho tri thức chuyên sâu cho từng domain cụ thể, các vai trò Agent chuyên biệt, và các quy trình phát triển tự động hóa tối ưu cho các công cụ lập trình AI hiện đại, kết hợp với các kỹ năng kỹ thuật từ `agent-skills`.

| Thành phần | Số lượng | Mô tả |
| :--- | :--- | :--- |
| **Agents** | 20 | Các chuyên gia AI độc lập (Frontend, Backend, Security, PM, QA, v.v.) |
| **Skills** | 53 | Các mô-đun tri thức chuyên sâu tải điều kiện (bao gồm 8 skill từ `agent-skills`) |
| **Workflows** | 18 | Quy trình tương tác tự động hóa lập trình viên dạng lệnh Slash (bao gồm 5 workflow mới) |

---

## 🛠️ Hướng dẫn Sử dụng

### 1. Cơ chế Tự động Điều hướng Agent (Zero-Setup)

Bạn không cần chỉ định Agent một cách thủ công. Hệ thống sẽ tự động phân tích yêu cầu của bạn, điều hướng thông minh đến đúng chuyên gia phù hợp và áp dụng các nguyên tắc lập trình của họ ngay lập tức:

```
You: "Thêm xác thực JWT vào API đăng nhập"
Agent: Applying @security-auditor + @backend-specialist...

You: "Căn giữa nút thanh toán và sửa lỗi giao diện tối"
Agent: Using @frontend-specialist...
```

### 2. Các Quy trình Tương tác (Slash Commands)

Thực hiện các quy trình phát triển mã nguồn bài bản bằng cách gõ trực tiếp các lệnh slash trong khung trò chuyện với AI:

| Lệnh | Mô tả chi tiết |
| :--- | :--- |
| `/brainstorm` | Lên ý tưởng, phân tích kiến trúc và giải pháp tối ưu trước khi viết code |
| `/build` | **MỚI** Triển khai code cuốn chiếu theo TDD (hỗ trợ `/build auto` chạy tự động) |
| `/code-simplify` | **MỚI** Tối giản hóa code phức tạp dựa trên Chesterton's Fence & Rule of 500 |
| `/coordinate` | Điều phối song song nhiều Agent chuyên gia cho các tác vụ kiểm tra phức tạp |
| `/create` | Tạo mới một tính năng hoặc xây dựng toàn bộ ứng dụng từ đầu |
| `/debug` | Kích hoạt quy trình gỡ lỗi chuyên sâu và có bằng chứng xác thực |
| `/deploy` | Thực hiện các kiểm tra an toàn pre-flight và triển khai lên production |
| `/enhance` | Thêm mới hoặc cải tiến các tính năng trong codebase hiện tại một cách an toàn |
| `/plan` | Lập kế hoạch chi tiết và tạo checklist triển khai công việc |
| `/preview` | Khởi động, dừng hoặc kiểm tra trạng thái máy chủ xem trước cục bộ |
| `/remember` | Ghi nhớ các quy chuẩn riêng của dự án vào bộ nhớ dài hạn |
| `/ship` | **MỚI** Kiểm tra phát hành thông qua 3 subagent chạy song song và rollback plan |
| `/spec` | **MỚI** Viết tài liệu đặc tả (PRD) cấu trúc trước khi code |
| `/status` | Báo cáo chi tiết tiến độ công việc đang chạy của AI |
| `/test` | Tự động tạo và thực thi các bộ kiểm thử (test suite) toàn diện |
| `/verify` | Xác minh code chạy thực tế thông qua checklist và build validation |
| `/webperf` | **MỚI** Kiểm tra và đánh giá hiệu năng Core Web Vitals của trang Web |

---

## 🧠 Triết lý Kiến trúc Cốt lõi

AG Kit được xây dựng dựa trên các mô hình thiết kế AI Agent đã qua kiểm chứng thực tế, giúp giảm lượng tiêu thụ token từ **13% đến 33%** đồng thời cải thiện chất lượng phản hồi:

*   **Coordinator Mode:** Cơ chế điều phối đa tác vụ song song, tránh việc thử lại tuần tự tốn kém tài nguyên.
*   **Bộ nhớ Dài hạn (Persistent Memory):** Cơ chế phân loại và lập chỉ mục qua `MEMORY.md`, loại bỏ việc phải giải thích lại các quy tắc dự án trong mỗi phiên chat mới.
*   **Nén Ngữ cảnh (Context Compression):** Tự động tóm tắt và thu gọn dữ liệu lịch sử để ngăn chặn hiện tượng tràn bộ nhớ trong các phiên làm việc kéo dài.
*   **Kích hoạt Skill có Điều kiện:** Chỉ tải các nguyên tắc lập trình có liên quan đến ngữ cảnh hiện tại nhờ cấu hình frontmatter thông minh, giữ cho cửa sổ ngữ cảnh luôn nhẹ nhàng nhất.

---

## 📚 Tham chiếu & Bản quyền

AG Kit là sản phẩm nghiên cứu và phát triển độc lập trong lĩnh vực kỹ nghệ prompt và luật thiết kế markdown. Dự án được tối ưu hóa dựa trên việc phân tích các mô hình AI Agent hàng đầu trong môi trường production:
*   *Không sao chép bất kỳ mã nguồn hay file bảo mật thương mại nào.*
*   Toàn bộ mã nguồn, cấu hình và kịch bản đều là phiên bản viết mới hoàn toàn, được phân phối dưới dạng mã nguồn mở theo giấy phép MIT.



---

## 📄 Giấy phép

Được phát hành dưới [Giấy phép MIT](LICENSE) © [Vudovn](https://github.com/vudovn).
