

# Tiếp Tục
Sau thời gian đầu thì mình đã dần có những định hướng cho việc học tập và chơi ctf. Mình nhận thấy bản thân mình còn thiếu sót rất nhiều về máy tính, máy tính hoạt động như nào, ra làm sao? Mình hoàn toàn không hiểu rõ. Đây là yếu tố không thể thiếu trong việc tìm hiểu thêm về ngành an toàn thông tin, vậy nên hôm nay mình sẽ đi tìm hiểu sơ qua về kiến trúc máy tính. Với việc máy tính cách ngày càng phát triển thì cũng có nhiều dạng kiến trúc về máy tính nhưng hôm nay chúng tao sẽ đề cập đến dạng kiến trúc phổ biến nhất đó là **kiến trúc Von Neumann**.

## Bắt đầu

Kiến trúc máy tính Von Neumann là một loại kiến trúc máy tính được dựa trên mô tả của nhà toán học và vật lý John Von Neumann. Về cơ bản thì máy tính sẽ được chia làm 3 phần:
- Bộ vi xử lý trung tâm (CPU).
- Bộ nhớ.
- Thiết bị vào ra.
<img src="https://github.com/Ducmanh2712/Ducmanh2712.github.io/assets/154677850/64933b27-bf12-433e-8bb0-985002933cc3" alt="..." width="700" />

## Chi tiết

### BỘ XỬ LÝ TRUNG TÂM
#### CPU (Central Processing Unit): Đây là trung tâm xử lý của máy tính, nơi thực hiện các phép tính và điều khiển hoạt động của hệ thống. CPU bao gồm các thành phần sau:


##### 1. Bộ xử lý logic số học (ALU):
ALU là một phần quan trọng của CPU.

+ ALU có chức năng thực hiện các phép tính số học và logic.
+ ALU sử dụng hai thanh ghi toán hạng OP1 và OP2 để giữ các toán hạng và kết quả.
+ ALU có thể thực hiện được các phép số học như cộng, trừ, tăng, giảm, nhân, chia, so sánh, các phép NOT, AND, OR, XOR, phép dịch bit, phép quay.


##### 2. Control Unit (Bộ điều khiển): 
CU là thành phần quản lý và điều khiển hoạt động của CPU. Nhiệm vụ chính của CU là giải mã các lệnh được lưu trữ tronng bộ nhớ và tạo ra các tín hiệu điều khiển các thành phần khác của CPU hoạt động. Trong CU cũng có một số thanh ghi riêng hỗ trợ việc thực thi lệnh (VD: MAR - Memory Address Register, IC - Instruction Register,PC - Program Counter, ...). CU hoạt động dựa theo tín hiệu của bộ định thời (clock) theo chu kỳ. Một chu kỳ thực hiện của CU bao gồm

+ Fetch (giai đoạn lấy lệnh): Lệnh sẽ được đọc từ bộ nhớ và sao chép vào thanh ghi trong CU.
+ Decode (giai đoạn giải mã): Lệnh đã được đọc trước đó được giải mã để xác định nhiệm vụ cần thực thi.
+ Execute (giai đoạn thực thi): Lệnh được thực hiện bởi các bộ phận trong CPU như ALU.
+ Store (giai đoạn lưu trữ): Kết quả được lưu trữ vào các thanh ghi.


##### 3. Thanh ghi (Register): 

+ Thanh ghi là một dạng bộ nhớ hoạt động được ở tốc độ cao. Bộ thanh ghi chính là bộ nhớ nằm trong CPU có tác dụng hỗ trợ hoạt động của CPU.
+ CPU dùng các thanh ghi với những mục đích khác nhau thể hiện qua tên gọi: 
+ Thanh ghi bộ đếm chương trình PC (program counter), thanh ghi này nằm trong CU.
+ Thanh ghi bộ tích lũy ACC (accummulator).
+ Thanh ghi đa dụng (general purpose register).
+ Thanh ghi chỉ số (index register).
+ Thanh ghi con trỏ chồng SP (stack pointer).
+ Thanh ghi cờ trạng thái (flags register).



