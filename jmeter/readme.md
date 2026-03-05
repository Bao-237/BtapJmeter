# JMeter Performance Test Report

## 1. Website được kiểm thử

Website: https://vnexpress.net

Công cụ sử dụng: Apache JMeter

Mục tiêu: kiểm thử hiệu năng website với nhiều kịch bản tải khác nhau.

---

# 2. Test Scenario 1 – Basic Load Test

### Cấu hình

- Number of Users (Threads): 10
- Loop Count: 5
- Request: GET Homepage

### Kết quả

| Metric | Value |
|------|------|
| Samples | 300 |
| Average Response Time | 551 ms |
| Min | 48 ms |
| Max | 4083 ms |
| Error Rate | 0% |
| Throughput | 39.9 requests/min |

### Summary Report

![Basic Test](results/summary1.png)

### Nhận xét

Website phản hồi ổn định với số lượng người dùng thấp. Không xuất hiện lỗi và thời gian phản hồi trung bình khoảng 551ms.

---

# 3. Test Scenario 2 – Heavy Load Test

### Cấu hình

- Number of Users: 50
- Ramp-up Period: 30 seconds
- Requests:
  - Homepage
  - World News page

### Kết quả

| Metric | Value |
|------|------|
| Total Samples | 1718 |
| Average Response Time | ~751 ms |
| Min | 44 ms |
| Max | 6576 ms |
| Error Rate | 0% |
| Throughput | 3.7 requests/sec |

### Summary Report

![Heavy Test](results/summary2.png)

### Nhận xét

Khi số lượng người dùng tăng lên 50, thời gian phản hồi trung bình tăng lên khoảng 751ms nhưng hệ thống vẫn hoạt động ổn định và không có lỗi.

---

# 4. Test Scenario 3 – Custom Scenario

### Cấu hình

- Number of Users: 20
- Duration: 60 seconds
- Requests:
  - Business page
  - Sports page

### Kết quả

| Metric | Value |
|------|------|
| Total Samples | 2657 |
| Average Response Time | ~1058 ms |
| Min | 78 ms |
| Max | 6110 ms |
| Error Rate | 0% |
| Throughput | 14 requests/sec |

### Summary Report

![Custom Test](results/summary3.png)

### Nhận xét

Ở kịch bản tùy chỉnh với nhiều request khác nhau, throughput đạt 14 requests/sec. Thời gian phản hồi trung bình tăng lên khoảng 1 giây nhưng hệ thống vẫn xử lý ổn định.

---

# 5. Kết luận

Qua 3 kịch bản kiểm thử:

- Website hoạt động ổn định với tải thấp và tải trung bình
- Khi số lượng người dùng tăng, response time tăng nhưng không xảy ra lỗi
- Throughput tăng khi số lượng request tăng

Điều này cho thấy website có khả năng xử lý tải khá tốt trong phạm vi kiểm thử.

---

# 6. Files trong thư mục jmeter
