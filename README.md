# 📊 HVAC Tools - Hướng Dẫn Sử Dụng Phần Mềm
---
9
## 📑 Mục Lục
1. [Hướng dẫn tải ứng dụng ](#1-hướng-dẫn--tải-ứng-dụng)
2. [Khởi Động & Nạp Dữ Liệu](#2-khởi-động--nạp-dữ-liệu)
3. [Quản Lý & Phân Nhóm Cảm Biến](#3-quản-lý--phân-nhóm-cảm-biến)
4. [Tùy Chỉnh Biểu Đồ & Trục Thời Gian](#4-tùy-chỉnh-biểu-đồ--trục-thời-gian)
5. [Cấu Hình Điểm Mốc Set Point](#5-cấu-hình-điểm-mốc-set-point)
6. [Chọn Tín Hiệu & Quản Lý Preset Biểu Đồ](#6-chọn-tín-hiệu--quản-lý-preset-biểu-đồ)
8. [Bảng Phân Tích Set Point & Cài Đặt Bài TEST](#7-bảng-phân-tích-set-point--cài-đặt-bài-test)
8. [Tương Tác Trên Đồ Thị & Phím Tắt](#8-tương-tác-trên-đồ-thị--phím-tắt)
9. [Xuất Báo Cáo & Cập Nhật Ứng Dụng](#9-xuất-báo-cáo--cập-nhật-ứng-dụng)

---

## 1. Hướng dẫn tải ứng dụng
- **Bước 1** : Click vào phần HVAC_Tools ở bên dưới Release
![Bước 1](assets/huongdan1.jpg)

- **Bước 2** : Click vào HVAC_Tools.zip để tải file nén phần mềm
![Bước 2](assets/huongdan2.jpg)

- **Bước 3** : Giải nén ứng dụng
![Bước 3](assets/huongdan3.jpg)

- **Bước 4** : Click chọn file HVACTools.exe để khởi chạy phần mềm
### Lưu ý : Lần đầu tiên chạy phần mềm sẽ phải giải nén các thư viện, nên sẽ mất khoảng vài giây.
![Bước 4](assets/huongdan4.jpg)
## 2. Khởi Động & Nạp Dữ Liệu

- **Mở tệp CSV**: Nhấn nút **`📂 Chọn Tệp CSV`** để chọn tệp log dữ liệu thử nghiệm từ máy tính.
- **Dữ liệu mẫu**: Nhấn **`📊 Nạp Dữ Liệu Mẫu`** để nạp nhanh tệp `data_thermal.csv` có sẵn để dùng thử.
- **Tần số lấy mẫu (Sampling Rate)**: Mặc định là `3.0 Hz` (3 mẫu/giây). Nếu tệp log không có cột `Time`, phần mềm sẽ tự động tính toán thời gian trôi qua dựa trên tần số này.
- **Phòng vệ dữ liệu tự động**: Phần mềm tự động hỗ trợ các bảng mã (UTF-8, Latin-1, CP1252) và tự động nhận diện nhiều định dạng ngày giờ khác nhau.

---

## 3. Quản Lý & Phân Nhóm Cảm Biến

Giao diện cột bên trái (**Nhóm 2**) cho phép gom các cảm biến nhiệt độ riêng lẻ thành các nhóm đại diện (VD: *Nhóm Vent, Nhóm Head, Nhóm Floor*):

- **Tạo nhóm mới**:
  1. Nhập **Tên nhóm** (VD: `Head`).
  2. Chọn **Đơn vị đo** (Mặc định `Temp (°C)`).
  3. Chọn các cảm biến từ danh sách **"Cảm biến chưa gán"** (giữ `Ctrl` hoặc `Shift` để chọn nhiều).
  4. Nhấn **`➕ Thêm Nhóm`**.
  *(💡 Màu đại diện sẽ tự động được chọn ngẫu nhiên đẹp mắt và tự đổi màu cho nhóm tiếp theo)*.
- **Bổ sung cảm biến vào nhóm đã có**: Chọn cảm biến bên dưới, để trống ô tên nhóm, chọn nhóm trong cây cấu trúc rồi nhấn **`➕ Thêm Nhóm`**.
- **Kéo thả cảm biến**: Bạn có thể kéo thả trực tiếp cảm biến giữa các nhóm trong cây cấu trúc để điều chỉnh nhanh.
- **Đổi màu / Đổi đơn vị / Xóa nhóm**:
  - Nhấp chuột phải vào tên nhóm trong cây cấu trúc để chọn menu ngữ cảnh.
  - Nhấp trực tiếp vào ô màu nhỏ bên phải tên nhóm để đổi màu đường biểu diễn.

---

## 4. Tùy Chỉnh Biểu Đồ & Trục Thời Gian

Tại **Nhóm 3 (Tùy Chỉnh Trục & Hiển Thị)**:
- **Tiêu đề đồ thị**: Nhập tên bài test để hiển thị trên đỉnh biểu đồ.
- **Đơn vị thời gian trục X**: Chọn hiển thị theo **`Phút (min)`**, **`Giây (s)`** hoặc **`Giờ (h)`**.
- **Bước nhảy lưới thời gian (Interval)**: Nhập khoảng cách giữa các vạch chia lưới (VD: `2.0` phút).
- **Giới hạn trục X (Xmin - Xmax)**: Nhập khoảng thời gian cần phóng to hoặc để `Auto` để tự động bao phủ toàn bộ bài test.
- **Trục Y chính / phụ**: Gán đơn vị cho trục Y bên trái và trục Y bên phải (hỗ trợ hiển thị đồng thời Nhiệt độ °C và Vận tốc xe kph).
- **Trục Y từ 0 / Đánh dấu Max-Min**: Tùy chọn cố định gốc tọa độ và hiển thị đỉnh cực trị trên đồ thị.

---

## 5. Cấu Hình Điểm Mốc Set Point

Tại **Nhóm 4 (Cấu Hình Điểm Mốc)**:
- **Số lượng điểm Set Point**: Nhập số mốc thời gian cần đánh giá (từ `1` đến `10` điểm: *A, B, C, D...*).
- **Vị trí thời gian**: Nhập mốc thời gian cụ thể (theo đơn vị phút/giây đang chọn) cho từng điểm Set Point.
- **Vẽ lên đồ thị**: Tích chọn để hiển thị các đường gióng dọc đứt nét kèm cờ đánh dấu Set Point trực tiếp trên biểu đồ.

---

## 6. Chọn Tín Hiệu & Quản Lý Preset Biểu Đồ

- **Chọn tín hiệu vẽ**: Tại **Nhóm 5**, nhấp chọn các nhóm đường trung bình hoặc tín hiệu vận tốc xe để hiển thị trên đồ thị.
- **💾 Lưu Preset**: Lưu toàn bộ cấu hình bài test hiện tại (nhóm cảm biến, màu sắc, đơn vị, setpoint, tín hiệu chọn) ra tệp `.json`.
- **📂 Nạp Preset**: Nạp lại cấu hình đã lưu để tái sử dụng ngay cho các lần thử nghiệm tiếp theo.

---

## 7. Bảng Phân Tích Set Point & Cài Đặt Bài TEST

Nhấn nút **`📋 Bảng Phân Tích Set Point`** trên thanh công cụ đồ thị để mở cửa sổ phân tích chuyên sâu:

### A. Đọc kết quả phân tích
- Bảng hiển thị chi tiết giá trị của từng nhóm cảm biến tại chính xác các mốc thời gian Set Point ($A, B, C...$).
- **Cột Deviation Head / Vent**: Tự động tính chênh lệch nhiệt độ giữa các cảm biến ($\text{Max} - \text{Min}$) trong từng nhóm để đánh giá độ đồng đều.
- **Tốc độ thay đổi nhiệt độ ($\Delta T / \Delta t$)**: Hiển thị tốc độ làm lạnh/sưởi (°C/phút) giữa 2 mốc Set Point liên tiếp.

### B. Cài Đặt Bài TEST (`⚙️ Cài Đặt Bài TEST`)
Trong bảng phân tích, nhấn **`⚙️ Cài Đặt Bài TEST`** để thiết lập tiêu chí đánh giá PASS/FAIL:
- **Thiết lập điều kiện (Rules)**: Chọn nhóm cảm biến, chọn phép so sánh ($\le, <, \ge, >, =, \ne$) và nhập ngưỡng nhiệt độ yêu cầu tại từng Set Point.
- **📋 Sao chép luật**: Sao chép nhanh toàn bộ điều kiện của một Set Point sang tất cả các Set Point khác chỉ với 1 click.
- **💾 Lưu / 📂 Nạp Preset Bài TEST**: Lưu và nạp riêng bộ quy tắc tiêu chí đánh giá ra file `.json`.
- **Phím tắt Hoàn tác / Làm lại**:
  - `Ctrl + Z`: Hoàn tác thao tác vừa thực hiện.
  - `Ctrl + Shift + Z` hoặc `Ctrl + Y`: Làm lại thao tác vừa hủy.

---

## 8. Tương Tác Trên Đồ Thị & Phím Tắt

| Thao Tác | Phím Tắt / Chuột | Chức Năng |
| :--- | :--- | :--- |
| **Kéo mốc Set Point** | Bấm giữ chuột trái vào đường Set Point | Di chuyển trực tiếp mốc thời gian trên đồ thị (Bảng phân tích sẽ cập nhật tức thì) |
| **Phóng to / Thu nhỏ** | Cuộn chuột giữa HOẶC `Ctrl +` / `Ctrl -` | Zoom in / Zoom out theo vị trí con trỏ chuột |
| **Di chuyển đồ thị (Pan)** | Bấm giữ chuột phải hoặc nút Pan | Kéo trượt vùng hiển thị đồ thị |
| **Khôi phục góc nhìn** | Nhấn biểu tượng 🏠 (Home) | Đưa biểu đồ về kích thước đầy đủ ban đầu |
| **Hoàn tác (Undo)** | `Ctrl + Z` | Khôi phục lại thao tác cài đặt trước đó |
| **Làm lại (Redo)** | `Ctrl + Shift + Z` / `Ctrl + Y` | Làm lại thao tác vừa Undo |
| **Lưu nhanh đồ thị** | Biểu tượng 💾 (Save) trên toolbar | Lưu đồ thị thành tệp ảnh (.png, .jpg, .svg, .pdf) |

---

## 9. Xuất Báo Cáo & Cập Nhật Ứng Dụng

- **Xuất dữ liệu đã tính toán**: Nhấn **`📤 Xuất Dữ Liệu`** để xuất toàn bộ DataFrame (bao gồm các cột trung bình nhóm và thời gian trôi qua `Elapsed_s`, `Elapsed_min`, `Elapsed_hr`) ra định dạng Excel `.xlsx` hoặc `.csv`.
- **Xuất bảng phân tích**: Trong cửa sổ Set Point Analysis, nhấn **`Xuất Bảng Ra Excel (.xlsx)`** để xuất bảng tổng hợp và đánh giá kết quả.
- **Kiểm tra bản cập nhật**:
  - Ứng dụng tự động kiểm tra phiên bản mới từ GitHub Releases khi khởi động.
  - Khi có bản nâng cấp, nút thông báo đỏ **`🔴 Bản mới vX.X.X`** sẽ xuất hiện ở góc trên bên phải. Nhấn vào để xem Release Notes chi tiết và tải bản cập nhật chỉ với 1 click.
- **Nhật ký sự cố (Crash Logs)**: File log được lưu tự động trong thư mục `logs/` và sẽ tự động được dọn dẹp sau 7 ngày để tối ưu dung lượng máy.

---

*Phát triển bởi THAINV30.* dựa trên nền tảng của tuannq38
