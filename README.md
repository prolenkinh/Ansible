
# Tổng quan về Ansible
![image](https://user-images.githubusercontent.com/129259654/229782993-26794af9-4404-4240-b431-dbfa73c13a01.png)
  Ansible là một công cụ quản lý, triển khai và điều phối cấu hình CNTT mã nguồn mở. Nó nhằm mục đích cung cấp mức tăng năng suất lớn trước nhiều thách thức tự động hóa. Công cụ này rất đơn giản để sử dụng nhưng đủ mạnh để tự động hóa các môi trường ứng dụng CNTT nhiều tầng phức tạp.
 ### Tại sao chúng ta cần Ansible?
  Chúng ta hãy thử hồi tưởng một chút về sự khởi đầu của máy tính nối mạng khi việc triển khai và quản lý máy chủ một cách đáng tin cậy và hiệu quả là một thách thức. Trước đây, các quản trị viên hệ thống quản lý các máy chủ bằng tay, cài đặt phần mềm, thay đổi cấu hình và quản trị các dịch vụ trên các máy chủ riêng lẻ.
  
  Khi các trung tâm dữ liệu phát triển và các ứng dụng được lưu trữ trở nên phức tạp hơn, các quản trị viên nhận ra rằng họ không thể mở rộng quy mô quản lý hệ thống thủ công của mình nhanh như các ứng dụng. Nó cũng cản trở tốc độ công việc của các nhà phát triển vì nhóm phát triển nhanh chóng và thường xuyên phát hành phần mềm, nhưng các hoạt động CNTT đang dành nhiều thời gian hơn cho việc cấu hình hệ thống. Đó là lý do tại sao các công cụ quản lý cấu hình và cung cấp máy chủ trở nên phát triển mạnh mẽ.
  
Hãy xem xét công việc quản trị một đội máy chủ thường xuyên tẻ nhạt. Chúng ta luôn cần cập nhật, đẩy các thay đổi, sao chép các tệp tin trên chúng, v.v. Những tác vụ này khiến mọi thứ trở nên rất phức tạp và tốn thời gian. Nhưng không cần quá lo lắng về điều đó vì chúng ta đã có giải pháp. Giải pháp đó chính là - Ansible. Nhưng trước khi hiểu nhiều hơn về Ansible, chúng ta hãy làm quen với một số thuật ngữ Ansible như:
+ Controller Machine: Nơi Ansible được cài đặt, chịu trách nhiệm chạy cấp phép trên các máy chủ mà bạn đang quản lý.
+ Inventory: Tệp khởi tạo chứa thông tin về các máy chủ (hosts) mà bạn đang quản lý.
+ Playbook: Điểm đầu vào để cung cấp cho Ansible, nơi tự động hóa được xác định thông qua các tác vụ sử dụng định dạng YAML.
+ Task: Một khối xác định một thủ tục sẽ được thực thi. Ví dụ: Cài đặt một package
+ Module: Một mô-đun thường tóm tắt một nhiệm vụ hệ thống, như xử lý các gói hoặc tạo và thay đổi tệp. Ansible có vô số mô-đun tích hợp, nhưng bạn cũng có thể tạo những mô-đun tùy chỉnh.
+ Role: Một cách được xác định trước để tổ chức playbook và các tệp khác nhằm tạo điều kiện chia sẻ và sử dụng lại các phần của cấp phép.
+ Play: Một cung cấp được thực hiện để thực thi các Task.
+ Facts: Các biến toàn cục chứa thông tin về hệ thống, như giao diện mạng hoặc hệ điều hành.
+ Handlers: Được sử dụng để kích hoạt các thay đổi trạng thái dịch vụ, chẳng hạn như khởi động lại hoặc dừng một dịch vụ.

Ansible là một công cụ hữu ích cho phép bạn tạo các nhóm máy, mô tả cách cấu hình các máy này hoặc những hành động nên thực hiện trên chúng. Ansible đưa ra tất cả các lệnh từ một vị trí trung tâm để thực hiện các tác vụ này.
  
Không có phần mềm máy khách nào khác được cài đặt trên các node (nút). Nó sử dụng SSH để kết nối với các node. Ansible chỉ cần được cài đặt trên máy điều khiển (máy mà bạn sẽ chạy lệnh), thậm chí có thể là máy tính xách tay của bạn. Nó là một giải pháp đơn giản cho một vấn đề phức tạp. 
 ### Ưu điểm của việc sử dụng Ansible
 - Simple(Đơn giản)
 
 ![image](https://user-images.githubusercontent.com/129259654/229785341-555e0de3-6eb0-4156-a711-221c82e7824b.png)
 
Ansible sử dụng một cú pháp đơn giản được viết bằng YAML được gọi là playbooks . YAML là một ngôn ngữ tuần tự hóa dữ liệu mà con người có thể đọc được. Vì vậy, không có kỹ năng mã hóa đặc biệt nào được yêu cầu và ngay cả những người trong tổ chức CNTT của bạn, những người không biết Ansible là gì cũng có thể đọc một cuốn sách và hiểu điều gì đang xảy ra. Ansible luôn thực hiện các nhiệm vụ theo thứ tự. Nó cũng đơn giản để cài đặt. Nhìn chung, sự đơn giản đảm bảo rằng bạn có thể bắt đầu nhanh chóng.

- Agentless (Không có tác nhân)

![image](https://user-images.githubusercontent.com/129259654/229785439-f3f6c9a1-4acd-4625-bf46-24eee5d1d89e.png)

Cuối cùng, Ansible hoàn toàn không có tác nhân. Không có tác nhân / phần mềm hoặc cổng tường lửa bổ sung nào mà bạn cần cài đặt trên hệ thống máy khách hoặc máy chủ mà bạn muốn tự động hóa .  Bạn không phải thiết lập riêng một cơ sở hạ tầng quản lý bao gồm quản lý toàn bộ hệ thống, mạng và bộ nhớ của bạn. Ansible giảm hơn nữa nỗ lực cần thiết cho nhóm của bạn để bắt đầu tự động hóa ngay lập tức.
- Powerful & Flexible (Mạnh mẽ và linh hoạt)

![image](https://user-images.githubusercontent.com/129259654/229785612-29972f9d-4e00-48c8-b6b1-fedee432af30.png)

Ansible có các tính năng mạnh mẽ có thể cho phép bạn lập mô hình ngay cả những quy trình công việc CNTT phức tạp nhất. Ansible có thể quản lý cơ sở hạ tầng, mạng, hệ điều hành và dịch vụ mà bạn đang sử dụng, vì Ansible cung cấp cho bạn hàng trăm mô-đun để quản lý chúng. Các khả năng của Ansible cùng nhau cho phép bạn điều phối toàn bộ môi trường ứng dụng bất kể nó được triển khai ở đâu.
- Efficient (Hiệu quả)

![image](https://user-images.githubusercontent.com/129259654/229785720-081da931-9f06-46f5-a65d-a843ddb76b31.png)

Không có phần mềm bổ sung trên máy chủ của bạn có nghĩa là nhiều tài nguyên hơn cho các ứng dụng của bạn. Ngoài ra, vì các mô-đun Ansible hoạt động thông qua JSON, Ansible có thể mở rộng với các mô-đun được viết bằng ngôn ngữ lập trình mà bạn đã biết. Ansible giới thiệu các mô-đun làm khối xây dựng cơ bản cho phần mềm của bạn. Vì vậy, bạn thậm chí có thể tùy chỉnh nó theo nhu cầu của mình.
### Ansible có thể làm được những gì?
Ansible thường được nhóm cùng với các công cụ quản lý cấu hình khác như Puppet, Chef, SaltStack, v.v. Vì vậy, Ansible không chỉ giới hạn ở quản lý cấu hình. Nó cũng có thể được sử dụng theo nhiều cách khác nhau. Bên dưới đã đề cập đến một số trong số chúng dưới đây:
- Provisioning

![image](https://user-images.githubusercontent.com/129259654/229786100-edc340e3-9736-47d1-8796-f28b06b0f139.png)

Ứng dụng của bạn phải tồn tại ở một nơi nào đó. Nếu bạn đang khởi động PXE (Preboot eXecution Environment) và khởi động máy chủ kim loại thô hoặc Máy ảo, hoặc tạo các phiên bản ảo hoặc đám mây từ các mẫu, Ansible & Ansible Tower sẽ giúp đơn giản hóa quy trình này. Tôi cũng sẽ cần cài đặt Visual Studio trong máy tính của bạn. Đây là lúc Ansible đảm bảo rằng các gói yêu cầu được tải xuống và cài đặt để cung cấp ứng dụng của tôi.

- Configuration Management

![image](https://user-images.githubusercontent.com/129259654/229786193-7353d820-0a7d-49a4-8da6-13637e93da29.png)

Nó thiết lập và duy trì tính nhất quán về hiệu suất của sản phẩm bằng cách ghi lại và cập nhật thông tin chi tiết mô tả phần cứng và phần mềm của doanh nghiệp. Thông tin đó thường bao gồm các phiên bản và bản cập nhật đã được áp dụng cho các gói phần mềm đã cài đặt cũng như vị trí và địa chỉ mạng của các thiết bị phần cứng. 

•	Application Deployment

 ![image](https://user-images.githubusercontent.com/129259654/229786418-a63ff771-7528-475c-b41f-954b039902d6.png)

Khi bạn xác định ứng dụng của mình với Ansible và quản lý việc triển khai với Ansible Tower, các nhóm có thể quản lý hiệu quả toàn bộ vòng đời ứng dụng từ phát triển đến sản xuất. Nhưng tại sao phải lo lắng về việc thực hiện từng bước một khi chúng ta có một công cụ như Ansible. Tất cả những gì bạn cần làm là liệt kê các tác vụ này trong sách phát Ansible của mình và ngồi xem Ansible thực hiện các tác vụ này theo thứ tự.

•	Security and Compliance

 ![image](https://user-images.githubusercontent.com/129259654/229786439-587584fe-7f9e-4f5e-80ce-f8121ca6ed06.png)
 
Khi bạn xác định chính sách bảo mật của mình trong Ansible, việc quét và khắc phục chính sách bảo mật trên toàn trang có thể được tích hợp vào các quy trình tự động khác. Và nó sẽ không thể thiếu trong mọi thứ được triển khai. Điều đó có nghĩa là, bạn cần phải định cấu hình các chi tiết bảo mật của mình một lần trong máy điều khiển của bạn và nó sẽ được nhúng vào tất cả các nút khác một cách tự động. Hơn nữa, tất cả thông tin đăng nhập (id người dùng quản trị và mật khẩu) được lưu trữ trong Ansible không thể truy xuất được ở dạng văn bản thuần bởi bất kỳ người dùng nào.

•	Orchestration

 ![image](https://user-images.githubusercontent.com/129259654/229786475-69cf63f1-ca05-4f88-a9c6-f873d2a29337.png)
 
Chỉ riêng cấu hình không xác định môi trường của bạn. Bạn cần xác định cách nhiều cấu hình tương tác và đảm bảo các phần khác nhau có thể được quản lý một cách tổng thể. Thoát khỏi sự phức tạp và hỗn loạn, Ansible mang lại trật tự. Ansible cung cấp Orchestration theo nghĩa điều chỉnh yêu cầu kinh doanh với các ứng dụng, dữ liệu và cơ sở hạ tầng. Nó xác định các chính sách và cấp độ dịch vụ thông qua quy trình làm việc tự động, cung cấp và quản lý thay đổi. Điều này tạo ra một cơ sở hạ tầng phù hợp với ứng dụng có thể được mở rộng hoặc thu nhỏ dựa trên nhu cầu của từng ứng dụng.