### KHỐI BỘ NHỚ
#### 1. Bộ nhớ là gì?
- Bộ nhớ nói đơn giản là bộ phận có chức năng lưu trữ thông tin, bộ nhớ là tập hợp các ô nhớ theo một trật tự nhất định, mỗi ô nhớ có một địa chỉ để xác định vị trí của ô nhớ đó.


#### 2. Đặc điểm của bộ nhớ.
- Lưu trữ thông tin theo dạng nhị phân. Dễ hiểu thì các thông tin sẽ được biên dịch sang dạng nhị phân (VD: 123 = 1111011) và lưu trữ trong bộ nhớ.
- CPU muốn làm việc với bộ nhớ phải cung cấp địa chỉ, dữ liệu và một số tín hiệu điều khiển như chọn bộ nhớ, cho phép đọc hoặc ghi hiểu nôm na là CPU sẽ điều khiển các bộ phận khác trong máy tính bằng các tín hiệu đến một chủ thể nào đó (ở đây là một vùng nhớ có địa chỉ nào đó) giống như não bộ sẽ gửi tín hiệu đến các bộ phận trong cơ thể vậy. 
- Nói đến bộ nhớ thì phải nói đến dung lượng và thời gian truy xuất, đây là hai đại lượng đặc trưng để đánh giá khả năng của một bộ nhớ:
+ Dung lượng chính là không gian có thể lưu trữ được của bộ nhớ, dung lượng càng lớn thì thông tin có thể lưu trữ càng nhiều.
+ Thời gian truy xuất là thời gian bộ nhớ đưa ra được dữ liệu. Bộ nhớ có thời gian truy xuất nhỏ thì dữ liệu được xử lý nhanh sẽ khiến máy tính hoạt động tốt hơn.


#### 3. Thao tác đọc và ghi bộ nhớ.
- Từ những gì chúng ta nói ở trên thì bộ nhớ có khả năng lưu trữ thông tin, dữ liệu. Do đó bộ nhớ có thao tác đọc giúp người dùng sử dụng dữ liệu có trong bộ nhớ và thao tác ghi giúp người dùng có thể ghi dữ liệu vào bộ nhớ.
+ Thao tác đọc bộ nhớ: CU đưa địa chỉ của ô nhớ cần đọc qua thanh ghi địa chỉ bộ nhớ (Thanh ghi MAR đã đề cập ở CU), BUS địa chỉ. CU đưa ra tín hiệu điều khiển đọc. Nội dung ô nhớ lúc này sẽ được đọc từ bộ nhớ và đưa vào thanh ghi đệm (MBR) của CPU.
+ Thao tác ghi bộ nhớ: Đơn vị điều khiển đưa địa chỉ của ô nhớ cần ghi qua MAR ra BUS địa chỉ và đưa dữ liệu qua MBR ra BUS dữ liệu. Sau đó đơn vị điều khiển đưa ra tín hiệu điều khiển ghi, dữ liệu từ đơn vị xử lý trung tâm được ghi vào bộ nhớ.


#### 4. RAM (Random Access Memory): 
RAM là một trong hai loại bộ nhớ chính bao gồm ROM và RAM, RAM cho phép đọc và ghi ngẫu nhiên dữ liệu đến bất kỳ vị trí nào trong bộ nhớ dựa theo địa chỉ của bộ nhớ. Đây cũng là lý do nó có tên gọi là "Bộ nhớ truy xuất ngẫu nhiên".

##### - Ram được chia làm hai loại là SRAM và DRAM, mỗi loại lại chia làm các loại nhỏ hơn và có đặc điểm riêng nhưng hôm nay chúng ta sẽ không đi sâu chi tiết vào từng loại RAM.

##### - RAM bản chất là cầu nối giữa các bộ phận trong hệ thống giúp máy tính hoạt động nhanh hơn nhờ vào khả năng truy xuất tốc độ cao của mình. Tuy nhiên nếu bị ngắt điện hoặc thiết bị tắt thì mọi dữ liệu trên RAM sẽ bị xóa sạch (Giống như khi bạn đang làm một bản word mà quên lưu lại thì dữ liệu sẽ bị mất hết)

##### - Cấu tạo của RAM gồm có:

