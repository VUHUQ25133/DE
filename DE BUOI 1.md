# Buổi 1: CƠ SỞ DỮ LIỆU

## 1. CSDL là gì?
### 1.1. Khái niệm CSDL: 
CSDL là một bộ sưu tập dữ liệu có hệ thống, được lưu trữ bằng điện tử. Nó có thể chứa bất kỳ loại dữ liệu nào, bao gồm từ, số, hình ảnh, video và tệp. Bạn có thể sử dụng phần mềm được gọi là hệ thống quản lý CSDL (DBMS) để lưu trữ, truy xuất và chỉnh sửa dữ liệu. Trong các hệ thống máy tính, CSDL từ cũng có thể tham khảo bất kỳ DBMS, đến hệ thống CSDL, hoặc một ứng dụng liên kết với CSDL.

### 1.2. Tại sao CSDL lại quan trọng?
CSDL hiệu năng cao có ý nghĩa quan trọng đối với bất kỳ tổ chức nào. CSDL hỗ trợ các hoạt động nội bộ trong công ty và lưu trữ hoạt động tương tác với khách hàng cũng như nhà cung cấp. Chúng cũng lưu giữ thông tin quản trị và nhiều dữ liệu chuyên biệt hơn, chẳng hạn như các mô hình kỹ thuật hoặc kinh tế. Ví dụ bao gồm hệ thống thư viện kỹ thuật số, hệ thống đặt chỗ du lịch và hệ thống kiểm kê. Sau đây là một số lý do cho thấy mức độ quan trọng của CSDL.

- **Điều chỉnh quy mô hiệu quả**: Các ứng dụng CSDL có thể quản lý một lượng lớn dữ liệu, giúp điều chỉnh quy mô thành hàng triệu, hàng tỷ và hơn thế nữa. Nếu không có CSDL thì không thể lưu trữ lượng dữ liệu kỹ thuật số này.

- **Tính toàn vẹn của dữ liệu**: CSDL thường có những quy tắc và điều kiện tích hợp để duy trì tính nhất quán của dữ liệu.

- **Bảo mật dữ liệu**: CSDL hỗ trợ những yêu cầu về quyền riêng tư và khả năng tuân thủ liên quan đến bất kỳ dữ liệu nào. Ví dụ: để có quyền truy cập CSDL, người dùng phải đăng nhập. Người dùng khác nhau cũng có thể được truy cập ở những cấp độ khác nhau, chẳng hạn như chỉ đọc.

- **Phân tích dữ liệu**: Hệ thống phần mềm hiện đại sử dụng CSDL để phân tích dữ liệu. Những hệ thống này có thể xác định các xu hướng và mẫu hoặc đưa ra dự đoán. Hoạt động phân tích dữ liệu giúp tổ chức tự tin đưa ra quyết định kinh doanh.

### 1.3. CSDL có công dụng gì?
Tất cả các ngành công nghiệp sử dụng CSDL cho nhiều trường hợp sử dụng khác nhau. Sau đây là một số ví dụ:

**- Phát hiện gian lận**: CSDL đồ thị hỗ trợ quản lý danh tính và phát hiện gian lận. Thuật toán máy học tìm ra mẫu và phát hiện hoạt động gian lận một cách tự động và chủ động.

**- Quản lý tài liệu**: CSDL NoSQL lưu trữ và quản lý tài liệu, chẳng hạn như các bài viết và hợp đồng. Những CSDL này cũng cho phép các tổ chức truy vấn và lập chỉ mục tài liệu.

**- Trò chơi và giải trí**: Nhiều công ty trò chơi và giải trí vận dụng CSDL một cách sâu rộng, giúp mang lại trải nghiệm đa phương tiện phong phú, chẳng hạn như hàng triệu người dùng có thể truy cập đăng nhập đồng thời.


## 2. Hệ quản trị CSDL là gì?

Hệ quản trị CSDL (Database Management System - DBMS) là một hệ thống phần mềm giúp quản lý, lưu trữ, truy xuất và chỉnh sửa các dữ liệu một cách có tổ chức và hiệu quả. DBMS là “cầu nối" giữa CSDL và người dùng hoặc các ứng dụng để thực hiện các hoạt động tạo, truy vấn, sửa đổi và xóa dữ liệu.

Hay hiểu đơn giản, hệ quản trị CSDL là hệ thống tự động hỗ trợ người dùng kiểm soát các thông tin, tạo dựng, cập nhật và duy trì các CSDL.

### 2.1. Cấu trúc của hệ quản trị cơ sở dữ liệu bao gồm những gì?
Cấu trúc chính của hệ quản trị cơ sở dữ liệu thường được chia thành:

**Thao tác với DBMS**
Các thao tác chính này gồm các thay đổi sơ đồ, các truy vấn và các thay đổi dữ liệu. Cụ thể các truy vấn sẽ là những yêu cầu về dữ liệu, hỏi đáp trong DBMS. Các thay đổi sơ đồ là việc thay đổi của người dùng quản trị cơ sở dữ liệu như tạo lập cơ sở dữ liệu mới hoặc thay đổi cấu trúc sơ đồ cơ sở dữ liệu. Thay đổi dữ liệu bao gồm việc xóa, cập nhật, sửa đổi dữ liệu trong hệ cơ sở dữ liệu. Các thao tác này sẽ nằm ở phần đỉnh của cấu trúc hệ quản trị cơ sở dữ liệu.

