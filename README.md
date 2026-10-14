
# Báo cáo kiểm thử hiệu năng website VnExpress bằng Apache JMeter

## 1. Mục tiêu

- Làm quen với giao diện và phương thức vận hành của công cụ kiểm thử hiệu năng Apache JMeter.
- Xây dựng kịch bản gửi HTTP Request (HTTPS GET) đồng thời tới website VnExpress (`https://vnexpress.net/`).
- Thu thập, đọc hiểu và phân tích kết quả phản hồi cũng như các chỉ số đo lường hiệu năng cốt lõi: thời gian phản hồi (Response Time), tỷ lệ lỗi (Error Rate), thông lượng (Throughput) và lưu lượng mạng.

---

## 2. Công cụ và môi trường sử dụng

- **Công cụ kiểm thử:** Apache JMeter 5.6.3
- **Website kiểm thử:** `https://vnexpress.net/`
- **Giao thức:** HTTPS (Cổng mặc định: 443)
- **Phương thức HTTP:** GET

---

## 3. Cấu hình kiểm thử

- **Test Plan:** `VnExpress Performance Test`
- **Thread Group:** `VnExpress Users`
  - **Number of Threads (users):** `10` *(Mô phỏng 10 người dùng đồng thời)*
  - **Ramp-up period (seconds):** `10` *(Cứ mỗi 1 giây sẽ có 1 người dùng mới được khởi chạy)*
  - **Loop Count:** `1` *(Mỗi người dùng gửi yêu cầu 1 lần $\rightarrow$ Tổng số samples: $10 \times 1 = 10$ requests)*
  - **Same user on each iteration:** Checked
- **HTTP Request:** `Access VnExpress Homepage`
  - **Protocol:** `https`
  - **Server Name or IP:** `vnexpress.net`
  - **HTTP Method:** `GET`
  - **Path:** `/`
- **Các Listener theo dõi kết quả:** `View Results Tree`, `Summary Report`, `Aggregate Report`.

---

## 4. Các bước thực hiện

1. Khởi động công cụ Apache JMeter 5.6.3.
2. Tạo **Test Plan** với tên `VnExpress Performance Test`.
3. Thêm **Thread Group** (`VnExpress Users`) và thiết lập các thông số tải: 10 threads, ramp-up 10s, loop 1.
4. Thêm sampler **HTTP Request** (`Access VnExpress Homepage`), cấu hình truy cập giao thức `https`, server `vnexpress.net` và đường dẫn `/`.
5. Tích hợp lần lượt các Listeners: `View Results Tree`, `Summary Report` và `Aggregate Report`.
6. Lưu kịch bản dưới tên `VnExpress Users.jmx`, chạy kịch bản (nút Run/Play) và ghi nhận kết quả hiển thị trên các màn hình báo cáo.

---

## 5. Hình ảnh minh họa kết quả thực hiện

### 5.1. Cấu hình Thread Group

# Báo cáo kiểm thử hiệu năng website VnExpress bằng Apache JMeter

## 1. Mục tiêu

- Làm quen với giao diện và phương thức vận hành của công cụ kiểm thử hiệu năng Apache JMeter.
- Xây dựng kịch bản gửi HTTP Request (HTTPS GET) đồng thời tới website VnExpress (`https://vnexpress.net/`).
- Thu thập, đọc hiểu và phân tích kết quả phản hồi cũng như các chỉ số đo lường hiệu năng cốt lõi: thời gian phản hồi (Response Time), tỷ lệ lỗi (Error Rate), thông lượng (Throughput) và lưu lượng mạng.

---

## 2. Công cụ và môi trường sử dụng

- **Công cụ kiểm thử:** Apache JMeter 5.6.3
- **Website kiểm thử:** `https://vnexpress.net/`
- **Giao thức:** HTTPS (Cổng mặc định: 443)
- **Phương thức HTTP:** GET

---

## 3. Cấu hình kiểm thử

- **Test Plan:** `VnExpress Performance Test`
- **Thread Group:** `VnExpress Users`
  - **Number of Threads (users):** `10` *(Mô phỏng 10 người dùng đồng thời)*
  - **Ramp-up period (seconds):** `10` *(Cứ mỗi 1 giây sẽ có 1 người dùng mới được khởi chạy)*
  - **Loop Count:** `1` *(Mỗi người dùng gửi yêu cầu 1 lần $\rightarrow$ Tổng số samples: $10 \times 1 = 10$ requests)*
  - **Same user on each iteration:** Checked
- **HTTP Request:** `Access VnExpress Homepage`
  - **Protocol:** `https`
  - **Server Name or IP:** `vnexpress.net`
  - **HTTP Method:** `GET`
  - **Path:** `/`
- **Các Listener theo dõi kết quả:** `View Results Tree`, `Summary Report`, `Aggregate Report`.

---

## 4. Các bước thực hiện

1. Khởi động công cụ Apache JMeter 5.6.3.
2. Tạo **Test Plan** với tên `VnExpress Performance Test`.
3. Thêm **Thread Group** (`VnExpress Users`) và thiết lập các thông số tải: 10 threads, ramp-up 10s, loop 1.
4. Thêm sampler **HTTP Request** (`Access VnExpress Homepage`), cấu hình truy cập giao thức `https`, server `vnexpress.net` và đường dẫn `/`.
5. Tích hợp lần lượt các Listeners: `View Results Tree`, `Summary Report` và `Aggregate Report`.
6. Lưu kịch bản dưới tên `VnExpress Users.jmx`, chạy kịch bản (nút Run/Play) và ghi nhận kết quả hiển thị trên các màn hình báo cáo.

---

## 5. Hình ảnh minh họa kết quả thực hiện

