# [IT3323] Xây dựng chương trình dịch

> Đinh Văn Phạm Việt - 20235870  
> Mã lớp: 171159 | Giảng viên: TS. Nguyễn Thị Thu Hương

Mã nguồn các bài thực hành xây dựng chương trình dịch cho ngôn ngữ KPL.

## Hướng dẫn

Mở terminal tại thư mục của từng bài và chạy lệnh biên dịch tương ứng:

- **Lab01 - Scanner** (`Lab01_Scanner`):
  ```powershell
  gcc scanner.c charcode.c error.c reader.c token.c -o scanner.exe
  ```
- **Lab02 - Parser** (`Lab02_Parser`):
  ```powershell
  gcc main.c parser.c charcode.c error.c reader.c scanner.c token.c -o parser.exe
  ```
- **Lab03 - Bảng ký hiệu** (`Lab03_SymTab_1`):
  ```powershell
  gcc main.c symtab.c debug.c -o symtab.exe
  ```

Hoặc sử dụng Makefile trong từng thư mục (cần GCC và Make trong PATH):

```powershell
make
make run
make clean
```