- **Bộ xử lý câu hỏi**: Phần này chịu trách nhiệm xử lý các truy vấn từ người dùng. Các nhiệm vụ thực hiện trong bộ xử lý câu hỏi gồm phân tích các truy vấn, tạo các kế hoạch thực thi và thực thi kế hoạch.

- **Bộ quản lý lưu trữ**: Có trách nhiệm lưu trữ, truy xuất dữ liệu trên các thiết bị lưu trữ như đĩa cứng, bộ nhớ. 

- **Bộ quản lý giao dịch**: Bộ quản lý giao dịch bao gồm cả bộ quản lý lưu trữ và bộ xử lý câu hỏi, thực hiện các nhiệm vụ bảo đảm tính toàn vẹn, tính nhất quán và tính phục hồi của dữ liệu.

- **Dữ liệu và siêu dữ liệu**: Đây là thành phần gồm các dữ liệu, thông tin về dữ liệu như cấu trúc, các ràng buộc và thuộc tính của dữ liệu. Lớp dữ liệu và siêu dữ liệu nằm ở phần đáy của kiến trúc DBMS, là thành phần chính để tạo nên hệ quản trị cơ sở dữ liệu.

### 2.2. Những đặc điểm của hệ quản trị cơ sở dữ liệu là gì?

- DBMS có tính bảo mật cao, cung cấp các cơ chế để bảo vệ dữ liệu khỏi bị mất cắp thông tin qua tài khoản và mật khẩu.
- Hệ quản trị cơ sở dữ liệu có thể sử dụng để lưu trữ, quản lý nhiều loại dữ liệu khác nhau.
- Cho phép mở rộng để đáp ứng nhu cầu của các ứng dụng có quy mô lớn. 
- Ứng dụng các kỹ thuật tối ưu hóa nhằm truy xuất dữ liệu, cập nhật thông tin nhanh chóng và hiệu quả.
- Tập trung dữ liệu vào một nơi duy nhất, ví dụ như máy chủ, giúp người dùng dễ dàng truy cập dữ liệu từ bất kỳ vị trí nào.
- Có thể chia sẻ và xử lý dữ liệu đa người dùng.
- Hỗ trợ triển khai trên các nền tảng đa dạng.
- DBMS tuân thủ theo tính chất ACID, gồm Atomicity (tính nguyên tử), Consistency (tính nhất quán), Isolation (tính độc lập), Durability (tính bền vững).

### 2.3. Phân loại hệ quản trị cơ sở dữ liệu
Hiện nay có nhiều hệ quản trị cơ sở dữ liệu được phân loại theo các tiêu chí khác nhau. Dưới đây là những cách phân loại hệ quản trị cơ sở dữ liệu phổ biến:

#### Theo mô hình dữ liệu
- **Hệ quản trị cơ sở dữ liệu quan hệ**: Đây là hệ quản trị cơ sở dữ liệu phổ biến nhất. Các dữ liệu được tổ chức dưới dạng bảng có hàng, cột ràng buộc để lưu trữ và quản lý dữ liệu.
- **Hệ quản trị cơ sở dữ liệu phi quan hệ**: Các dữ liệu được tổ chức không theo mô hình quan hệ, thường dùng để quản lý, lưu trữ dữ liệu phi cấu trúc như văn bản, video, hình ảnh.
#### Theo cách lưu trữ
- **Lưu trữ trên bộ nhớ**: Lưu trữ dữ liệu trong bộ nhớ RAM để cung cấp tốc độ truy xuất nhanh.
- **Lưu trữ trên đĩa cứng**: Các dữ liệu được lưu trữ trên đĩa cứng.
#### Theo mức độ phân tán
- **Hệ quản trị cơ sở dữ liệu cục bộ**: Dữ liệu được lưu trữ trên máy tính cục bộ, được sử dụng cho các ứng dụng nhỏ và có quy mô vừa phải.
- **Hệ quản trị cơ sở dữ liệu phân tán**: Là loại hệ quản trị cơ sở dữ liệu lưu trữ dữ liệu trên nhiều máy tính, được sử dụng cho các ứng dụng có quy mô lớn và có yêu cầu khả năng mở rộng cao.

### 2.4. Các chức năng chính của hệ quản trị cơ sở dữ liệu là gì?
Hệ quản trị cơ sở dữ liệu cung cấp nhiều chức năng quan trọng, bao gồm:

- **Tạo và quản lý cơ sở dữ liệu**: Hệ quản trị cơ sở dữ liệu giúp người dùng tạo lập cơ sở dữ liệu, cấu trúc của cơ sở dữ liệu, thêm, sửa và xóa dữ liệu trong cơ sở dữ liệu.
- **Truy vấn dữ liệu**: DBMS cung cấp các công cụ để người dùng truy vấn dữ liệu trong cơ sở dữ liệu, chẳng hạn như ngôn ngữ truy vấn SQL.
- **Bảo mật dữ liệu**: Hệ quản trị cơ sở dữ liệu có chức năng giúp bảo vệ dữ liệu khỏi các truy cập trái phép, chẳng hạn như sử dụng các cơ chế xác thực và cấp phép.
- **Sao lưu, khôi phục dữ liệu**: Chức năng của DBMS là giúp khôi phục, sao lưu dữ liệu trong trường hợp dữ liệu bị mất hoặc bị hỏng.

