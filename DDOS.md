## 1. chào 
 - xin chào thầy và các bạn, nhóm mình là nhóm 11. gồm có mình - nguyễn văn hiệp , lã ngọc sơn và phạm phú quí.  hôm nay nhóm mình sẽ thuyết trình đồ án giữa kỳ với nội dung là ** tìm hiểu về tấn công DDOS** như các bạn đã biết, thì hiện nay là thời đại công nghiệp 4.0 mọi thứ đều được tự động hóa, và internet là một vấn đề thiết yếu để phát triển ứng dụng của công nghiệp tự động. chính vì vậy mà các vấn đề về internet đang ngày càng mở rộng và phức tạp hơn, một trong những vấn đề đó là an toàn mạng máy tính. các cuộc tấn công với quy mô lớn thường xuyên xảy ra , như là cuộc tấn công vào github vừa rồi - đó là một cuộc tấn công DDOS điển hình .  với lưu lượng băng thông lên đến 1,35 Tbps. một con số kinh khủng so với lưu lương băng thông vài Mbps trên đường truyền của nhà mỗi người . vậy thì DDOS là gì và tại sao nó lại mạnh đến như vậy, hôm nay chúng ta sẽ đi vào tìm hiểu nó .

## 2.  giới thiệu nội dung

 - ok ! nội dung hôm nay chúng ta sẽ tìm hiểu gồm có:
  <ul>
  <li> phần đầu giới thiệu về tổng quan ở phần này chúng ta sẽ phân tích xem DDOS là gì và mục đích của nó.</li>
  <li> phần 2 sẽ giới thiệu cho các bạn về các phương thức tấn công, dấu hiệu và cơ sở lý thuyết để một cuộc tấn công DDOS được thực hiện thành công.</li>
  <li> phần 3 giới thiệu đến các bạn các tool phổ biến để thực hiện tấn công DDOS và cách thức vận hành tool này . thêm vào đó sẽ là phần demo tấn công web side của trường do hai bạn quí và sơn thực hiện bằng công cụ DDOS  đã được dùng trong cuộc tấn công github vừa qua. thông qua demo thì chúng ta sẽ hiểu hơn về cơ chế của DDOS và đi dến phần cuối là cơ chế để bảo vệ hệ thống .</li>
  </ul>

## 4 DDOS là gì và mục đích của nó. 

 - DDOS là viết tắt của distributed denial of service , dịch ra thì nó có nghĩa là từ chối dịch vụ phân tán . đó là một cuộc tấn công mà qua đó một (hoặc một nhóm) người có thể làm cho một hệ thống không thể sử dụng được hoặc làm chậm đáng kể hệ thống cho người dùng hợp pháp bằng cách quá tải các tài nguyên để không ai có thể truy cập nó, nói một cách dễ hiểu thì làm rớt mạng. 

## vậy thì mục đích của nó là gì 
 
 - thứ nhất : Cố gắng khai thác tối đa tài nguyên phần cứng của máy chủ làm cho hệ thống bị treo. 

 - thứ hai : Ngăn chặn những người dùng cụ thể truy cập một dịch vụ nào đó
 
 - thứ ba : Nhắm vào các trang mạng hay server tiêu biểu như ngân hàng, cổng thanh toán thẻ tín dụng và thậm chí DNS root servers

 - đây là một bài báo viết về vụ tấn công github và làm sập nó khoảng 10p . nghe thì có vẻ ít nhưng chừng đó củng làm một trang web lớn thiệt hại hàng ngàn đô rồi đấy .

## 5.

 - vậy thì làm cách nào để một cuộc tấn công ddos gây ra hậu quả như vậy , chúng ta sẽ tìm hiểu về phương thức tấn công của nó . đầu tiên đa số các cuộc tấn công từ chối dịch vụ đều Nhằm tiêu tốn tài nguyên tính toán như băng thông, dung lượng đĩa cứng hoặc thời gian xử lý . như các bạn có thể thấy trong hình , khi một cuộc tấn công DDOS xảy ra , băng thông sẽ tăng một cách bất thường, kèm theo đó là mạng giật và lag đó là những dấu hiệu của một cuộc tấn công đang xảy ra.

## 6  

 - tiếp theo, một hình thức củng rất hay được sử dụng trong tấn công DDOS là Phá vỡ các thông tin cấu hình như thông tin định tuyến. như các bạn đã biết , khi các router chạy các giao thức định tuyến động như ospf , eigrp hay giữa các ISP thì có giao thức BGP thì để duy trì được tráng thái ổn định của hệ thống các router này phải gửi ra gói tin hello định kỳ để báo cho hàng xóm biết mình vẫn ổn . khi một cuộc tấn công ddos xảy ra , các gói tin này bị nghẽn lại và dẫn đến tình trạng cập nhật thông tin cấu hình bị lỗi. 

 - ngoài ra tấn công ddos còn có thể Phá vỡ các trạng thái thông tin như việc tự động reset lại các phiên TCP. ở phần sau chúng ta sẽ tìm hiểu về phương thức tấn công SYN attack , là một ví dụ điển hình cho việc tấn công vào cơ chế của chồng giao thức tcp

 - Phá vỡ các thành phần vật lý của mạng máy tính. điều này xảy ra khi mà một thiết bị mạng phải xử lý quá nhiều gói tin trong thời gian ngắn dẫn đến quá tải phần cứng , lúc đó sẽ dẫn tới treo hoặc reboot lại thiết bị dẫn đến cả hệ thống mạng bị sập. 

 - mục tiêu cuối cùng là Làm tắc nghẽn thông tin liên lạc có chủ đích giữa các người dùng và nạn nhân dẫn đến việc liên lạc giữa hai bên không được thông suốt.



