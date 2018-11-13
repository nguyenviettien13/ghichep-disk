###I. Cấu tạo ổ HDD

![disk](/images/disk1.gif)

Gồm 4 thành phần chính : Cụm đĩa, cụm đầu đọc, cụm mạch điện, vỏ đĩa cứng.
####1. Cụm đĩa
- **1.1 Đĩa từ** 
	- Đĩa bằng nhô, thủy tinh, hoặc sứ có chế độ hoạt động tương đối nặng.
	- Có khả năng lưu trữ tốt, an toàn, không bị "nhão" (nhả từ)
	- Đĩa được phủ vật liệu từ ở cả 2 mặt và bao bọc bằng lớp vỏ bảo vệ.
	
- **1.2 Trục quay**
	- Là bộ phận dịch chuyển đầu từ.
    - Nhiều loại đĩa cứng sử dụng mô tơ cuộn dây di động (voice coil motor) hay gọi là mô tơ cuộn dây quay (rotary coil) hoặc servo để điều khiển chuyển động của đầu từ.
- **1.3 Động cơ (Motor trục quay)**
	- Yếu tố xác định chất lượng ổ cứng là tốc độ mà đĩa từ lướt qua dưới đầu đọc/ghi. Đĩa từ lướt qua đầu từ với tốc độ khá cao ( ít nhất là 3600 vòng/phút)
	- Mô tơ trục (spindle mô tơ) có chức năng làm quay các đĩa từ.
	- Mô tở trục là loại không có chổi quét, chiều cao thấp, dùng điện 1 chiều, tương tự mô tơ trong ổ đĩa mềm.
	
####2. Cụm đầu đọc
- **2.1 Đầu đọc/ghi (Head)**
	- Cấu tạo gồm lõi ferit và cuộn dây ( giống như nam châm điện )
	- Đầu đọc trong đĩa cứng đọc dữ liệu dưới dạng từ hóa trên bề mặt từ hoặc từ hóa lên các mặt đĩa khi ghi dữ liệu.
	- Số đầu đọc ghi luôn bằng số mặt hoạt động được của các đĩa từ.
	
####3. Cụm mạch điện
<ul>
	<li> Mạch điều khiển : Có nhiệm vụ điều khiển động cơ đồng trục, điều khiển sự di chuyển của cần di chuyển đầu đọc để đảm bảo đến đúng vị trí trên bề mặt đĩa.</li>	
	<li>Mạch xử lý dữ liệu : dùng để xử lý những dữ liệu đọc/ghi của ổ đĩa cứng.</li>		
	<li>Bộ nhớ đệm : nơi tạm lưu dữ liệu trong quá trình đọc/ghi dữ liệu. Dữ liệu trên bộ nhớ đệm sẽ mất đi khi ổ đĩa cứng ngừng được cấp điện.</li>	
	<li>Đầu cắm nguồn cung cấp điện cho ổ đĩa cứng.</li>	
	<li>Đầu kết nối giao tiếp với máy tính.</li>	
	<li>ác cầu nối (jumper) : lựa chọn chế độ làm việc của ổ đĩa cứng (SATA 150 hoặc SATA 300) hay thứ tự trên các kênh trên giao tiếp IDE (master hoặc slave hoặc tự lựa chọn ), lựa chọn các thông số làm việc khác.</li>	
</ul>	
####4. Vỏ đĩa cứng
<ul>
	<li>Chứa các linh kiện gắn trên nó, phần nắp đậy lại các bảo vệ linh kiện bên trong.</li>	
	<li>Vỏ đĩa cứng nhằm định vị các linh kiện, chịu đựng va chạm (ở mức thấp) để bảo vệ ổ đĩa cứng, không cho bụi vào trong ổ đĩa cứng.</li>	
	<li>Vỏ đĩa có lõ thoáng nhằm đảm bảo cản bụi và cân bằng áp suất môi trường ngoài và môi trường trong.</li>	
</ul>	
###II. Cấu trúc dữ liệu

![disk](/images/disk2.jpg)

####1. Track - Rãnh từ
<ul>
	<li>Các vòng tròn đồng tâm trên mặt đĩa dùng để xác định các vùng lưu trũ dữ liệu riêng biệt trên mặt đĩa.</li>
	<li>Mặc định, các track không cố định, chúng sẽ thay đổi vị trí khi được định dạng ở cấp thấp (low format) nhằm tái cấu trúc cho phù hợp khi đĩa bị hư hỏng (bad block) do xuống cấp của phần cơ.</li>
	<li>Tập hợp các track cùng bán kính của mặt đĩa khác nhau để tạo thành các trụ (cylinder), có 1024 cylinder ( từ 0-1023 ). Mỗi ổ cứng sẽ có nhiều cylinder vì có nhiều đĩa từ khác nhau.</li>
</ul>	
####2. Sector - Cung từ
<ul>
	<li>Mỗi track được chia thành các đường hướng tâm tạo thành các sector (cung từ), Sector là đơn vị chứa dữ liệu nhỏ nhất, dung lượng 512 byte.</li>
	<li>Số sector trên các track từ phần rìa đĩa đên tâm đĩa là khác nhau, các ổ cứng đều chia ra 10 vùng, mỗi vùng có tỷ số sector/track bằng nhau.</li>
</ul>	
####3. Cluster - Liên cung
<ul>
	<li>Một đơn vị lưu trữ 1 hoặc nhiều sector.</li>
	<li>Khi lưu dữ liệu vào ổ cứng, các dữ liệu được ghi vào hàng chục, hàng trăm cluster liền kề hoặc không liền kề nhau. Nếu không có sẵn có cluster liền nhau, HĐH sẽ tìm kiếm cluster còn trống ở gần và ghi tiếp dữ liệu lên đĩa.</li>
</ul>
	