+ Bo mạch: Bo mạch kết nối các thành phần của RAM và máy tính.
+ Vi xử lý: Đối với một số loại RAM đồng bộ, vi xử lý có tác dụng đồng bộ hóa các hoạt động của RAM và loại bỏ các tín hiệu không cần thiết.
+ Ngân hàng bộ nhớ: Ngân hàng bộ nhớ chứa các module có tác dụng lưu trữ dữ liệu và là tác dụng chính của RAM.
+ Bộ đếm: Bộ đếm theo dõi các địa chỉ để cho phép truy cập tốc độ cao.


##### - Ram có các chức năng:

+ Lưu trữ tạm thời dữ liệu khi máy tính hoạt động. Ví dụ khi một chương trình hoạt động, các phần của chương trình và dữ liệu tương ứng được tải vào RAM để CPU có thể truy cập và xử lý nhanh chóng hơn thay vì phải truy xuất vào ổ cứng vì RAM có tốc độ truy cập nhanh và khả năng truy xuất ngẫu nhiên giúp tăng tốc độ xử lý của hệ thống.
+ Hỗ trợ thực thi chương trình: Một số dữ liệu sẽ được chuyển từ ổ cứng vào RAM khi chương trình hoạt động để giúp cho CPU có thể truy cập và thực thi một cách nhanh chóng hơn.
+ Quản lý các biến và dữ liệu: Khi một hàm hoặc một chương trình con được gọi, các biến cục bộ và biến dữ liệu thực thi được lưu trữ trong RAM. RAM cung cấp vùng nhớ để lưu trữu các biến và dữ liệu cho phép chương trình thực hiện các phép tính và xử lý dữ liệu cục bộ trong quá trình thực thi.



#### 5. ROM (Read Only Memory): ROM là loại bộ nhớ có chức năng lưu trữ các chương trình cơ bản của máy tính giúp máy tính khởi động, hệ điều hành,... Là bộ nhớ cơ bản để máy tính có thể hoạt động.
##### - Như tên gọi thì ROM Là bộ nhớ chỉ đọc, ROM không có thao tác ghi dữ liệu. 

##### - RAM khi bị ngắt điện hoặc tắt máy sẽ bị xóa sạch dữ liệu nhưng ROM thì không.

##### - ROM có cấu trúc được chia làm 3 phần:
+ Bộ giải mã địa chỉ: Gồm bộ giải mã hàng và bộ giải mã cột có tác dụng xác định địa chỉ truy cập và truy xuất dữ liệu từ ROM.
+ Mảng thanh ghi: Là nơi lưu trữ dữ liệu đã được lập trình sẵn vào ROM và có sự sắp xếp theo ma trận vuông. Người dùng không thể lưu trữ thêm vào những thanh ghi này.

### KHỐI VÀO RA:
#### 1. Đặc điểm của khối vào ra.
##### - Khối vào ra có chức năng điều khiển các thiết bị ngoại vi (như là bàn phím, màn hình,...) để giao tiếp với thế giới bên ngoài trong đó:
+ Mỗi thiết bị ngoại vi sẽ được điều khiển độc lập. Dễ hiểu thì màn hình sẽ được điều khiển độc lập với bàn phím.
+ Mỗi thiết bị ngoại vi được điều khiển bởi một mạch vi xử lý chuyên dụng riêng như là mạch điều khiển màn hình, mạch điều khiển đĩa, mạch điều khiển bàn phím, mạch điều khiển giao tiếp mạng,...

#### 2. Cách hoạt động của khối vào ra.
##### - CPU giao tiếp với các vi xử lý vào ra thông qua các cổng vào ra.
##### - Mỗi cổng vào ra cũng có một địa chỉ riêng.
##### - Mỗi vi xử lý vào ra có thể có nhiều địa chỉ cổng vào ra.
##### - Việc lựa chọn cổng vào ra cũng được thực hiện bởi mạch giải mã địa chỉ vào ra.

#### 3. Phân loại.
##### - Thông thường các thiết bị ngoại vi sẽ được phân loại theo chiều trao đổi dữ liệu:
+ Màn hình, máy in, máy chiếu,... là thiết bị xuất.
+ Bàn phím, chuột, máy scan,... là thiết bị nhập.
+ Đĩa, Flash drive (USB),... là thiết bị vừa xuất vừa nhập.