## 7 
 
 - 1 Ping of Death là kỹ thuật tấn công làm quá tải hệ thống mạng bằng cách gửi các gói tin ICMP có kích thước vượt quá 65.536 byte đến mục tiêu. Do kích thước này lớn hơn kích thước cho phép của các gói tin IP nên nó sẽ được chia nhỏ ra rồi gửi từng phần đến máy đích. Khi đến mục tiêu, nó sẽ được ráp lại thành gói tin hoàn chỉnh, do có kích thước quá mức cho phép, nó sẽ gây ra tràn bộ nhớ đệm và bị treo.

 - 2 SSping là một cuộc tấn công DDOS ở cấp độ mạng, cơ chế hoạt động của nó như sau . ở trường hợp thông thường , khi một gói tin có kích thước lớn được gửi qua môi trường internet, các gói tin sẽ được chia nhỏ ra (hoạt động này gọi là phân mãnh gói tin) và đánh số cho từng gói tin, ở phía máy nhận , nó sẽ sử dụng ngăng xếp TCP/ IP để lắp ráp lại các gói tin bị phân mãnh để thành 1 gói hoàn chỉnh . khi tấn công , kẻ tấn công cố gắng dùng các gói tin có phân đoạn lớn, như vậy máy nạn nhân sẽ phải tiêu tốn ngăn xếp để lắp ráp gói tin lại. khi ngăn xếp này đầy , thì máy nạn nhân sẽ quá tải. 

 - 3 land attack , trong tình huống này , kẻ tấn công sẽ gửi gói syn tới mục tiêu với ip đích , ip nguồn , port nguồn , port đich giống nhau , như vậy máy mục tiêu sẽ không biết phải làm gì dẫn đến máy bị treo .

 - 4 Smurf : với kỹ thuật này, máy tính của kẻ tấn công sẽ giả mạo IP của nạn nhân và gửi gói tin broadcast ra bên ngoài , khi các máy khác trên cùng mạng đó nhận được thì nó sẽ đáp trả lại IP đích - chính là Ip của nạn nhân, do một lượng lớn gói tin phản hồi nên máy đích sẽ bị quá tải .

 - 5 SYN Flood : một hình thức tấn công rất phổ biến hiện nay , trong đó , máy của kẻ tấn công sẽ gửi các gói ICMP với cờ SYN được bật để báo hiệu bắt đầu một tiến trình kết nối. lúc này máy mục tiêu sẽ gửi 1 gói tin ack trở về và chờ đợi đáp trả từ máy cuẩ kẻ tấn công , nhưng gói tin trả lời sẽ không được gửi , dẫn đến máy mục tiêu sẽ phải dành ra một lượng tài nguyên chờ, cứ như vậy kẻ tấn công lại tiếp tục thực hiện điều tương tự dẫn đến tiêu hao hết tài nguyên của máy nạn nhân và cuối cùng máy nạn nhân sẽ bị treo hoặc khởi động lại.  


 ngoài ra còn có rất nhiều các kỹ thuật khác , nhưng 5 kỹ thuật trên đây là phổ biến nhất . ngoài ra còn có ...Win Nuke, RPC Locator, Jolt2, Bubonic, CPU Hog 

## 8. 
 
 - khi một hệ thống đang bị tấn công chúng ta có thể dễ dàng nhận ra nó bằng các cách sau :
 <ul>
 <li>Mạng thực thi chậm khác thường khi mở tập tin hay truy cập Website</li>
 <li>Không thể dùng một website cụ thể</li>
 <ll>Không thể truy cập bất kỳ website nào</li>
 <li>Tăng lượng thư rác nhận được</li>
 </ul>

## 9+10. 

 - hiện tại để thực thi 1 cuộc tấn công DDOS có rất nhiều công cụ , một số trong đó khá phổ biến và có thể tìm thấy ở trên mạng.

1. Tribal Flood Network 2000 (TFN2K)
2. Trinoo
3. Stacheldraht

- trong đó thì tribal và stacheldraht là 2 công cụ không chính thống còn trinoo là công cụ được phát hành chính thống . 

- trong trinoo máy của kẻ tấn công sẽ điều khiển các máy chủ và gọi đó là các masters , các masters sẽ điều kiển các máy zombie và gọi là các deamons . giữa kẻ tấn công master và deamon liên lạc với nhau thông qua các port mặc định 
-  Attacker - master: 27665/tcp
-  Master - daemon: 27444/udp
-  Daemon -  master: 31335/udp

 - chính những deamon mới thực sự là những máy trực tiếp thực hiện tấn công , còn kẻ tấn công chỉ điều khiển từ xa. như vậy có thể ẩn giấu được vị trí của mình với mục tiêu .


## 11 

 - sau đây là phần trình diễn tấn công DDOS do quí và sơn thực hiện , mục tiêu là web của học viện sử dụng tool t50 và hình thức syn attack để tấn công


## 12 

 - vừa rồi là phần trình diễn tấn công , qua đó chúng ta thấy được sự nguy hiểm của cuộc tấn công DDOS và cách thức nó được khởi tạo. đồng thời chúng ta nhận thấy rằng , tấn công DDOS là không thể ngăn chặn triệt để mà chỉ có thể hạn chế , nên sau đây là các đề xuất để phòng tránh và giảm nhẹ thiệt hại của hệ thống đối với việc tấn công DDOS. 

 - Thiết kế hệ thống mạnh mẽ và hiệu quả
 - Giới hạn băng thông
 - Cập nhật các bản vá thường xuyên
 - Chạy số lượng dịch vụ ít nhất
 - Chỉ cho phép lưu lượng truy cập cần thiết
 - Chặn địa chỉ IP
 - Giữ an toàn cho mạng
 - Cài đặt hệ thống phát hiện xâm nhập

 
