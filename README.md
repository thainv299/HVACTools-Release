# 📊 HVAC Tools - Hướng Dẫn Sử Dụng Phần Mềm

**HVAC Tools (Thermal Test Analyzer)** là ứng dụng chuyên dụng dành cho kỹ sư thử nghiệm HVAC ô tô, hỗ trợ phân tích dữ liệu nhiệt độ, vẽ biểu đồ tương tác thời gian thực, đánh giá tiêu chí bài test (Acceptance Criteria) tại các mốc Set Point và xuất báo cáo tự động.

---

## 📑 Mục Lục
1. [Khởi Động & Nạp Dữ Liệu](#1-khởi-động--nạp-dữ-liệu)
2. [Quản Lý & Phân Nhóm Cảm Biến](#2-quản-lý--phân-nhóm-cảm-biến)
3. [Tùy Chỉnh Biểu Đồ & Trục Thời Gian](#3-tùy-chỉnh-biểu-đồ--trục-thời-gian)
4. [Cấu Hình Điểm Mốc Set Point](#4-cấu-hình-điểm-mốc-set-point)
5. [Chọn Tín Hiệu & Quản Lý Preset Biểu Đồ](#5-chọn-tín-hiệu--quản-lý-preset-biểu-đồ)
6. [Bảng Phân Tích Set Point & Cài Đặt Bài TEST](#6-bảng-phân-tích-set-point--cài-đặt-bài-test)
7. [Tương Tác Trên Đồ Thị & Phím Tắt](#7-tương-tác-trên-đồ-thị--phím-tắt)
8. [Xuất Báo Cáo & Cập Nhật Ứng Dụng](#8-xuất-báo-cáo--cập-nhật-ứng-dụng)

---

## 1. Khởi Động & Nạp Dữ Liệu

- **Mở tệp CSV**: Nhấn nút **`📂 Chọn Tệp CSV`** để chọn tệp log dữ liệu thử nghiệm từ máy tính.
- **Dữ liệu mẫu**: Nhấn **`📊 Nạp Dữ Liệu Mẫu`** để nạp nhanh tệp `data_thermal.csv` có sẵn để dùng thử.
- **Tần số lấy mẫu (Sampling Rate)**: Mặc định là `3.0 Hz` (3 mẫu/giây). Nếu tệp log không có cột `Time`, phần mềm sẽ tự động tính toán thời gian trôi qua dựa trên tần số này.
- **Phòng vệ dữ liệu tự động**: Phần mềm tự động hỗ trợ các bảng mã (UTF-8, Latin-1, CP1252) và tự động nhận diện nhiều định dạng ngày giờ khác nhau.

---

## 2. Quản Lý & Phân Nhóm Cảm Biến

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

## 3. Tùy Chỉnh Biểu Đồ & Trục Thời Gian

Tại **Nhóm 3 (Tùy Chỉnh Trục & Hiển Thị)**:
- **Tiêu đề đồ thị**: Nhập tên bài test để hiển thị trên đỉnh biểu đồ.
- **Đơn vị thời gian trục X**: Chọn hiển thị theo **`Phút (min)`**, **`Giây (s)`** hoặc **`Giờ (h)`**.
- **Bước nhảy lưới thời gian (Interval)**: Nhập khoảng cách giữa các vạch chia lưới (VD: `2.0` phút).
- **Giới hạn trục X (Xmin - Xmax)**: Nhập khoảng thời gian cần phóng to hoặc để `Auto` để tự động bao phủ toàn bộ bài test.
- **Trục Y chính / phụ**: Gán đơn vị cho trục Y bên trái và trục Y bên phải (hỗ trợ hiển thị đồng thời Nhiệt độ °C và Vận tốc xe kph).
- **Trục Y từ 0 / Đánh dấu Max-Min**: Tùy chọn cố định gốc tọa độ và hiển thị đỉnh cực trị trên đồ thị.

---

## 4. Cấu Hình Điểm Mốc Set Point

Tại **Nhóm 4 (Cấu Hình Điểm Mốc)**:
- **Số lượng điểm Set Point**: Nhập số mốc thời gian cần đánh giá (từ `1` đến `10` điểm: *A, B, C, D...*).
- **Vị trí thời gian**: Nhập mốc thời gian cụ thể (theo đơn vị phút/giây đang chọn) cho từng điểm Set Point.
- **Vẽ lên đồ thị**: Tích chọn để hiển thị các đường gióng dọc đứt nét kèm cờ đánh dấu Set Point trực tiếp trên biểu đồ.

---

## 5. Chọn Tín Hiệu & Quản Lý Preset Biểu Đồ

- **Chọn tín hiệu vẽ**: Tại **Nhóm 5**, nhấp chọn các nhóm đường trung bình hoặc tín hiệu vận tốc xe để hiển thị trên đồ thị.
- **💾 Lưu Preset**: Lưu toàn bộ cấu hình bài test hiện tại (nhóm cảm biến, màu sắc, đơn vị, setpoint, tín hiệu chọn) ra tệp `.json`.
- **📂 Nạp Preset**: Nạp lại cấu hình đã lưu để tái sử dụng ngay cho các lần thử nghiệm tiếp theo.

---

## 6. Bảng Phân Tích Set Point & Cài Đặt Bài TEST

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

## 7. Tương Tác Trên Đồ Thị & Phím Tắt

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

## 8. Xuất Báo Cáo & Cập Nhật Ứng Dụng

- **Xuất dữ liệu đã tính toán**: Nhấn **`📤 Xuất Dữ Liệu`** để xuất toàn bộ DataFrame (bao gồm các cột trung bình nhóm và thời gian trôi qua `Elapsed_s`, `Elapsed_min`, `Elapsed_hr`) ra định dạng Excel `.xlsx` hoặc `.csv`.
- **Xuất bảng phân tích**: Trong cửa sổ Set Point Analysis, nhấn **`Xuất Bảng Ra Excel (.xlsx)`** để xuất bảng tổng hợp và đánh giá kết quả.
- **Kiểm tra bản cập nhật**:
  - Ứng dụng tự động kiểm tra phiên bản mới từ GitHub Releases khi khởi động.
  - Khi có bản nâng cấp, nút thông báo đỏ **`🔴 Bản mới vX.X.X`** sẽ xuất hiện ở góc trên bên phải. Nhấn vào để xem Release Notes chi tiết và tải bản cập nhật chỉ với 1 click.
- **Nhật ký sự cố (Crash Logs)**: File log được lưu tự động trong thư mục `logs/` và sẽ tự động được dọn dẹp sau 7 ngày để tối ưu dung lượng máy.

---

*Phát triển bởi THAINV30.* dựa trên nền tảng của tuannq38
