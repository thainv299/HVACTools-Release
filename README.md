# 📊 HVAC Tools - Hướng Dẫn Sử Dụng Phần Mềm

---

## 📑 Mục Lục
1. [Hướng dẫn tải ứng dụng](#1-hướng-dẫn--tải-ứng-dụng)
2. [Khởi Động, Nạp & Quản Lý Dữ Liệu Tệp](#2-khởi-động-nạp--quản-lý-dữ-liệu-tệp)
3. [Quản Lý & Phân Nhóm Cảm Biến](#3-quản-lý--phân-nhóm-cảm-biến)
4. [Tùy Chỉnh Biểu Đồ & Trục Thời Gian](#4-tùy-chỉnh-biểu-đồ--trục-thời-gian)
5. [Cấu Hình Điểm Mốc Set Point](#5-cấu-hình-điểm-mốc-set-point)
6. [Chọn Tín Hiệu & Quản Lý Preset Biểu Đồ (Save As)](#6-chọn-tín-hiệu--quản-lý-preset-biểu-đồ-save-as)
7. [Vẽ Biểu Đồ Trên Giao Diện & Xử Lý Nền](#7-vẽ-biểu-đồ-trên-giao-diện--xử-lý-nền)
8. [Bảng Phân Tích Set Point & Tiêu Chí Đánh Giá](#8-bảng-phân-tích-set-point--tiêu-chí-đánh-giá)
9. [Tương Tác Trên Đồ Thị & Phím Tắt](#9-tương-tác-trên-đồ-thị--phím-tắt)
10. [Xuất Báo Cáo & Cập Nhật Ứng Dụng](#10-xuất-báo-cáo--cập-nhật-ứng-dụng)

---

## 1. Hướng dẫn tải ứng dụng
### - **Bước 1** : Click vào phần HVAC_Tools ở bên dưới Release

![Bước 1](assets/huongdan1.jpg)

### - **Bước 2** : Click vào HVAC_Tools.zip để tải file nén phần mềm

![Bước 2](assets/huongdan2.jpg)

### - **Bước 3** : Giải nén ứng dụng

![Bước 3](assets/huongdan3.jpg)

### - **Bước 4** : Click chọn file HVACTools.exe để khởi chạy phần mềm
### Lưu ý : Lần đầu tiên chạy phần mềm sẽ phải giải nén các thư viện, nên sẽ mất khoảng vài giây.

![Bước 4](assets/huongdan4.jpg)

---

## 2. Khởi Động, Nạp & Quản Lý Dữ Liệu Tệp

- **Nạp tệp mới (CSV / Excel)**: Nhấn nút **`📂 Chọn Tệp CSV / Excel`** trên thanh công cụ Header để nạp tệp dữ liệu thử nghiệm (hỗ trợ các định dạng `.csv`, `.xlsx`, `.xls`, `.xlsm`, `.xlsb`).
- **Tự động nhận diện Sheet Excel**: Nếu tệp Excel chứa từ 2 Sheet trở lên, phần mềm sẽ tự động bật hộp thoại cho phép bạn xem danh sách và chọn đúng Sheet dữ liệu cần phân tích.
- **Nạp nhiều tệp dữ liệu (Multi-file Comparison)**: 
  - Cho phép nạp đồng thời hoặc bổ sung tệp dữ liệu thứ 2, 3... vào bài phân tích để so sánh song song.
  - Mỗi tệp khi nạp vào sẽ được tự động gán tiền tố phân biệt (VD: `[F1]`, `[F2]`) cho các tên cảm biến.
  - Ứng dụng tự động quy đổi mốc thời gian của từng tệp về gốc thời gian tương đối $t=0$ giúp so sánh dữ liệu giữa các bài test chính xác.
- **Hộp thoại "Quản Lý Tệp 📁"**:
  - Nhấn nút **`Quản Lý Tệp 📁`** để mở bảng quản lý danh sách toàn bộ các tệp đã nạp trong phiên làm việc.
  - Cho phép chọn/thay đổi Sheet Excel riêng cho từng tệp hoặc xóa bỏ tệp bất kỳ khỏi bài phân tích.
  - **Cấu hình thời gian độc lập cho từng tệp**: Tùy chọn giữa chế độ **`📁 Cột Time từ tệp`** (sử dụng mốc thời gian thực trong log) hoặc **`⏱️ Tính theo Hz`** và nhập **Tần số lấy mẫu (Sampling Rate Hz)** riêng cho từng tệp mà không ảnh hưởng tới mốc thời gian của các tệp khác.
- **Cảnh báo dữ liệu thiếu cột Time**: Nếu tệp nạp vào không chứa cột `Time` hợp lệ, ứng dụng tự động hiển thị hộp thoại cảnh báo và gợi ý người dùng chuyển sang chế độ tính toán thời gian theo Hz.

---

## 3. Quản Lý & Phân Nhóm Cảm Biến

Giao diện cột bên trái (**Sensors**) cho phép gom các cảm biến riêng lẻ thành các nhóm đại diện (VD: *Exhaust pipe skin, Rear muffler, Engine block, Generator, Vent, Head, Floor...*):

- **Tạo nhóm mới**:
  1. Nhập **Tên nhóm mới** (VD: `Exhaust pipe skin`).
  2. Chọn **Đơn vị đo** (`Temp (°C)`, `Speed (km/h)`, `Force (N)`, `Pressure (bar)`, `RPM`, `Other`).
  3. Chọn các cảm biến cần gán từ cây **"Cảm biến chưa gán"** (giữ phím `Ctrl` hoặc `Shift` để chọn nhiều cảm biến cùng lúc).
  4. Nhấn nút **`➕ Thêm Nhóm`**.
  *(💡 Màu đại diện đường biểu diễn sẽ tự động được hệ thống phối ngẫu nhiên đẹp mắt và chống trùng lặp giữa các nhóm)*.
- **Bổ sung / Di chuyển cảm biến (Drag & Drop)**: 
  - Kéo thả trực tiếp cảm biến lẻ hoặc kéo **nguyên thư mục tệp** từ danh sách chưa gán thả vào nhóm mục tiêu trong cây cấu trúc nhóm.
- **Đổi màu / Đổi đơn vị / Đổi tên / Xóa nhóm**:
  - Nhấp chuột phải vào tên nhóm hoặc cảm biến trong cây cấu trúc để mở menu ngữ cảnh (Đổi màu, Đổi đơn vị, Đổi tên, Xóa nhóm).
  - Nhấp trực tiếp vào ô màu nhỏ bên cạnh tên nhóm để mở hộp thoại bảng màu (Color Palette) và tùy chỉnh màu đường đồ thị.

---

## 4. Tùy Chỉnh Biểu Đồ & Trục Thời Gian

Tại mục **Chart (Cấu hình đồ thị & trục thời gian)**:
- **Tiêu đề đồ thị**: Nhập tên bài test để hiển thị nổi bật ở đỉnh biểu đồ (VD: *Thermal Analysis Chart*).
- **Đơn vị thời gian trục X**: Chuyển đổi linh hoạt đơn vị hiển thị giữa **`Phút (min)`**, **`Giây (s)`** hoặc **`Giờ (h)`**.
- **Bước nhảy lưới thời gian (Interval)**: Nhập khoảng cách giữa các vạch chia lưới (VD: `5.0` phút).
- **Giới hạn trục X (Xmin - Xmax)**: Nhập khoảng thời gian chi tiết cần tập trung quan sát hoặc để trống để phần mềm tự động bao phủ toàn bộ bài test (`Auto`).
- **Trục Y chính / phụ (Dual Y-Axes)**: Phân bố hiển thị các nhóm tín hiệu lên **Trục Y Trái** (Left Axis - Nhiệt độ °C) và **Trục Y Phải** (Right Axis - Vận tốc km/h, Áp suất bar, RPM...).
- **Tùy chọn hiển thị nâng cao**:
  - **Trục Y từ 0 (Force Y from 0)**: Bắt buộc gốc tọa độ Y bắt đầu từ 0.
  - **Đánh dấu Max-Min (Show Max/Min)**: Tự động đánh dấu các điểm cực trị đại (Max) và cực tiểu (Min) kèm nhãn giá trị trực tiếp trên từng đường biểu diễn.

---

## 5. Cấu Hình Điểm Mốc Set Point

Tại mục **Setpoints (Cấu hình mốc thời gian đánh giá)**:
- **Số lượng mốc Set Point**: Nhập số lượng mốc cần theo dõi (từ `1` đến `10` điểm: *SP A, SP B, SP C...*) hoặc bấm nút **`➕ Thêm`** để tạo nhanh từng mốc.
- **Vị trí & Đơn vị Set Point**: Nhập mốc thời gian cụ thể và chọn đơn vị tương ứng (`min`, `s`, `hr`) cho từng mốc. Nhấn nút 🗑️ để xóa mốc dư thừa.
- **Hiển thị đường gióng lên đồ thị**: Tích chọn **`Vẽ lên đồ thị`** để hiển thị các đường gióng đứng nét đứt kèm cờ đánh dấu (*SP A, SP B...*).
- **Hiển thị thông số đa tệp (Multi-file Tooltips)**: Khi vẽ lên đồ thị, mỗi đường gióng Set Point sẽ tự động tính toán và hiển thị nhãn giá trị thực tế của **tất cả các nhóm cảm biến (thuộc nhiều tệp dữ liệu khác nhau)** tại vị trí mốc thời gian đó, tích hợp thuật toán chống đè chữ thông minh (Stagger Offset) giúp dễ quan sát.

---

## 6. Chọn Tín Hiệu & Quản Lý Preset Biểu Đồ (Save As)

Tại mục **Signals (Danh sách tín hiệu vẽ đồ thị)**:
- **Lọc tín hiệu 🔍**: Ô tìm kiếm nhanh giúp tìm kiếm tên nhóm hoặc cảm biến cần vẽ.
- **Thao tác hàng loạt**: Nhấn nút **`✓ Chọn tất cả`** hoặc **`✗ Bỏ chọn tất cả`** để bật/tắt nhanh toàn bộ tín hiệu.
- **💾 Lưu Preset (Save As)**: Nhấn nút **`💾 Lưu Preset`** ở thanh Header – phần mềm sẽ **luôn bật hộp thoại Save As** cho phép bạn chọn thư mục và đặt tên tệp `.json` mới để lưu lại toàn bộ cấu hình sơ đồ nhóm, màu sắc, vị trí setpoint, đơn vị và tín hiệu đã chọn.
- **📂 Nạp Preset**: Nhấn nút **`📂 Nạp Preset`** để chọn và tái sử dụng tệp cấu hình `.json` đã lưu. Thuật toán tự động khớp tên cảm biến thông minh kể cả khi tệp dữ liệu nạp vào có hoặc không có tiền tố tệp (`[F1]`, `[F2]`).

---

## 7. Vẽ Biểu Đồ Trên Giao Diện & Xử Lý Nền

- **Tính toán mượt mà dưới nền (Multi-threading QThread)**: Khi bạn thực hiện bất kỳ thao tác chỉnh sửa cấu hình nào (thay đổi vị trí setpoint, chọn tín hiệu, đổi đơn vị, gom nhóm...), ứng dụng sẽ thực hiện tính toán dữ liệu ngầm dưới luồng nền QThread mà **không làm giật lag giao diện người dùng**.
- **Vẽ lên giao diện khi bấm nút**: Biểu thị đồ thị trực quan nét cao chỉ được cập nhật và vẽ lên màn hình bên phải khi bạn chủ động bấm nút **`🚀 Vẽ Đồ Thị (Draw Chart)`**, giúp tối ưu hóa hiệu năng tối đa khi thao tác với lượng dữ liệu lớn.

---

## 8. Bảng Phân Tích Set Point & Tiêu Chí Đánh Giá

Nhấn nút **`Phân Tích Set Point`** trên thanh điều khiển biểu đồ để mở cửa sổ phân tích chuyên sâu:

### A. Đọc kết quả phân tích
- Bảng tổng hợp chi tiết giá trị thực tế của từng nhóm cảm biến (từ nhiều file khác nhau) tại chính xác các mốc thời gian Set Point (*SP A, SP B...*).
- **Độ chênh lệch Deviation**: Tự động tính chênh lệch nhiệt độ nội bộ nhóm ($\text{Max} - \text{Min}$) tại mốc Set Point để đánh giá độ đồng đều phân bố luồng khí/nhiệt.
- **Tốc độ thay đổi nhiệt độ ($\Delta T / \Delta t$)**: Tính tốc độ tăng hoặc làm lạnh nhiệt độ (°C/phút) giữa 2 mốc Set Point liên tiếp.

### B. Thiết Lập Tiêu Chí Đánh Giá Bài TEST (`⚙️ Cài Đặt Bài TEST` / PASS-FAIL Criteria)
Trong bảng phân tích, nhấn nút **`⚙️ Cài Đặt Bài TEST`** để cài đặt bộ quy tắc đánh giá PASS / FAIL:
- **Thiết lập điều kiện (Rules)**: Chọn nhóm cảm biến, chọn phép so sánh ($\le, <, \ge, >, =, \ne$) và nhập ngưỡng nhiệt độ yêu cầu tại từng mốc Set Point.
- **Tự động đánh giá**: Hệ thống so sánh kết quả thực tế với điều kiện và đánh giá trực quan (**Xanh PASS** / **Đỏ FAIL**).
- **📋 Sao chép luật**: Sao chép nhanh toàn bộ quy tắc đánh giá của 1 Set Point sang tất cả các Set Point còn lại chỉ với 1-click.
- **💾 Lưu / 📂 Nạp Preset Bài TEST**: Lưu và nạp riêng bộ quy tắc tiêu chí đánh giá ra file `.json` phục vụ cho các bài thử nghiệm tiêu chuẩn.
- **Lịch sử Hoàn tác (Undo/Redo)**: Hỗ trợ phím tắt `Ctrl + Z` (Hoàn tác) và `Ctrl + Y` / `Ctrl + Shift + Z` (Làm lại) khi thiết lập luật.

---

## 9. Tương Tác Trên Đồ Thị & Phím Tắt

| Thao Tác | Phím Tắt / Chuột | Chức Năng |
| :--- | :--- | :--- |
| **Kéo mốc Set Point** | Bấm giữ chuột trái vào cờ/đường Set Point | Kéo di chuyển trực tiếp mốc thời gian trên đồ thị (Bảng phân tích sẽ cập nhật tức thì) |
| **Phóng to / Thu nhỏ** | Cuộn chuột giữa HOẶC `Ctrl +` / `Ctrl -` | Zoom in / Zoom out theo vị trí con trỏ chuột |
| **Di chuyển đồ thị (Pan)** | Bấm giữ chuột phải HOẶC nút Pan | Kéo trượt vùng hiển thị đồ thị |
| **Khôi phục góc nhìn** | Nhấn biểu tượng 🏠 (Home) trên toolbar | Reset biểu đồ về góc nhìn toàn cảnh ban đầu |
| **Hoàn tác (Undo)** | `Ctrl + Z` | Khôi phục lại thao tác cài đặt tiêu chí trước đó |
| **Làm lại (Redo)** | `Ctrl + Shift + Z` / `Ctrl + Y` | Làm lại thao tác vừa Undo |
| **Lưu nhanh đồ thị** | Biểu tượng 💾 (Save) trên toolbar | Xuất đồ thị thành tệp ảnh độ phân giải cao (.png, .jpg, .svg, .pdf) |

---

## 10. Xuất Báo Cáo & Cập Nhật Ứng Dụng

- **Xuất dữ liệu đã tính toán**: Nhấn nút **`Xuất Dữ Liệu`** tại màn hình chính để xuất toàn bộ DataFrame (bao gồm các cột mốc thời gian `Elapsed_s`, `Elapsed_min`, `Elapsed_hr` và các dòng dữ liệu trung bình nhóm) ra tệp Excel `.xlsx` hoặc `.csv`.
- **Xuất bảng kết quả phân tích**: Trong cửa sổ Set Point Analysis, nhấn nút **`Xuất Bảng Ra Excel (.xlsx)`** để xuất báo cáo bảng tổng hợp chỉ số và kết quả đánh giá PASS/FAIL.
- **Kiểm tra bản cập nhật tự động**:
  - Khi khởi động, ứng dụng tự động kiểm tra phiên bản mới công bố trên GitHub Releases.
  - Khi có bản nâng cấp, nút thông báo đỏ **`🔴 Bản mới vX.X.X`** sẽ xuất hiện ở góc trên bên phải Header. Nhấn vào để xem ghi chú phát hành (Release Notes) và cập nhật tự động.
- **Nhật ký sự cố (Crash Logs)**: File log lỗi được ghi tự động trong thư mục `logs/` và được hệ thống tự động dọn dẹp sau 7 ngày để tối ưu dung lượng máy tính.

---

*Phát triển bởi THAINV30, DỰA TRÊN NỀN TẢNG CỦA TUANNQ38, GÓP Ý BY LONGHV9*