#### 4. Phương pháp vào ra dữ liệu:
##### - Có 4 phương pháp vào ra dữ liệu, trong đó mỗi phương pháp đều có ưu nhược điểm mà mình sẽ không đi sâu vào hôm nay:
+ Vào ra do CPU chủ động có 2 loại: Vào ra theo định trình và vào ra có khiểm tra trạng thái.
+ Vào ra do các thiết bị vào ra chủ động có 2 loại: Vào ra theo ngắt cứng và vào ra theo kiểu DMA.


### HỆ THỐNG BUS
##### - Bên trên thì mình cũng có đề cập vài lần đến Bus, vậy bus là gì? Bus chính là những đường dẫn, nối đến các bộ phận của hệ thống, là các dây cáp nối trong đó được chia làm nhiều nhóm cáp có các chức năng khác nhau. 

#### 1. Phân loại Bus.

##### - Bus địa chỉ: 
+ Bus địa chỉ là tuyến đưa những thông tin về địa chỉ ô nhớ, nhắm xác định, phân biệt vị trí các ô nhớ hay các thiết bị ngoại vi.
+ Bus địa chỉ là Bus 1 chiều: Ra từ CPU,, vào các khối còn lại như bộ nhớ, khối vào ra.
+ Mỗi đường địa chỉ của Bus địa chỉ có thể phân biệt được hai địa chỉ là 0 và 1. Vậy nên với 2 đường địa chỉ khả năng định địa chỉ sẽ là 4 0 (00), 1(01), 2 (10) và 3 (11); Vậy thì chúng ta có thể hiểu là số lượng địa chỉ mà Bus có thể quản lý được tùy thuộc vào số đường địa chỉ của Bus.


##### - Bus dữ liệu: 
+ Bus dữ liệu là Bus có tác dụng xử lý thông tin.
+ Bus dữ liệu là Bus 2 chiều: Có thể đưa dữ liệu từ CPU ra các khối và ngược lại từ các khối vào CPU.
+ Bus dữ liệu cũng trao đổi dữ liệu dưới dạng nhị phân mà mỗi đường dữ liệu sẽ tương ứng với 1 bit (VD: Bus dữ liệu có 32 đường cho phép mỗi lần trao đổi được 4 byte dữ liệu).


##### - Bus điều khiển/trạng thái: theo mô hình Von Neumann các bạn có thể thấy là các Bus được dùng chung cho cả hai khối vào ra và khối bộ nhớ. Mục đích cho điều này là để tiết kiệm số đường truyền trong mỗi tuyến. Nhưng như vậy thì hẳn bạn sẽ thắc mắc là làm sao máy tính có thể phân biệt được là khi nào thì CPU muốn làm việc với bộ nhớ, khi nào thì muốn làm việc với khối vào ra hay khi nào thì dữ liệu đi từ CPU ra và khi nào thì dữ liệu đi vào CPU,... Điều này chính là lý do cho sự xuất hiện của Bus điều khiển/trạng thái. 
+ Bus điều khiển/trạng thái có chức nâng xác định rõ CPU muốn làm việc với bộ phận nào hay chiều dữ liệu là chiều ra hay vào CPU,...
+ Những đường có chiều xuất phát từ CPU thường được xem là đường điều khiển và ngược lại những đường có chiều hướng vào CPU thường được xem là đường trạng thái. 
+ Mỗi đường trong Bus địa chỉ đều mang tên riêng và mục đích riêng (VD: Đường MEMR là đường dẫn tín hiệu điều khiển đọc bộ nhớ, hay đường MEMW là đường điều khiển ghi bộ nhớ, IORD là điều khiển quá trình nhập, IOWR là điều khiển quá trình xuất,...)


Vậy là chúng ta đã nói qua về kiến trúc máy tính Von Neumann. Hiểu về kiến trúc máy tính để hiểu về cách hoạt động của máy tính là một yếu tố quan trọng trong ngành An toàn thông tin nói chung và việc chơi CTF nói riêng.

# TO BE CONTINUED


