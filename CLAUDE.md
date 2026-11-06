# CLAUDE.md

Báo cáo LaTeX tiếng Việt (template HCMUT). Xem `README.md` cho cấu trúc thư mục và cách build.

## Build

```bash
latexmk main.tex   # xuất build/main.pdf (cấu hình trong .latexmkrc)
```

## Quy tắc viết file .tex

- **Không viết cả đoạn văn trên một dòng.** Mỗi dòng tối đa 100 ký tự; ngắt dòng ở khoảng trắng
  giữa các từ. Dòng trống mới là ngắt đoạn, xuống dòng đơn thì LaTeX coi như dấu cách.
- Thụt lề 2 dấu cách cho nội dung trong `\begin{...}...\end{...}` và `\item`.
- Sau khi tạo/sửa file `.tex`, chạy formatter rồi build lại để kiểm tra:

  ```bash
  tex-fmt <file.tex>          # một file
  find . -name '*.tex' -not -path './build/*' -exec tex-fmt {} +   # toàn bộ (không đụng .bib)
  ```

  Cấu hình formatter nằm ở `tex-fmt.toml` (`wraplen = 100`, `tabsize = 2`).
- Không ngắt dòng bên trong `verbatim`/`lstlisting`, URL, hay key của `\cite{...}`/`\label{...}`.
