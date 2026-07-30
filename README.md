# Hướng dẫn biên dịch báo cáo (Compilation Guide)

Dự án này chứa mã nguồn LaTeX cho báo cáo: **A Comparative Study of BERT, LSTM, and Hybrid BERT-LSTM Models for Vietnamese Sentiment Analysis**.

## Yêu cầu môi trường (Prerequisites)
Để biên dịch được mã nguồn, máy tính của bạn cần cài đặt một trong các bản phân phối LaTeX sau (bao gồm sẵn công cụ `latexmk`):
- **Windows:** [MiKTeX](https://miktex.org/) hoặc [TeX Live](https://tug.org/texlive/)
- **macOS:** [MacTeX](https://tug.org/mactex/)
- **Linux:** `texlive-full`

## Hướng dẫn biên dịch (How to compile)

### Cách 1: Sử dụng Terminal / Command Line (Khuyên dùng)
Để biên dịch mã nguồn `main.tex` và tự động liên kết danh mục tài liệu tham khảo (`references.bib`), bạn hãy mở Terminal (hoặc Command Prompt) tại thư mục chứa dự án và chạy lệnh duy nhất sau:

```bash
latexmk -pdf main.tex
```

**💡 Lệnh này hoạt động như thế nào?**
Thay vì phải gõ thủ công chu trình 4 lệnh (`pdflatex` $\rightarrow$ `bibtex` $\rightarrow$ `pdflatex` $\rightarrow$ `pdflatex`), `latexmk` là một công cụ thông minh sẽ tự động phân tích mã nguồn và chạy lặp lại các công cụ cần thiết với số lần chuẩn xác để tạo ra file PDF hoàn chỉnh cùng hệ thống trích dẫn không bị lỗi.

### Cách 2: Sử dụng VS Code
Nếu bạn dùng trình soạn thảo Visual Studio Code:
1. Cài đặt extension **LaTeX Workshop**.
2. Nhấn `Ctrl + Shift + P` (hoặc `Cmd + Shift + P` trên macOS).
3. Tìm và chọn `LaTeX Workshop: Build with recipe`.
4. Chọn **latexmk 🔃**.

## Dọn dẹp file tạm (Cleaning auxiliary files)
Quá trình biên dịch LaTeX thường sinh ra nhiều file tạm (như `.aux`, `.bbl`, `.log`,...). Để dọn dẹp thư mục làm việc, hãy chạy lệnh:

```bash
latexmk -c
```
Lệnh này sẽ xóa các file tạm mà vẫn giữ lại mã nguồn (`.tex`, `.bib`) và file `.pdf` cuối cùng.
