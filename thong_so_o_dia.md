### I. Các thông số đánh giá hiệu năng ổ cứng

Ba thông số cơ bản để đánh giá hiệu năng ổ cứng: throughput, latency và IOPS

#### 1. Throughput
- Chỉ ra tốc độ transfer data (MB/s hoặc GB/s). LÀ thông số khi check perfomance của ổ cứng bằng câu lệnh "**dd**" trong linux

- Câu lệnh để kiểm tra thougput

```
dd if=/dev/zero of=/tmp/test1.img bs=1G count=1 oflag=dsync
```

![disk](/images/disk3.png)

#### 2. Latency (ms)

- Thời gian ổ cứng bắt đầu thực hiện 1 data transfer. TRong HDD vật lý truyền thống, latency bao gồm seek time ( thời gian đầu đọc tìm ra vị trí data)
 và rotational latency (độ trễ chuyển động quay của trục). Thông số latency quyết định hiệu năng của volume vì nó quyết định thời gian trễ khi bắt
 đầu thực hiện thao tác.
 
#### 3. IOPS - Input/Output Operations Per Second

- Là số thao tác đọc ghi trên ổ cứng trong 1s. 
- Trong điện toán đám mây, nơi mà tài nguyên phần cứng được chia sẻ với nhiều người, IOPS quyết định độ nhanh và nhạy của 
volume do bản chất IOPS càng cao thì càng nhiều thao tác có thể thực hiện được đồng thời 1 lúc.

- Tốc độ xử lý càng nhanh => tốc độ hoạt động ứng dụng càng cao

### II. Chuẩn ổ đĩa cứng
#### 1. Chuẩn IDE (Parallel ATA hoặc PATA)
<ul>
<li>IDE là một chuẩn giao diện, được dùng trực tiếp bởi bo mạch chủ (BMC) của máy tính để truyền tải thông tin qua lại với ổ đĩa cứng hay ổ đĩa quang.</li>
<li>Chuẩn IDE thực hiện phương thức truyền tải dữ liệu song song. Tốc độ truyền tải dữ liệu hiện hành đối với chuẩn parallel IDE là 133 MB/s (ATA/133).</li>
</ul>

#### 2. Chuẩn SATA

<ul>
<li>Chuẩn SATA (Serial Avanced Technology Attachment), hay đơn giản được gọi là SATA – là một chuẩn ổ đĩa cứng được tạo nhằm mục đích thay thế cho giao diện IDE, cho phép truyền tải theo chế độ nối tiếp.</li>
Các thông số theo version của chuẩn SATA

|SATA Version | Bandwith | Speed|
|--------------|-------|------|
| SATA 3.0 | 6Gb/s | 600MB/s |
| SATA 2.0 | 3Gb/s | 300MS/s |
| SATA 1.0 | 1,5Gb/s | 150MB/s |


