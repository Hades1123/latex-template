# Template báo cáo LaTeX (tiếng Việt)

Template báo cáo đồ án / bài tập lớn của Khoa KH&KT Máy tính – ĐH Bách khoa TP.HCM,
rút ra từ báo cáo đồ án chuyên ngành. Gồm trang bìa, lời cảm ơn/cam đoan/tóm tắt,
mục lục + danh mục bảng/hình, 5 chương mẫu, tài liệu tham khảo (biblatex/biber).

## Bắt đầu nhanh

1. Sửa **`config/metadata.tex`**: tên đề tài, loại báo cáo, GVHD, danh sách sinh viên, niên khóa.
2. Sửa nội dung trong `intro/` và `content/chapterN/`.
3. Thêm tài liệu vào `references.bib`, trích dẫn bằng `\cite{key}`.
4. Biên dịch (cần TeX Live đầy đủ, `latexmk`, `biber`):

```bash
latexmk main.tex      # xuất build/main.pdf
latexmk -C            # dọn file trung gian
```

Trong VS Code: cài extension **LaTeX Workshop**, mở `main.tex`, Ctrl+S để tự build.

## Cấu trúc

| Đường dẫn | Vai trò |
|---|---|
| `main.tex` | Điểm vào: thứ tự cấu hình và các chương |
| `config/metadata.tex` | **Thông tin báo cáo** (chỉ sửa file này cho bìa/header/footer) |
| `config/packages.tex` | Các gói sử dụng |
| `config/format.tex` | Lề, cỡ chữ 13pt, giãn dòng 1.5 |
| `config/section.tex` | Đánh số: chương I, II… / mục 1, 2… / 1.1, 1.2…; định dạng mục lục |
| `config/code.tex` | Kiểu hiển thị mã nguồn (`listings`) |
| `config/usecase.tex` | Macro bảng đặc tả use case (`ucspec`, `\ucrow`, `ucsteps`, `\ucdiagrams`, `\chuachot`) |
| `partials/title.tex` | Trang bìa (viền TikZ + logo) |
| `partials/header_footer.tex` | Header logo + footer; số trang La Mã (đầu) / `Trang x/N` (nội dung) |
| `intro/` | Lời cảm ơn, lời cam đoan, tóm tắt |
| `content/chapter1…5/` | Các chương, mỗi chương một file `\section{...}` |
| `pictures/` | Logo trường |

## Lưu ý

- `\parindent = 0`: ngắt đoạn bằng dòng trống hoặc `\\`.
- Mã nguồn trong `lstlisting` không hiển thị được ký tự tiếng Việt có dấu; viết code/comment không dấu.
- Không cần use case? Xóa `\input{config/usecase}` trong `main.tex` và `content/chapter2/example-usecase.tex`.
- Thêm chương: tạo file mới trong `content/` và `\input` vào `main.tex`. Phụ lục: bỏ comment khối `\appendix` ở cuối `main.tex`.
- Đổi sang trường/khoa khác: sửa `config/metadata.tex` và thay ảnh trong `pictures/` (giữ tên `logobk.png`, `logobk.jpg`).