### 5.1. Cấu hình Thread Group

<img width="1506" height="816" alt="01-cau-hinh-thread-group" src="https://github.com/user-attachments/assets/e73a7add-aba8-4fd8-bea0-aa052a3f9e8c" />

### 5.2. Cấu hình HTTP Request

<img width="1517" height="820" alt="02-cau-hinh-http-request" src="https://github.com/user-attachments/assets/b3db0dca-eac5-4646-9f8a-cd68f5bbbd00" />


### 5.3. Kết quả View Results Tree

<img width="1520" height="845" alt="03-view-results-tree" src="https://github.com/user-attachments/assets/8b67e4ce-2653-4704-b5d0-c4ae71189fc9" />

### 5.4. Summary Report

<img width="1515" height="852" alt="04-summary-report" src="https://github.com/user-attachments/assets/c89faade-1a99-4be3-bfc5-ff1ff92c625a" />


### 5.5. Aggregate Report

<img width="1518" height="848" alt="05-aggregate-report" src="https://github.com/user-attachments/assets/bd459a30-11bb-4455-87f1-1e7849576886" />


---

## 6. Bảng số liệu và Phân tích kết quả thực tế

### 6.1. Bảng số liệu ghi nhận từ hệ thống

Dưới đây là số liệu thống kê chi tiết trích xuất trực tiếp từ **Summary Report** và **Aggregate Report**:

| Chỉ số (Metric) | Giá trị thực tế | Đơn vị | Ý nghĩa phân tích |
| :--- | :---: | :---: | :--- |
| **# Samples** | **10** | requests | Tổng số yêu cầu gửi đến máy chủ (10 threads × 1 loop) |
| **Average** | **232** | ms | Thời gian phản hồi trung bình của toàn bộ các yêu cầu |
| **Median** | **177** | ms | $50\%$ số yêu cầu hoàn tất trong vòng $\le 177$ ms |
| **90% Line** | **362** | ms | $90\%$ số người dùng nhận được phản hồi trong vòng $\le 362$ ms |
| **95% Line** | **362** | ms | $95\%$ số người dùng nhận được phản hồi trong vòng $\le 362$ ms |
| **99% Line** | **579** | ms | $99\%$ số người dùng nhận được phản hồi trong vòng $\le 579$ ms |
| **Min** | **107** | ms | Thời gian phản hồi nhanh nhất ghi nhận được |
| **Maximum** | **579** | ms | Thời gian phản hồi chậm nhất ghi nhận được |
| **Std. Dev.** | **134.83** | - | Độ lệch chuẩn biểu thị mức độ dao động của thời gian phản hồi |
| **Error %** | **0.00%** | % | Tỷ lệ lỗi (tất cả 10/10 requests đều thành công) |
| **Throughput** | **1.1/sec** | req/s | Tốc độ xử lý trung bình của kịch bản (1.1 yêu cầu/giây) |
| **Received KB/sec**| **277.33** | KB/s | Tốc độ tải dữ liệu máy chủ truyền về máy khách |
| **Sent KB/sec** | **0.12** | KB/s | Tốc độ gửi dữ liệu đi từ máy khách |
| **Avg. Bytes** | **264,130.9** | bytes | Kích thước trung bình một gói phản hồi (xấp xỉ 258 KB) |

---

### 6.2. Phân tích và Đánh giá chi tiết

1. **Về tính ổn định và Mã phản hồi (Response Code):**
   - Kiểm tra trên **View Results Tree** cho thấy $10/10$ requests đều hiển thị trạng thái màu xanh.
   - Mã trạng thái phản hồi: `Response code: 200`, `Response message: OK`.
   - Tỷ lệ lỗi là **0.00%**, chứng minh hệ thống máy chủ VnExpress tiếp nhận và xử lý trọn vẹn mọi yêu cầu gửi tới mà không phát sinh lỗi kết nối hay lỗi máy chủ (không có mã lỗi `4xx` hay `5xx`).

2. **Về thời gian phản hồi (Response Time):**
   - Thời gian phản hồi trung bình đạt **232 ms**, nhanh nhất là **107 ms** và chậm nhất chỉ là **579 ms**.
   - Phân vị **90% Line và 95% Line đều đạt 362 ms** (dưới 0.4 giây). Điều này chứng minh rằng hầu hết tất cả người dùng đều có trải nghiệm tải trang ban đầu rất nhanh chóng và mượt mà.

3. **Về thông lượng (Throughput) và Lưu lượng dữ liệu:**
   - Thông lượng đạt **1.1 requests/sec**, hoàn toàn phù hợp với cấu hình tải đặt ra ban đầu (10 users được kích hoạt rải đều trong thời gian 10 giây Ramp-up: $10 \text{ requests} / 10 \text{ seconds} \approx 1 \text{ req/s}$).
   - Kích thước trang tải về trung bình là **~264.1 KB** với tốc độ truyền tải dữ liệu đạt **277.33 KB/sec**, đảm bảo đường truyền mạng thông suốt.

---

## 7. Kết luận

- Bài thực hành đã hoàn thành đầy đủ mục tiêu: cấu hình kịch bản kiểm thử hiệu năng tải trang cơ bản trên Apache JMeter, chạy thử nghiệm và trích xuất số liệu phân tích trực quan.
- Website VnExpress có tốc độ phản hồi nhanh, độ ổn định cao (0% lỗi) đối với mức tải 10 người dùng đồng thời.
- **Kỹ năng đạt được:** Nắm vững các khái niệm căn bản trong kiểm thử hiệu năng (Thread Group, Sampler, Listener) và cách phân tích các báo cáo tóm lược quan trọng (`Summary Report`, `Aggregate Report`).


