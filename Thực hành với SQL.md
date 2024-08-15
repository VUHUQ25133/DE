# 1. Các hàm toán học

|     Hàm     | Mô tả                                                                          |Ví dụ        | Kết quả      |
|-------------|--------------------------------------------------------------------------------|-------------|--------------|
|ABS          | Tính giá trị tuyệt đối của một số                                              |ABS(-10)     | 10           |
|CBRT         | Tính toán khối lập phương của một số                                           |CBRT(8)      | 2            |
|CEIL//CEILING| Làm tròn một số lên tới số nguyên gần nhất, lớn hơn hoặc bằng số đó            |CEIL(-12.8)  | -12          |
|DEGREES      | Chuyển đổi radian sang độ                                                      |DEGREES(0.8) | 45.83662361  |
|DIV          | Trả về thương số nguyên của hai giá trị số                                     |DIV(8,3)     | 2            |
|EXP          | Trả về giá trị số mũ trong ký hiệu khoa học của một số đó                      |EXP(1)       | 2.718281828  |
|FLOOR        | Làm tròn một số xuống số nguyên gần nhất, nhỏ hơn hoặc bằng số đó              |FLOOR(10.6)  | 10           |
|LN           | Trả về logarit tự nhiên của một giá trị số                                     |LN(3)        | 1.098612289  |
|LOG          | Trả về logarit cơ sở 10 của một giá trị số                                     |LOG(1000)    | 3            |
|LOG          | Trả lại logarit của một giá trị số cho một cơ sở được chỉ định                 |LOG(8, 64)   | 2            |
|MOD          | Chia tham số đầu tiên cho tham số thứ hai và trả lại phần còn lại              |MOD(10,4)    | 2            |
|PI           | Trả về giá trị của PI                                                          |PI()         | 3.141592654  |
|POWER        | Nâng một giá trị số lên số mũ của giá trị số thứ hai                           |POWER(5, 3)  | 125          |
|RADIANS      | Chuyển đổi độ sang radian                                                      |RADIANS(60)  | 1.047197551  |
|ROUND        | Làm tròn số đến số nguyên gần nhất hoặc đến một vị trí thập phân được chỉ định |ROUND(10.3)  | 10           |
|SCALE        | Trả về số chữ số thập phân trong phần phân số                                  |SCALE(1.234) | 3            |
|SIGN         | Trả về dấu (dương, âm) của một giá trị số                                      |SIGN(-1)     | -1           |
|SQRT         | Trả về căn bậc hai của một giá trị số                                          |SQRT(3.0)    | 1.732050808  |
|TRUNC        | Cắt bớt một giá trị số thành toàn bộ số đến các vị trí thập phân được chỉ định |TRUNC(12.3)  | 12           |
|WIDTH_BUCKET | Gán các giá trị cho các nhóm trong biểu đồ chiều rộng bằng nhau.               |             |              |

# 2. Thao tác với văn bản

## 2.1. Length Function
Xác định số lượng ký tự trong chuỗi là điều bạn sẽ sử dụng thường xuyên khi làm việc với dữ liệu trong cơ sở dữ liệu SQL. Nhiều tình huống sẽ yêu cầu bạn tìm độ dài của chuỗi được lưu trữ trong cơ sở dữ liệu của bạn. 
Ví dụ: bạn có thể cần giới hạn số lượng ký tự được hiển thị trong một ứng dụng hoặc bạn có thể cần đảm bảo rằng một cột trong tập dữ liệu của bạn chứa các giá trị có cùng độ dài.

Hàm **CHAR_LENGTH** có thể được sử dụng để xác định số lượng ký tự trong chuỗi. **CHAR_LENGTH** chấp nhận một chuỗi làm đầu vào và trả về số lượng ký tự trong chuỗi dưới dạng số nguyên cho đầu ra.

**LENGTH** tương tự **CHAR_LENGTH**, chấp nhận cùng một tham số và trả về kết quả giống như bạn có thể thấy trong ví dụ này.
```sql
    SELECT CHAR_LENGTH('CodeLearn'); --9
    SELECT LENGTH('CodeLearn'); --9
```
Hai chức năng này có thể được sử dụng thay thế cho nhau tùy theo sở thích của bạn

## 2.2. Left Function (Right Function)
Hàm **LEFT** cho phép bạn trích xuất n kí tự đầu tiên của chuỗi. Tham khảo ví dụ dưới đây:
```sql
    SELECT LEFT('This is the description.', 7); --Kết quả là: This is 
    SELECT LEFT('Codelearn1 Codelearn2', 9); --Kết quả là: Codelearn
```
Hàm **RIGHT** cũng giống với **LEFT** nhưng như bạn có thể đoán được, nó sẽ lấy ra n ký tự cuối cùng của chuỗi. Nói cách khác thì nó sẽ lấy từ bên phải sang.
```sql
    SELECT RIGHT('This is the description.', 12); --description.
    SELECT RIGHT('Codelearn1 Codelearn2', 10);--Kết quả là: Codelearn2
```

## 2.3. SubString Function
Hàm **SUBSTR** trả về một phần của chuỗi. Sau đây minh họa cú pháp của hàm:
```sql
    SUBSTRING(chuỗi, vị_trí_bắt_đầu, độ_dài)
```
Hãy cùng kiểm tra từng thông số chi tiết:

- *string* là một chuỗi có kiểu dữ liệu là char, varchar, text, v.v.
- *vị_trí_bắt_đầu* là một số nguyên chỉ định nơi bạn muốn trích xuất chuỗi con. Nếu *vị_trí_bắt_đầu* bằng 0, chuỗi con bắt đầu ở ký tự đầu tiên của chuỗi.
- *độ_dài* là một số nguyên dương xác định số lượng ký tự mà bạn muốn trích xuất từ ​​chuỗi bắt đầu tại *vị_trí_bắt_đầu*. Nếu tổng số *vị_trí_bắt_đầu* và độ dài lớn hơn số lượng ký tự trong chuỗi, hàm chuỗi con trả về toàn bộ chuỗi bắt đầu tại *vị_trí_bắt_đầu*. Tham số *độ_dài* là tùy chọn. Nếu bạn bỏ qua tham số *độ_dài*, hàm chuỗi con trả về toàn bộ chuỗi bắt đầu tại *vị_trí_bắt_đầu*.

Xem các ví dụ sau:
```sql
    SELECT SUBSTRING ('PostgreSQL', 1, 8); -- PostgreS
    SELECT SUBSTRING ('PostgreSQL', 8); -- SQL
```

PostgreSQL cung cấp một cú pháp khác của SUBSTR như sau:
```sql
    SUBSTRING(chuỗi FROM vị_trí_bắt_đầu FOR độ_dài);
```
Ở cách viết này, PostgreSQL đặt ba tham số thành một. Xem ví dụ sau:
```sql
    SELECT SUBSTRING ('PostgreSQL' FROM 1 FOR 8); -- PostgreS
    SELECT SUBSTRING ('PostgreSQL' FROM 8); -- SQL
```

## 2.4. Position Function
Hàm **POSITION** trả về một số nguyên biểu thị vị trí đầu tiên mà chuỗi c xuất hiện trong chuỗi s. 

Nhìn vào bảng *customers* chúng ta có thể tìm thấy vị trí của dấu *@* trong cột email.
|id|full_name       |email                              |
|--|----------------|-----------------------------------|
|1 |MARY SMITH      |MARY.SMITH@sakilacustomer.org      |
|2 |PATRICIA JOHNSON|PATRICIA.JOHNSON@sakilacustomer.org|
|3 |LINDA WILLIAMS  |LINDA.WILLIAMS@sakilacustomer.org  |
|4 |BARBARA JONES   |BARBARA.JONES@sakilacustomer.org   |

```sql
    SELECT email, POSITION('@' IN email) 
    FROM customers;
```
Kết quả trả về sẽ là:
|email                              |position|
|-----------------------------------|--------|
|MARY.SMITH@sakilacustomer.org      |   11   |
|PATRICIA.JOHNSON@sakilacustomer.org|   17   |
|LINDA.WILLIAMS@sakilacustomer.org  |   15   |
|BARBARA.JONES@sakilacustomer.org   |   14   |

## 2.5. Concat Function
Để nối hai hoặc nhiều chuỗi thành một, bạn sử dụng toán tử nối chuỗi **||** như ví dụ sau:
```sql
    SELECT 'Concatenation' || ' ' || 'Operator'; 
    -- Kết quả là: Concatenation Operator
```
Kể từ phiên bản 9.1, PostgreSQL đã giới thiệu một hàm chuỗi tích hợp có tên **CONCAT** để nối hai hoặc nhiều chuỗi thành một. 
Sau đây minh họa cú pháp của hàm **CONCAT**:
```sql
    SELECT CONCAT('CONCAT',' ', 'function'); -- Kết quả là: CONCAT function
```

## 2.6. Case of String
Sẽ có lúc bạn muốn định dạng lại một chuỗi thành chuỗi các ký tự in hoa, in thường hoặc chuỗi chứa các ký tự viết hoa ở chữ cái đầu của mỗi từ (kiểu tiêu đề). Điều này có ích trong việc chuẩn hóa dữ liệu để thao tác. Hàm **UPPER** cho phép bạn định dạng lại một chuỗi thành chữ hoa. **UPPER** chấp nhận một chuỗi làm tham số và trả về chuỗi chữ hoa.
```sql
    SELECT UPPER(email) FROM customer;
```

Hàm **LOWER** tương tự như **UPPER** nhưng thay đổi chuỗi thành một chuỗi toàn chữ thường. Sau đây là ví dụ về cột title ở bảng film:
```sql
    SELECT LOWER(title) FROM film;
```

Tương tự, hàm **INITCAP** sẽ chuyển đổi một chuỗi thành chuỗi tiêu đề - tức là kí tự đầu mỗi từ được viết hoa:
```sql
    SELECT INITCAP(title) FROM film;
```

Hãy luôn nhớ rằng chuyển đổi dữ liệu chuỗi sẽ hữu ích khi chuẩn hóa và làm sạch bộ dữ liệu.

## 2.7. Reverse Function
Hàm **REVERSE** thực hiện đúng như tên của nó, hàm **REVERSE** chấp nhận một chuỗi là tham số duy nhất của nó và trả về cùng một chuỗi theo thứ tự ngược lại như bạn thấy ở ví dụ dưới đây:
```sql
    SELECT title, REVERSE(title) FROM film;
```

## 2.8. Replace Function
Đôi khi bạn sẽ cần đảm bảo rằng dữ liệu bạn đang trích xuất không chứa bất kỳ khoảng trắng nào. Có nhiều cách tiếp cận khác nhau mà bạn có thể thực hiện để làm sạch và chuẩn bị dữ liệu cho những tình huống này. Một kỹ thuật phổ biến là thay thế bất kỳ khoảng trắng nào bằng dấu gạch dưới.

Hàm **REPLACE** sẽ tìm một chuỗi con trong một chuỗi và thay thế nó bằng một chuỗi con khác. Nhìn vào kết quả của truy vấn sau:
```sql
    SELECT description FROM film;
```
Kết quả trả về sẽ là:

|description|
|-----------|
|A Fateful Display of a Womanizer And a Mad Scientist who must Outgun a A Shark in Soviet Georgia
A Astounding Epistle of a Student And a Squirrel who must Defeat a Boy in Ancient China
A Astounding Character Study of a Madman And a Robot who must Meet a Mad Scientist in An Abandoned Fun House
A Unbelieveable Drama of a Student And a Husband who must Outrace a Sumo Wrestler in Berlin

Bạn sẽ nhận thấy rằng cụm từ *A Astounding* xuất hiện trong một vài hàng đầu tiên là sai ngữ pháp. Vì vậy, bạn muốn sửa lỗi này và thay thế tất cả các lần xuất hiện của *A Astounding* bằng *An Astounding*.

Bạn có thể sử dụng hàm **REPLACE** để làm việc này, hàm **REPLACE** nhận vào 3 tham với thông tin như sau:
- Đầu tiên là chuỗi nguồn mà bạn muốn thao tác.
- Thứ hai là chuỗi con bạn muốn tìm trong chuỗi nguồn.
- Tham số cuối cùng là chuỗi thay thế.

Vì vậy, bạn thay thế văn bản bằng truy vấn bên dưới:
```sql
    SELECT REPLACE(description, 'A Astounding', 'An Astounding') AS description 
    FROM film
```
|description|
|-----------|
A Fateful Display of a Womanizer And a Mad Scientist who must Outgun a A Shark in Soviet Georgia
An Astounding Epistle of a Student And a Squirrel who must Defeat a Boy in Ancient China
An Astounding Character Study of a Madman And a Robot who must Meet a Mad Scientist in An Abandoned Fun House
A Unbelieveable Drama of a Student And a Husband who must Outrace a Sumo Wrestler in Berlin

## 2.9. Lpad Function
Sau đây minh họa cú pháp của hàm LPAD:
```sql
    LPAD(string, length[, fill])  
```
- **string**: là một chuỗi nên được đệm ở bên trái
- **length**: là một số nguyên dương chỉ định độ dài của chuỗi kết quả sau khi đệm. Lưu ý rằng nếu chuỗi dài hơn đối số độ dài, chuỗi sẽ bị cắt ở bên phải.
- **fill**: là một chuỗi được sử dụng để đệm. Đối số điền là tùy chọn. Nếu bạn bỏ qua đối số điền, giá trị mặc định của nó là khoảng trắng.

Hàm **LPAD** trả về một chuỗi ký tự đệm trái cho các ký tự có độ dài. Hãy cùng xem một số ví dụ về việc sử dụng hàm **LPAD**. Câu lệnh sau sử dụng hàm **LPAD** để đệm thêm dấu * ở bên trái chuỗi PostgreSQL.
```sql
    SELECT LPAD('PostgreSQL',15,'*');
```
Kết quả là:

|lpad|
|----|
*****PostgreSQL

## 2.10. Trim Function
Hàm **TRIM** loại bỏ một ký tự cụ thể khỏi chuỗi. Theo mặc định, hàm **TRIM** xóa khoảng trắng (' ') nếu bạn không chỉ định rõ ràng về ký tự mà bạn muốn xóa. Hàm **TRIM** rất hữu ích khi chúng ta muốn xóa các ký tự thừa ra khỏi một chuỗi trong cơ sở dữ liệu. Chúng ta thường sử dụng **TRIM** để làm sạch dữ liệu.

Dưới đây minh họa cú pháp của hàm **TRIM**.
```sql
    TRIM([LEADING | TRAILING | BOTH] [kí_tự] FROM chuỗi)
    TRIM(LEADING kí_tự FROM chuỗi) --xóa các kí tự 'character' khỏi đầu chuỗi 
    TRIM(TRAILING kí_tự FROM chuỗi) --loại bỏ tất cả các kí tự 'character' ở cuối chuỗi
    TRIM(BOTH kí_tự FROM chuỗi) --xóa tất cả các kí tự 'character' ở đầu và cuối chuỗi
```
Hoặc chỉ đơn giản là:
```sql
    TRIM(chuỗi, 'character')
```
Xem các ví dụ sau về việc loại bỏ các khoảng trắng ở các vị trí khác nhau:
```sql
SELECT 
   TRIM(LEADING FROM '  PostgreSQL TRIM'), --Kết quả là: 'PostgreSQL TRIM'
   TRIM(TRAILING FROM 'PostgreSQL TRIM   ' ), --Kết quả là: 'PostgreSQL TRIM'
   TRIM('  PostgreSQL TRIM  '); --Kết quả là: 'PostgreSQL TRIM'
```
### Các hàm LTRIM, RTRIM và BTRIM của PostgreSQL
PostgreSQL cung cấp cho bạn các hàm **LTRIM, RTRIM và BTRIM** là phiên bản ngắn hơn của hàm **TRIM**.

- Hàm **LTRIM** loại bỏ tất cả các ký tự, khoảng trắng theo mặc định, từ đầu chuỗi.
- Hàm **RTRIM** loại bỏ tất cả các ký tự, khoảng trắng theo mặc định, từ cuối chuỗi.
- Hàm **BTRIM** là sự kết hợp của các hàm **LTRIM** và **RTRIM**.

### Xóa các ký tự khoảng trắng khỏi chuỗi
Đôi khi, chuỗi của bạn có thể chứa các ký tự khoảng trắng thừa ở giữa các từ mà bạn muốn xóa. Tuy nhiên, hàm **TRIM** chỉ cho phép bạn xóa các khoảng trắng ở đầu và cuối, không phải tất cả các ký tự khoảng trắng khác. Bạn có thể gọi hàm TRIM nhiều lần nhưng không hiệu quả.

Một cách để loại bỏ các ký tự khoảng trắng đấy khỏi chuỗi là sử dụng hàm **REGEXP_REPLACE**. Ví dụ, câu lệnh sau sẽ loại bỏ khoảng trắng thừa giữa chữ cái.
```sql
--Kết quả là: 'this is code learn'
    SELECT REGEXP_REPLACE('this     is code     learn', '\s+', ' ', 'g'); 
```
Mẫu **\s+** được giải thích như sau:
- **\s** : cách viết ngắn của biểu thức chính quy cho khoảng trắng.
- **+** : có nghĩa là 1 hoặc nhiều sự phù hợp liên tiếp.
- **'g'**: chỉ định thay thế từng chuỗi con phù hợp thay vì chỉ một chuỗi con đầu tiên.

# 3. Làm việc với ngày/giờ

## 3.1. Current Date/Time Function
Bây giờ chúng ta sẽ tìm hiểu cách truy vấn và sử dụng ngày và giờ ở thời điểm hiện tại trong các truy vấn với các mức độ chính xác khác nhau.

PostgreSQL cung cấp một số chức năng để truy xuất ngày/giờ trong thời điểm hiện tại:

**NOW** cho phép bạn truy xuất giá trị **TIMESTAMP** cho ngày và giờ hiện tại với độ chính xác micro giây cùng với múi giờ. Nếu bạn muốn lấy **TIMESTAMP** hiện tại mà không có múi giờ. Bạn có thể ép kiểu nó, hãy tham khảo ví dụ dưới đây:
```sql
    SELECT NOW(); --    2020-05-30 02:51:18.44854+07
    SELECT NOW()::TIMESTAMP; -- 2020-05-30 02:51:18.44854
```
Hàm **CURRENT_TIMESTAMP** trả về cùng kết quả với hàm NOW. Một điểm khác biệt giữa **CURRENT_TIMESTAMP** và **NOW** là với **CURRENT_TIMESTAMP** bạn có thể chỉ định một tham số đầu vào chỉ định độ chính xác của phân số trong kết quả trả về, điều này sẽ khiến kết quả có các giây được làm tròn đến số chữ số phân số được chỉ định, hãy xem ví dụ bên dưới:
```sql
SELECT CURRENT_TIMESTAMP(2);  -- 2020-05-30 02:51:18.44+00
```
Đôi khi bạn muốn lấy ngày hoặc giờ hiện tại nhưng không quan tâm đến độ chính xác của phần trăm như kiểu **TIMESTAMP**, bạn có thể sử dụng **CURRENT_DATE** hoặc **CURRENT_TIME** để đạt được mục đích này. Ngoài ra, bạn có thể sử dụng hàm **CURRENT_TIME** để lấy giá trị thời gian với múi giờ mà không có giá trị ngày.
```sql
    SELECT CURRENT_DATE; -- 2020-05-30
    SELECT CURRENT_TIME; -- 02:51:18.44854+07
```

## 3.2. Extract Function
Hàm **EXTRACT** của PostgreSQL lấy ra giá trị năm, tháng và ngày từ giá trị date/time. Dưới đây minh họa cú pháp của hàm **EXTRACT**.
```sql
    EXTRACT(trường FROM nguồn)
```
Đối số trường chỉ định trường cần lấy từ nguồn có giá trị date/time. Danh sách sau đây minh họa một số giá trị trường hợp lệ:

|Giá trị của trường|           Nếu source là TIMESTAMP                         |Nếu source là INTERVAL |
|------------------|-----------------------------------------------------------|-----------------------|
|   DAY            |Ngày của tháng (1-31)                                      |   Số ngày             |
|   DOW            |Ngày trong tuần với Chủ nhật (0) đến Thứ Bảy (6)           |   N/A                 |
|   DOY            |Ngày trong năm dao động từ 1 đến 366                       |   N/A                 |
|   HOUR           |Giờ (0-23)                                                 |   Số giờ              |   
|   MINUTE         |Phút (0-59)                                                |   Số phút             |
|   MONTH          |Tháng (1-12)                                               |   Số tháng (0-11)     |
|   WEEK           |Số của tuần đánh số tuần theo tiêu chuẩn ISO 8601 trong năm|   N/A                 |
|   YEAR           |Năm                                                        |   Giống như TIMESTAMP |

Nguồn là một giá trị của kiểu **TIMESTAMP** hoặc **INTERVAL**. Nếu bạn nhập vào một giá trị **DATE**, hàm sẽ chuyển nó thành giá trị **TIMESTAMP**.
Dưới đây là ví dụ về hàm **EXTRACT** trích xuất từ giá trị **TIMESTAMP**:
```sql
SELECT EXTRACT(YEAR FROM TIMESTAMP '2016-12-31 13:30:15');   -- Kết quả là: 2016
SELECT EXTRACT(MONTH FROM TIMESTAMP '2016-12-31 13:30:15');  -- Kết quả là: 12
SELECT EXTRACT(DOW FROM TIMESTAMP '2016-12-31 13:30:15'); -- Kết quả là: 6
SELECT EXTRACT(DOY FROM TIMESTAMP '2016-12-31 13:30:15'); -- Kết quả là: 366

-- Dưới đây là ví dụ về hàm EXTRACT trích xuất từ giá trị INTERVAL:
SELECT EXTRACT(MONTH FROM INTERVAL '6 years 5 months 4 days 3 hours 2 minutes 1 second'. ); --Kết quả là: 5
```

## 3.3. Age Function
Chúng ta thường phải tính toán độ tuổi trong các ứng dụng kinh doanh, ví dụ: độ tuổi của mọi người, số năm phục vụ của nhân viên, v.v. 
Trong PostgreSQL, bạn có thể sử dụng hàm **AGE** để thực hiện các tác vụ này. Dưới đây minh họa cú pháp của hàm **AGE**:
```sql
AGE (TIMESTAMP, TIMESTAMP); 
```
Hàm **AGE** chấp nhận hai giá trị **TIMESTAMP**. Nó trừ đi đối số thứ hai từ đối số thứ nhất và trả về một khoảng làm kết quả.

Xem ví dụ sau:
```sql
    SELECT AGE('2017-01-01','2011-06-24');  --5 years 6 mons 7 days
```
Nếu bạn muốn lấy ngày hiện tại làm đối số đầu tiên, bạn có thể sử dụng hình thức sau của hàm **AGE**:
```sql
    AGE(TIMESTAMP); 
```
Ví dụ: nếu một người có ngày sinh là *2000-01-01* và ngày hiện tại *2017-03-20*, tuổi sẽ là:
```sql
    SELECT CURRENT_DATE,  AGE(TIMESTAMP '2000-01-01');
```
|date       |         age           |
|-----------|-----------------------|
|2017-03-20    |17 years 2 mons 19 days|

## 3.4. Kiểu dữ liệu INTERVAL
Kiểu dữ liệu **INTERVAL** cho phép bạn lưu trữ và thao tác một khoảng thời gian tính bằng *năm, tháng, ngày, giờ, phút, giây, v.v ...* Sau đây minh họa các loại **INTERVAL**:
```sql
@ INTERVAL [ trường ] [ (p) ]
```
Một **INTERVAL** có kích thước lưu trữ 16 byte có thể lưu trữ một khoảng thời gian với phạm vi *từ -178.000.000 năm đến 178.000.000 năm.*

Ngoài ra, một **interval** có thể có giá trị chính xác với tùy chọn p trong phạm vi cho phép là từ 0 đến 6. 
Độ chính xác p là số chữ số phân số được giữ lại trong các trường thứ hai.

**Dấu tại (@) là tùy chọn do đó bạn có thể bỏ qua nó.**

Các ví dụ sau đây cho thấy một số giá trị khoảng:
```sql
INTERVAL '2 months ago';
INTERVAL '3 hours 20 minutes';
```
Trong nội bộ, PostgreSQL lưu trữ các giá trị khoảng thời gian là tháng, ngày và giây. Giá trị tháng và ngày là số nguyên trong khi trường giây có thể có phân số.

Các **INTERVAL** rất hữu ích khi thực hiện tính toán về ngày hay là thời gian. Ví dụ: nếu bạn muốn biết thời gian của 3 giờ 2 phút trước tại thời điểm hiện tại của năm ngoái, bạn có thể sử dụng câu lệnh sau:
```sql
SELECT
   NOW(),
   NOW() - INTERVAL '1 year 3 hours 20 minutes' AS "3 hours 20 minutes ago of last year";
```
Kết quả đầu ra là

|           now             |3 hours 20 minutes ago of last year|
|---------------------------|-----------------------------------|
|2017-02-20 20:01:54.0404-08|    2016-02-20 16:41:54.0404-08    |

### Toán tử interval
Bạn có thể áp dụng toán tử số học ( +, -, *, etc.,) cho các giá trị **interval**, ví dụ:
```sql
    SELECT INTERVAL '2h 50m' + INTERVAL '10m'; -- 03:00:00
    SELECT INTERVAL '2h 50m' - INTERVAL '50m'; -- 02:00:00
    SELECT 600 * INTERVAL '1 minute'; -- 10:00:00
```

## 3.5. TO_DATE Function
```sql
TO_DATE(text, format)
```
Hàm **TO_DATE** chấp nhận hai đối số đầu vào là chuỗi. Đối số đầu tiên là chuỗi mà bạn muốn chuyển đổi thành một ngày. Đối số thứ hai là định dạng kiểu ngày cho đối số thứ nhất. Hàm **TO_DATE** trả về giá trị **DATE**.

Xem ví dụ sau
```sql
    SELECT TO_DATE('20170103','YYYYMMDD');
```

Đầu ra cho thấy
|to_date   |
|----------|
|2017-01-03|

Do đó, hàm trả về ngày 3 tháng 1 năm 2017.

## 3.6. DATE_PART Function
Hàm **DATE_PART** sẽ giúp bạn lấy ra một trường con từ giá trị ngày hoặc thời gian đầu vào. Dưới đây minh họa cú pháp của hàm **DATE_PART**:
```sql
    DATE_PART(trường, nguồn)
```
Trường chỉ định bộ phận/giá trị nào được lấy ra từ ​​nguồn.

Nguồn là một biểu thức trả về kiểu data tạm thời (temporal) như: **TIMESTAMP, TIME hoặc INTERVAL**. Nếu nguồn có giá trị là **DATE**, hàm sẽ tự chuyển thành nguồn thành **TIMESTAMP**.

Để trích xuất giá trị năm từ một giá trị **TIMESTAMP**, bạn chuyển 'year' ở đối số trường:
```sql
    SELECT DATE_PART('year',TIMESTAMP '2017-01-01');
    DATE_PART 2017
```
Để trích xuất giờ, phút, giây từ giá trị **TIMESTAMP**, bạn chuyển giá trị giờ, phút và giây tương ứng cho hàm **DATE_PART()**:
```sql
    SELECT DATE_PART('hour',TIMESTAMP '2017-03-18 10:20:30') h;
    SELECT DATE_PART('minute',TIMESTAMP '2017-03-18 10:20:30') m;
    SELECT DATE_PART('second',TIMESTAMP '2017-03-18 10:20:30') s;
```
Kết quả đầu ra sẽ là:
|h |m | s |
|--|--|---|
|10|20| 30|

Để trích xuất ngày trong tuần (dow- day of week) và hoặc ngày trong năm (doy - day of year) từ giá trị **TIMESTAMP**, bạn sử dụng các câu lệnh sau:
```sql
    SELECT DATE_PART('dow',TIMESTAMP '2017-03-18 10:20:30') dow;
    SELECT DATE_PART('doy',TIMESTAMP '2017-03-18 10:20:30') doy;
```
Kết quả đầu ra sẽ là:

|dow|doy|
|---|---|
| 6 |77 |

## 3.7. DATE_TRUNC Function
Hàm **DATE_TRUNC** cắt ngắn một giá trị **TIMESTAMP** hoặc **INTERVAL** dựa trên một phần ngày được chỉ định, ví dụ: giờ, tuần hoặc tháng và trả về **TIMESTAMP** bị cắt hoặc **INTERVAL**.

Sau đây minh họa cú pháp của hàm **DATE_TRUNC**:
```sql
    DATE_TRUNC('datepart', trường)
```
Đối số *datepart* là mức độ chính xác được sử dụng để cắt ngắn trường.

Đối số trường có kiểu dữ liệu là **TIMESTAMP** hoặc **INTERVAL**, là đầu vào để cắt bớt. Đối số này cũng có thể là một biểu thức trả về giá trị có kiểu dữ liệu là **TIMESTAMP** hoặc **INTERVAL**. Hàm **DATE_TRUNC** trả về giá trị **TIMESTAMP** hoặc **INTERVAL**.

Ví dụ sau đây cắt một giá trị **TIMESTAMP** và trả về kết quả với độ chính xác đến giờ.
```sql
    SELECT DATE_TRUNC('hour', TIMESTAMP '2017-03-17 02:09:30'); 
    --Kết quả trả về: 2017-03-17 02:00:00
```
Nếu bạn muốn cắt ngắn giá trị **TIMESTAMP** đến phần phút, bạn chuyển chuỗi *minute* thành đối số đầu tiên thay cho *hour*:
```sql
    SELECT DATE_TRUNC('minute', TIMESTAMP '2017-03-17 02:09:30');
    --Kết quả trả về: 2017-03-17 02:09:00
```

# 4. Các mệnh đề SET

## 4.1. Union Operator
Toán tử **UNION** kết hợp các tập kết quả của hai hoặc nhiều câu lệnh **SELECT** thành một tập kết quả duy nhất. Sau đây minh họa cú pháp của toán tử **UNION** kết hợp các tập kết quả từ hai truy vấn:
```sql
    SELECT cột_1, cột_2 FROM tên_bảng_1
    UNION
    SELECT cột_1, cột_2 FROM tên_bảng_2;
```
Quy tắc được áp dụng cho các truy vấn **UNION** như sau:

- Cả hai truy vấn phải trả về cùng số lượng cột.
- Các cột tương ứng trong các truy vấn phải có kiểu dữ liệu tương thích.

Toán tử **UNION** loại bỏ tất cả các hàng trùng lặp trừ khi bạn sử dụng **UNION ALL**. Chúng ta thường sử dụng toán tử **UNION** để kết hợp dữ liệu từ các bảng tương tự nhau.

Hãy cùng xem các bảng sau:

- sales2007q1: lưu trữ dữ liệu bán hàng trong Q1 2007.
- sales2007q2: lưu trữ dữ liệu bán hàng trong quý 2 năm 2007.

*sales2007q1*:
```
name    amount
--------------------
Mike    150000.25
Jon     132000.75
Mary    100000.00
```
*sales2007q2*:
```
name    amount
-------------------
Mike    120000.25
Jon     142000.75
Mary    100000.00
```
Chúng ta sử dụng toán tử **UNION** để kết hợp dữ liệu từ cả hai bảng như sau:
```sql
    SELECT * FROM sales2007q1
    UNION
    SELECT * FROM sales2007q2;
```
Truy vấn trả về kết quả sau:
```
name    amount
-------------------
Jon     132000.75
Jon     142000.75
Mary    100000.00
Mike    120000.25
Mike    150000.25
```

**UNION** cũng có thể được sử dụng để xác định tất cả các lần xuất hiện của một trường trên nhiều bảng. Ngoài ra, nếu chúng ta **UNION** hai cột có tên khác nhau, bảng kết quả sẽ trả về tên cột của bảng đầu tiên ta thực hiện **UNION**.

## 4.2. Union All Operator
Bạn sẽ gặp phải một số trường hợp là có một số bản ghi bị xóa sau khi sử dụng toán tử **UNION** bởi vì có giá trị trùng lặp. Nếu bạn không muốn điều đó xảy ra, hãy sử dụng toán tử **UNION ALL** để có được tất cả các bản ghi bao gồm cả bản ghi trùng lặp:
```sql
    SELECT * FROM sales2007q1
    UNION ALL
    SELECT * FROM sales2007q2;
```
```
name    amount
------------------
Mike    150000.25
Jon     132000.75
Mary    100000
Mike    120000.25
Jon     142000.75
Mary    100000
```
Để sắp xếp kết quả được trả về bởi toán tử **UNION/UNION ALL**, hãy sử dụng mệnh đề **ORDER BY** ở cuối cùng truy vấn như câu lệnh sau:
```sql
    SELECT * FROM sales2007q1
    UNION ALL
    SELECT * FROM sales2007q2
    ORDER BY name ASC, amount DESC;
```
```
name    amount
------------------
Jon     142000.75
Jon     132000.75
Mary    100000
Mary    100000
Mike    150000.25
Mike    120000.25
```

Nếu bạn đặt mệnh đề **ORDER BY** ở cuối mỗi câu **SELECT**, tập kết quả sau khi **UNION** sẽ không được sắp xếp như bạn mong đợi. Bởi vì khi toán tử **UNION** kết hợp các tập kết quả được sắp xếp từ mỗi truy vấn, thứ tự của các bản ghi không được đảm bảo.

## 4.3. Except Operator
Toán tử **EXCEPT** trả về các hàng riêng biệt từ truy vấn đầu tiên không nằm trong đầu ra của truy vấn thứ hai. Dưới đây minh họa cú pháp của toán tử **EXCEPT**.
```sql
    SELECT danh_sách_cột FROM A WHERE điều_kiện_a
    EXCEPT 
    SELECT danh_sách_cột FROM B WHERE điều_kiện_b;
```
Để kết hợp các truy vấn bằng toán tử **EXCEPT**, bạn phải tuân theo các quy tắc sau:

- Số lượng cột và thứ tự của chúng phải giống nhau trong cả hai truy vấn.
- Kiểu dữ liệu của các cột tương ứng phải tương thích.

Hãy xem các bảng film và inventory như sau. Câu truy vấn sau sẽ trả về kết quả của dữ liệu trong bảng film:
```sql
SELECT film_id, title FROM film
```
```
film_id     title
--------------------------------
1           Academy Dinosaur
2           Ace Goldfinger
3           Adaptation Holes
4           African Egg
5           Alien Center
```
Truy vấn sau đây trả về các phim trong kho:
```sql
    SELECT DISTINCT inventory.film_id, title 
    FROM inventory 
    INNER JOIN film ON film.film_id = inventory.film_id 
    ORDER BY title;
```
```
film_id     title
------------------------------
1           Academy Dinosaur
3           Adaptation Holes
5           Alien Center
```

Để có được những bộ phim không có trong kho, bạn sử dụng toán tử **EXCEPT** như sau:
```sql
    SELECT film_id, title FROM film
    EXCEPT
    SELECT DISTINCT inventory.film_id, title FROM inventory
    INNER JOIN film ON film.film_id = inventory.film_id
    ORDER BY title;
```
```
film_id     title
----------------------------
2           Ace Goldfinger
4           African Egg
```
Lưu ý rằng mệnh đề **ORDER BY** được đặt ở cuối câu lệnh để sắp xếp các bộ phim theo tiêu đề. Nếu bạn đặt mệnh đề **ORDER BY** trong mỗi truy vấn, kết quả cuối cùng có thể không được sắp xếp vì mỗi truy vấn sẽ sắp xếp kết quả được đặt theo cột tiêu đề và sau đó toán tử **EXCEPT** được áp dụng cho cả hai truy vấn.

## 4.4. Intersect Operator
Giống như toán tử **UNION** và **EXCEPT**, toán tử **INTERSECT** của PostgreSQL kết hợp các tập kết quả của hai hoặc nhiều câu lệnh b thành một tập kết quả duy nhất. Toán tử **INTERSECT** trả về những bản ghi có sẵn trong cả hai tập kết quả hoặc được trả về bởi cả hai truy vấn.

Ví dụ sau đây minh họa cú pháp của toán tử **INTERSECT**:
```sql
    SELECT danh_sách_cột FROM A
    INTERSECT
    SELECT danh_sách_cột FROM B;
```
Để sử dụng toán tử **INTERSECT**, các cột xuất hiện trong các câu lệnh **SELECT** phải tuân theo các quy tắc dưới đây:
- Số lượng cột và thứ tự của chúng trong các mệnh đề SELECT phải giống nhau.
- Các kiểu dữ liệu của các cột phải tương thích.
Hãy xem dữ liệu của ba bảng employees , keys, và hipos.

Bảng *employees*
```
employee_id     employee_name
------------------------------
1               Joyce Edwards
2               Diane Collins
3               Alice Stewart
4               Julie Sanchez
5               Heather Morris
6               Teresa Rogers
7               Doris Reed
8               Gloria Cook
9               Evelyn Morgan
10              Jean Bell
```
Bảng *keys*
```
employee_id     effective_date
--------------------------------
1               2000-02-01
2               2001-06-01
5               2002-01-01
6               2005-06-01
```
Bảng *hipos*
```
employee_id     effective_date
--------------------------------
9               2000-01-01
2               2002-06-01
5               2005-06-01
10              2006-06-01
```
Bảng *employee* lưu trữ dữ liệu chính của nhân viên. Bảng *keys* lưu trữ các nhân viên chủ chốt và bảng *hipos* lưu trữ các nhân viên có tiềm năng cao.

Để có được những nhân viên vừa từ bảng *keys* là những nhân viên có tiềm năng và ở cảng bảng *hipos* - là những nhân viên có tác động cao thì ta thực hiện như sau
```sql
    SELECT employee_id FROM keys
    INTERSECT
    SELECT employee_id FROM hipos;
```
Kết quả đầu ra là

|employee_id|
|-----------|
5
2

Tập kết quả cho thấy nhân viên có id là 2 và 5 là những nhân viên chủ chốt, không chỉ có tiềm năng cao mà còn có độ tác động cao.

Để sắp xếp tập kết quả được trả về bởi toán tử **INTERSECT**, hãy đặt mệnh đề **ORDER BY** ở cuối câu lệnh, không phải ở cuối mỗi câu lệnh **SELECT**.

# 5. Biểu thức điều kiện

## 5.1. Basic CASE Statement
Biểu thức **CASE** giống như câu lệnh **IF/ELSE** trong các ngôn ngữ lập trình khác. PostgreSQL cung cấp hai dạng biểu thức **CASE**.

Dưới đây minh họa hình thức chung của câu lệnh **CASE**:
```sql
CASE 
      WHEN điều_kiện_1 THEN kết_quả_1
      WHEN điều_kiện_2 THEN kết_quả_2
      [WHEN ...]
      [ELSE kết_quả_n]
END
```
Trong dạng chung này, mỗi điều kiện là một biểu thức trả về giá trị boolean, đúng hoặc sai.

- Nếu điều kiện ước tính là đúng, biểu thức **CASE** trả về kết quả tương ứng với điều kiện và tất cả các nhánh **CASE** khác hoàn toàn không xử lý.
- Nếu tất cả các điều kiện đánh giá là sai, biểu thức **CASE** sẽ trả về kết quả trong phần **ELSE**. Nếu bạn bỏ qua mệnh đề **ELSE**, biểu thức **CASE** sẽ trả về **null**.

Lưu ý rằng tất cả các biểu thức kết quả phải có các loại dữ liệu có thể chuyển đổi thành một loại dữ liệu duy nhất. Ví dụ: chuỗi, số và thời gian.

Với dữ liệu của bảng film:
```
film_id     title               rental_rate     rating
--------------------------------------------------------
1           ACADEMY DINOSAUR    0.99            PG
2           ACE GOLDFINGER      4.99            G
3           ADAPTATION HOLES    2.99            NC-17
4           AFFAIR PREJUDICE    2.99            G
5           AFRICAN EGG         2.99            G
6           AGENT TRUMAN        2.99            PG
7           AIRPLANE SIERRA     4.99            PG-13
8           AIRPORT POLLOCK     4.99            R
9           ALABAMA DEVIL       2.99            PG-13
10          ALADDIN CALENDAR    4.99            NC-17
```

Giả sử bạn muốn chỉ định phân khúc giá cho phim với logic sau:

- "Mass" nếu giá cho thuê là 0,99
- "Economic" nếu giá cho thuê là 1,99
- "Luxury" nếu giá cho thuê là 4,99
Và bạn muốn biết số lượng phim thuộc về phân khúc. Trong trường hợp này, bạn có thể sử dụng biểu thức CASE để xây dựng truy vấn như sau:
```sql
SELECT
   SUM ( CASE WHEN rental_rate = 0.99 THEN 1 ELSE 0 END ) AS "Mass",
   SUM ( CASE WHEN rental_rate = 2.99 THEN 1 ELSE 0 END ) AS "Economic",
   SUM ( CASE WHEN rental_rate = 4.99 THEN 1 ELSE 0 END ) AS "Luxury"
FROM film;
```
Kết quả đầu ra sẽ là:
```
Mass    Economic    Luxury
--------------------------
1       5           4
```
Trong truy vấn này, chúng ta đã sử dụng biểu thức **CASE** để trả về 1 hoặc 0 nếu giá cho thuê rơi vào từng phạm vi giá. Và đã áp dụng hàm **SUM** để tính tổng số phim cho từng phân khúc giá.

### Biểu thức CASE đơn giản của PostgreSQL
PostgreSQL cung cấp một dạng khác của biểu thức **CASE** được gọi là dạng đơn giản như sau:
```sql
CASE biểu_thức
    WHEN giá_trị_1 THEN kết_quả_1
    WHEN giá_trị_2 THEN kết_quả_2
    [WHEN ...]
ELSE kết_quả_n
END;
```
Trước tiên, **CASE** đánh giá biểu thức và sau đó so sánh kết quả với từng giá trị* (giá_trị_1 , giá_trị_2 , khác)* trong mệnh đề **WHEN** liên tục cho đến khi tìm thấy kết quả khớp. Khi kết quả của biểu thức bằng với một giá trị trong mệnh đề **WHEN**, **CASE** trả về kết quả tương ứng trong mệnh đề **THEN**.

Nếu **CASE** không tìm thấy bất kỳ kết quả khớp nào, nó sẽ trả về kết_quả_n trong phần **ELSE** hoặc giá trị **NULL** nếu phần **ELSE** không có sẵn. Điều này tương tự như câu lệnh switch trong các ngôn ngữ lập trình khác như C/C ++ và Java.

### Note 
- Trong R hoặc Python, bạn có khả năng tính toán **SUM** các giá trị logic (nghĩa là **TRUE**/**FALSE**) trực tiếp. Trong SQL, bạn phải chuyển đổi các giá trị này thành 1 và 0 trước khi tính tổng. Điều này có thể được thực hiện bằng cách sử dụng một câu lệnh **CASE**.

- Các câu lệnh **CASE** sẽ trả về bất kỳ giá trị nào bạn chỉ định trong mệnh đề **THEN**. Đây là một công cụ cực kỳ mạnh mẽ để tính toán và thao tác dữ liệu khi được sử dụng cùng với một câu lệnh tổng hợp. Nhiệm vụ chính bạn có thể thực hiện là sử dụng **CASE** bên trong hàm **AVG** để tính phần trăm thông tin trong cơ sở dữ liệu của bạn. Đây là một ví dụ về cách bạn thực hiện nó:
```sql
    AVG(CASE WHEN condition_is_met THEN 1
            WHEN condition_is_not_met THEN 0 END)
```
Với phương pháp này, điều quan trọng là chỉ định chính xác bản ghi nào được tính là 0, nếu không, tính toán của bạn có thể không chính xác!

# 6. Truy vấn con

## 6.1. Building on subqueries
Truy vấn con cơ bản trong **WHERE** sẽ chỉ thực thi một lần trong toàn bộ câu lệnh; nó sẽ hữu ích trong khi bạn cần lọc những kết quả dựa trên thông tin mà bạn cần phải tính toán trước.
Lấy ví dụ là bạn cần tạo một danh sách các trận đấu có số bàn thắng của đội nhà cao hơn số bàn thắng trung bình của các trận đấu. Bạn có thể tính toán số trung bình trước, rồi đưa số trung bình đấy vào truy vấn tìm trận đấu ở mệnh đề **WHERE** như ví dụ dưới đây.
```sql
    SELECT AVG(home_goal) FROM matches --Kết quả là: 3.0000000000000000;
    SELECT date, home_id, away_id, home_goal, away_goal
    FROM matches
    WHERE home_goal > 3.0000000000000000
```
Hoặc bạn có thể đặt truy vấn tìm số trung bình vào trong mệnh đề **WHERE**, bên trong dấu ngoặc đơn như sau:
```sql
    SELECT date, home_id, away_id, home_goal, away_goal
    FROM matches
    WHERE home_goal > (SELECT AVG(home_goal) FROM matches)
```

Nhưng nếu bạn muốn trả về một tập hợp kết quả phức tạp hơn thì sao? Các truy vấn con trong câu lệnh **FROM** là một công cụ mạnh mẽ để tái cấu trúc và chuyển đổi dữ liệu của bạn.

Giả sử bạn quan tâm đến việc lấy được thông tin của TOP 2 đội có số lượng bàn thắng sân nhà cao nhất và trên trung bình. Thì trước tiên điều bạn cần là tính trung bình số bàn thắng cho mỗi đội trong giải đấu và sau đó tìm ra giá trị tối đa cho các đội. Điều này có thể dễ dàng thực hiện với truy vấn con trong **FROM**.

Đầu tiên, bạn sẽ tạo truy vấn sẽ trở thành truy vấn con của bạn. Truy vấn này chọn *team_long_name* và **AVG** của cột *home_goal* từ bảng *matches*.

Với dữ liệu của bảng matches như sau:
```
id   date       home_id     away_id     home_goal   away_goal
---------------------------------------------------------------
1    7/29/2011  1           2           2           0
2    7/30/2011  3           1           3           3
3    7/30/2011  2           1           1           4
4    7/30/2011  2           3           5           6
5    7/30/2011  1           3           4           1
6    7/30/2011  1           2           1           1
```
Và bảng teams:
```
team_id    team_long_name     team_short_name
----------------------------------------------
1          KRC Genk           GEN
2          Beerschot AC       BAC
3          SV Zulte-Waregem   ZUL
```
```sql
    SELECT t.team_long_name AS team, AVG(m.home_goal) AS home_avg
    FROM matches AS m
    LEFT JOIN teams AS t ON m.home_id = t.team_id
    GROUP BY team;
```
Bảng team **LEFT JOIN** với bảng *matches* dùng cột *hometeam_id*,điều này sẽ giúp bạn xác định đội chủ nhà. Câu truy vấn cũng sẽ được nhóm lại theo cột team. Và kết quả sẽ trông như thế này: giá trị trung bình sẽ được tính cho mỗi team trong bảng:

Kết quả trả về sẽ là:
```
team                home_avg
----------------------------------------
Beerschot AC        3.0000000000000000
KRC Genk            2.3333333333333333
SV Zulte-Waregem    3.0000000000000000
```

Để chỉ nhận được TOP 2 các đội bóng làm kết quả cuối cùng, hãy đặt truy vấn toàn bộ truy vấn vào bên trong mệnh đề **FROM** của truy vấn chính và đảm bảo đặt cho nó một **ALIAS** như sau:
```sql
    SELECT team, home_avg
    FROM(
        SELECT t.team_long_name AS team, AVG(m.home_goal) AS home_avg
        FROM matches AS m
    LEFT JOIN teams AS t ON m.home_id = t.team_id
    GROUP BY team) AS subquery

    ORDER BY home_avg DESC
    LIMIT 2;
```
Kết quả trả về như sau:
```
team                home_avg
-----------------------------------------
Beerschot AC        3.0000000000000000
SV Zulte-Waregem    3.0000000000000000
```

Có một vài điều quan trọng cần nhớ khi sử dụng các truy vấn con trong mệnh đề **FROM**:
- Đầu tiên, là bạn có khả năng tạo nhiều hơn một truy vấn con trong câu lệnh **FROM** của bất kỳ truy vấn chính nào. Khi bạn làm như vậy, hãy đảm bảo rằng bạn cung cấp cho mỗi truy vấn con một **ALIAS** và đảm bảo rằng bạn có thể **JOIN** chúng với nhau, giống như bạn sẽ khi truy vấn một bảng từ cơ sở dữ liệu của bạn.
- Thứ hai, bạn có thể **JOIN** bất cứ truy vấn con vào bất kỳ bảng hiện có nào trong cơ sở dữ liệu của bạn. Tuy nhiên, bạn cần đảm bảo rằng bạn có một cột trong truy vấn con mà bạn có thể sử dụng với **JOIN**.


Đến nay, chúng ta đã cùng nhau đề cập đến cách sử dụng các truy vấn con trong các mệnh đề **FROM** và **WHERE**. Các truy vấn con cũng có thể được gọi trong mệnh đề **SELECT** để trả về giá trị trong một tập dữ liệu. 

Các truy vấn con trong **SELECT** được sử dụng để trả về một giá trị tổng hợp duy nhất. Điều này khá hữu ích bởi vì như chúng ta đã biết, ta không thể sử dụng lệnh tổng hợp một cách trực tiếp trong truy vấn SQL khi câu lệnh chưa được thực hiện nhóm (**GROUP BY**) lại. Trong trường hợp bạn không muốn **GROUP** các cột thì thực hiện truy vấn con trong **SELECT** là một cách để khắc phục điều đó.

Các truy vấn con trong **SELECT** cũng rất hữu ích trong việc giúp bạn thực hiện các phép tính phức tạp. Sử dụng một câu truy vấn con trong **SELECT** khá đơn giản và được thực hiện giống như cách bạn thực hiện các truy vấn con trong mệnh đề **WHERE** và **FROM**.

Với dữ liệu từ bảng *matches* như sau:
```
id    season    home_id     away_id    home_goal   away_goal
---------------------------------------------------------------
1     1         5           4          2           0
2     1         4           5          3           3
3     2         9           5          1           4
4     2         5           4          5           6
5     2         6           5          4           1
```
Giả sử chúng ta muốn tạo một cột để so sánh tổng số trận đấu được chơi mỗi mùa giải (season) với tổng số trận đấu được chơi tất cả các mùa. Trước tiên chúng ta cần tính tổng số trận đấu trong tất cả các mùa:
```sql
    SELECT COUNT(id) FROM matches;
    -- Kết quả trả về sẽ là 5
```

Sau đó, chúng ta sẽ đưa kết quả đã lấy ở trên vào phần mệnh đề SELECT như sau:
```sql
    SELECT
        season,
        COUNT(id) AS no_matches,
        5 AS total_matches
    FROM matches
    GROUP BY season;
```
Hoặc, chúng ta có thể thêm truy vấn con trực tiếp vào câu lệnh **SELECT** để có kết quả giống hệt nhau.
```sql
SELECT
    season,
    COUNT(id) AS matches,
    (SELECT COUNT(id) FROM matches) AS total_matches
FROM matches
GROUP BY season;
```
Kết quả trả về sẽ là:
```
season  no_matches  total_matches
-----------------------------------
1       2           5
2       3           5
```
Có một vài cân nhắc khi làm việc với các truy vấn con trong mệnh đề **SELECT**.

- Đầu tiên là truy vấn con trong mệnh đề **SELECT** cần trả về một giá trị duy nhất. Nếu kết quả truy vấn con của bạn trả về nhiều hàng, toàn bộ truy vấn của bạn sẽ phát sinh lỗi.
- Điều thứ hai cần chú ý là vị trí của các bộ lọc dữ liệu của bạn trong cả truy vấn chính và truy vấn phụ.

## 6.2. Correlated subqueries
Truy vấn con tương quan là một loại truy vấn con đặc biệt, sử dụng các giá trị từ truy vấn bên ngoài để tạo kết quả cuối cùng. Truy vấn con được thực hiện lại mỗi khi một hàng mới trong tập dữ liệu cuối được trả về, để tạo đúng từng thông tin mới.

Các truy vấn con tương quan được sử dụng cho các loại tính toán đặc biệt, chẳng hạn như **JOIN**, lọc và đánh giá dữ liệu trong cơ sở dữ liệu.

Đối với dữ liệu của các bảng sau:

countries
```
id    name
--------------
1     Belgium
2     England
3     France
```
matches
```
id   country_id   date          home_id    away_id    home_goal    away_goal
------------------------------------------------------------------------------
1    1            2011-07-29    1          2          2            0
2    2            2011-07-30    3          1          3            3
3    2            2011-07-30    2          1          1            4
4    3            2011-07-30    2          3          5            6
5    3            2011-07-30    1          3          4            1
6    1            2011-07-30    1          2          1            1
```
Hãy trả lời câu hỏi **"Số bàn thắng trung bình được ghi ở mỗi quốc gia trong tất cả các mùa giải là bao nhiêu?"**

Để trả lời cho câu hỏi trên, đơn giản là bạn chỉ cần **JOIN** hai bảng *matches* và bảng *countries*, lấy trung bình các bàn thắng được ghi và nhóm toàn bộ truy vấn theo tên quốc gia, mang lại một hàng với giá trị trung bình cho mỗi quốc gia.
```sql
SELECT 
    c.name AS country,
    AVG(m.home_goal + m.away_goal) AS avg_goals
FROM countries AS c
    LEFT JOIN matches AS m ON c.id = m.country_id 
GROUP BY country 
ORDER BY avg_goals;
```
Kết quả trả về sẽ là:
```
country    avg_goals
-------------------------------
France     8.0000000000000000
England    5.5000000000000000
Belgium    2.0000000000000000
```
Thay vì **JOIN**, bạn có thể sử dụng một truy vấn con tương quan như sau:
```sql
SELECT
    c.name AS country,
    (SELECT AVG(home_goal + away_goal) 
     FROM matches AS m 
     WHERE m.country_id = c.id) AS avg_goals 
FROM countries AS c 
ORDER BY avg_goals DESC;
```
Kết quả trả về sẽ là:
```
country    avg_goals
--------------------------------
France     8.0000000000000000
England    5.5000000000000000
Belgium    2.0000000000000000
```
Bạn có thể nhận thấy rằng, ở mệnh đề **WHERE** yêu cầu SQL trả về một giá trị cho câu truy vấn con cột *country_id* của bảng *matches*, khớp bằng cột *c.id* trong câu truy vấn bên ngoài của bảng *countries*. Bằng cách này, toàn bộ **JOIN** được thay thế và kết quả giống hệt nhau.

Một số khác biệt giữa các truy vấn con cơ bản và truy vấn con tương quan:

|Truy vấn con cơ bản    |Truy vấn phụ tương quan|
|-----------------------|-----------------------|
|Các truy vấn con cơ bản có thể được sử dụng để trích xuất, tái cấu trúc hoặc lọc thông tin và có thể chạy độc lập với truy vấn chính.|Một truy vấn con tương quan không thể tự thực hiện được vì nó phụ thuộc vào các giá trị trong truy vấn chính.|
|Một truy vấn con cơ bản sẽ chỉ thực thi một lần trong toàn bộ câu lệnh.|Một truy vấn con tương quan được thực thi theo các vòng lặp - một lần cho mỗi hàng được tạo bởi tập dữ liệu. Điều này có nghĩa là việc thêm các truy vấn con tương quan sẽ làm giảm hiệu suất truy vấn của bạn, bởi vì truy vấn của bạn bị lặp đi lặp lại.|

Hãy cẩn thận không bao gồm quá nhiều truy vấn con tương quan trong câu truy vấn của bạn, hoặc câu truy vấn của bạn có thể mất nhiều thời gian để chạy.

Các truy vấn con lồng nhau có chức năng chính xác như tên gọi của chúng - đó là các truy vấn được lồng bên trong các truy vấn con khác. Như ở các chương trước, thông tin trong cơ sở dữ liệu thường không được định dạng đúng ngay từ đầu, hay không được định dạng phù hợp với mục đích của bạn, vì thế cần phải có nhiều lần chuyển đổi và lọc dữ liệu trước khi bạn sử dụng ở truy vấn chính. Đó là lí do mà bạn thực hiện truy vấn con lồng nhau.

Điều quan trọng cũng cần lưu ý là các truy vấn lồng nhau có thể tương quan hoặc không tương quan. Cũng có thể là sự kết hợp của hai - truy vấn con bên trong có thể tương quan, bên ngoài không tương quan hoặc ngược lại. Và mỗi truy vấn con tương quan có thể tham chiếu thông tin từ truy vấn con bên ngoài hoặc truy vấn chính. Việc đấy hoàn toàn phụ thuộc vào vấn đề bạn đang tìm cách giải quyết.

Đối với dữ liệu của các bảng sau:

countries
```
id   name
--------------
1    Belgium
2    England
3    France
```
matches
```
id   country_id     country_id   date          home_id    away_id    home_goal    away_goal
------------------------------------------------------------------------------
1    1              2011/2012    2011-07-29    1          2          2            0
2    2              2011/2012    2011-07-30    3          1          3            3
3    2              2011/2012    2011-07-30    2          1          1            4
4    3              2011/2012    2011-07-30    2          3          5            6
5    3              2012/2013    2011-07-30    1          3          4            1
6    1              2012/2013    2011-07-30    1          2          1            1
```
Hãy xem xét ví dụ sau. Bạn muốn trả lời một câu hỏi: **"Số bàn thắng trung bình của mỗi quốc gia được ghi trong một trận đấu trong mùa 2011/2012 là bao nhiêu?"**
```sql
SELECT
    c.name AS country,
    (SELECT AVG(home_goal + away_goal)
        FROM matches AS m 
        WHERE m.country_id = c.id 
            AND id IN 
                (SELECT id FROM matches WHERE season = '2011/2012')) AS avg_goals 
FROM country AS c;
```
Đầu ra sẽ là:
```
country    avg_goals
-------------------------------
Belgium    2.0000000000000000
England    5.5000000000000000
France     11.0000000000000000
```
Cách giải quyết này khá giống với trước, ngoại trừ việc bạn phải bổ sung thêm một bước tạo truy vấn con thứ hai, lồng nhau bên trong câu lệnh **SELECT** và truy vấn con bên ngoài có một câu lệnh tương quan với truy vấn chính.

# 7. Biểu thức bảng chung

## 7.1. CTE syntax
Biểu thức bảng chung là tập kết quả tạm thời mà bạn có thể tham chiếu trong một câu lệnh SQL khác bao gồm **SELECT, INSERT, UPDATE** hoặc **DELETE**... Nói là biểu thức tạm thời bởi vì chúng chỉ tồn tại trong khi thực hiện truy vấn.

Phần sau đây cho thấy cú pháp tạo **CTE**:
```sql
    WITH cte_name (column_list) AS (
        CTE_query_definition 
    )
    câu lệnh;
```

Trong cú pháp này:
- Trước tiên, chỉ định tên của **CTE** theo danh sách cột tùy chọn.
- Thứ hai, bên trong phần thân của mệnh đề **WITH**, chỉ định truy vấn trả về tập kết quả. Nếu bạn không chỉ định rõ ràng danh sách cột sau tên **CTE**, danh sách những cột được chọn ở *CTE_query_definition* sẽ trở thành danh sách cột của **CTE**.
- Thứ ba, sử dụng **CTE** như bảng hoặc dạng xem trong câu lệnh có thể là **SELECT, INSERT, UPDATE, hoặc DELETE.**
- Biểu thức bảng chung hoặc **CTE** thường được sử dụng để đơn giản hóa các phép nối và truy vấn con phức tạp trong PostgreSQL.

Hãy lấy một số ví dụ về việc sử dụng **CTE** để hiểu rõ hơn. Chúng tôi sẽ sử dụng các bảng *film* và *rental*. 
Xem ví dụ sau:
```sql
    WITH cte_film AS (
        SELECT film_id, title,
            (CASE WHEN length < 30 THEN 'Short'
                WHEN length < 90 THEN 'Medium'
                ELSE 'Long'
            END) length    
        FROM film
    )
    SELECT film_id, title, length FROM cte_film 
    WHERE length = 'Long' 
    ORDER BY  title; 
```
Với dữ liệu của bảng film như sau:
```
film_id     title               rental_duration     rental_rate    length    replacement_cost    rating
---------------------------------------------------------------------------------------------------------
1           ACADEMY DINOSAUR    6                   0.99            86          20.99            PG
2           ACE GOLDFINGER      3                   4.99            48          12.99            G
3           ADAPTATION HOLES    7                   2.99            50          18.99            NC-17
4           AFFAIR PREJUDICE    5                   2.99            117         26.99            G
5           AFRICAN EGG         6                   2.99            130         22.99            G
6           AGENT TRUMAN        3                   2.99            169         17.99            PG
7           AIRPLANE SIERRA     6                   4.99            62          28.99            PG-13
8           AIRPORT POLLOCK     6                   4.99            54          15.99            R
9           ALABAMA DEVIL       3                   2.99            114         21.99            PG-13
10          ALADDIN CALENDAR    6                   4.99            63          24.99            NC-17
```
Kết quả trả về sẽ là:
```
film_id     title               length
---------------------------------------
4           AFFAIR PREJUDICE    Long
5           AFRICAN EGG         Long
6           AGENT TRUMAN        Long
9           ALABAMA DEVIL       Long
```

Biểu thức bảng chung có hai phần:
- Phần đầu tiên xác định tên của **CTE** là *cte_film*.
- Phần thứ hai xác định câu lệnh **SELECT** biểu thức với các hàng.
- Sau đó, chúng ta đã sử dụng *cte_film* **CTE** trong câu lệnh **SELECT** để chỉ trả lại các phim có độ dài là *'Long'*.

Biểu thức bảng chung có nhiều lợi ích so với truy vấn con như sau:
- Đầu tiên, **CTE** chỉ chạy một lần và kết quả được lưu trữ trong bộ nhớ, do đó cải thiện được về vấn đề thời gian trong việc chạy truy vấn của bạn.
- Thứ hai, **CTE** là một công cụ tuyệt vời để tổ chức các câu truy vấn dài và phức tạp. Bạn có thể khai báo nhiều **CTE** nếu bạn cần, từng cái một.
- Bạn cũng có thể tham chiếu thông tin trong **CTE** đã khai báo trước đó. Ví dụ: nếu bạn có 3 **CTE** trong một truy vấn, **CTE** thứ ba của bạn có thể truy xuất thông tin từ **CTE** thứ nhất và thứ hai.
- Cuối cùng, **CTE** có thể tự tham chiếu trong một loại bảng đặc biệt gọi là **CTE đệ quy**. Chúng ta sẽ cùng đề cập đến **CTE đệ quy** sau.

## 7.2. Recursive CTE
Truy vấn đệ quy là truy vấn đề cập đến **CTE đệ quy**. Các truy vấn đệ quy rất hữu ích trong nhiều tình huống như truy vấn dữ liệu phân cấp như cấu trúc tổ chức, hóa đơn tài liệu, v.v.

Sau đây minh họa cú pháp của **CTE đệ quy**:
```sql
    WITH RECURSIVE cte_name AS(
        CTE_query_definition -- non-recursive term
        UNION [ALL]
        CTE_query_definition -- recursive term
    ) SELECT * FROM cte_name;
```
Dạng thông thường của một query đệ quy **WITH** luôn bắt đầu bằng một mệnh đề không đệ quy (non-recursive) tiếp sau đó là phép toán **UNION** (hoặc **UNION ALL**), mệnh đề đệ quy - lưu trữ và truy vấn tới các kết quả sinh ra từ phép toán.

Đánh giá recursive query
- Thực hiện đánh giá mệnh đề non-recursive, phép toán **UNION** (không phải **UNION ALL**) loại trừ các row bị trùng lặp, tất cả các row còn lại trong kết quả của query đệ quy sẽ được lưu trong một bảng tạm (temporary working table)
- Sau khi nạp dữ liệu cho bảng tạm, lặp lại các bước sau: 
    - a. Đánh giá biểu thức đệ quy, thay thế nội dung hiện tại của bảng hiện hành bằng các bản ghi theo dạng đệ quy tự tham chiếu (self-reference). Đối với phép **UNION** (không phải **UNION ALL**) loại bỏ các row trùng lặp (so với tất cả các bản ghi đang tồn tại) các row còn lại trong kết quả truy vấn đệ quy sẽ được cập nhật lại trong bảng trung gian tạm thời. 
    - b. Thay thế nội dung của bảng hiện hành bằng bảng tạm thời trung gian, giải phóng dữ liệu ở bảng trung gian.

Với dữ liệu từ bảng employee:
```
employee_id     full_name           manager_id
-------------------------------------------------
1               Heinz Griesser      0
2               Andreas Sitter      1
3               Thomas Bergmann     1
4               Hannes Berg         2
5               Anna Kruggel        4
6               Karin Pacher        5
7               Patrick Wurzer      1
8               Micheal Maier       7
9               David Fanzott       4
10              Andrea Sternig      1
```
Truy vấn sau đây trả về tất cả các cấp dưới của người quản lí có *manager_id* là 2.
```sql
    WITH RECURSIVE subordinates AS (
        SELECT employee_id, manager_id, full_name
        FROM employees
        WHERE employee_id = 2
        UNION
        SELECT e.employee_id, e.manager_id, e.full_name
        FROM employees e
        INNER JOIN subordinates s ON s.employee_id = e.manager_id
    ) 
    SELECT * FROM subordinates;
```
Bảng trả về sẽ là:
```
employee_id     manager_id      full_name
-----------------------------------------------
2               1               Andreas Sitter
4               2               Hannes Berg
5               4               Anna Kruggel
9               4               David Fanzott
6               5               Karin Pacher
```
Hãy cùng tìm hiểu cách nó hoạt động như sau:
- Câu CTE đệ quy có tên là subordinates (cấp dưới) đã định nghĩa là hai thuật ngữ - một là thuật ngữ đệ quy và một là thuật ngữ không đệ quy.
- Thuật ngữ không đệ quy trả về tập kết quả cơ sở R0 gồm có nhân viên có với id là 2 như sau.
```
employee_id  manager_id   full_name
-----------------------------------------
2            1            Andreas Sitter
```
Thuật ngữ đệ quy trả về (các) cấp dưới trực tiếp của nhân viên có id là 2. Đây là kết quả của việc **JOIN** giữa bảng *employees* và **CTE** *subordinates*. Lần đệ quy đầu tiên sẽ trả về tập kết quả sau:
```
employee_id    manager_id    full_name
--------------------------------------------
4              2             Hannes Berg
```
PostgreSQL thực hiện đệ quy nhiều lần. Tại lần đệ quy thứ hai của thuật ngữ đệ quy, kết quả đầu ra được trả về như sau:
```
employee_id     manager_id      full_name
-----------------------------------------------
5               4               Anna Kruggel
9               4               David Fanzott
6               5               Karin Pacher
```


# 8. Các hàm windown

## 8.1. Windown vs. GROUP BY

Các hàm **windown** thực hiện một hoạt động nào đó trên một tập hợp các hàng có liên quan đến hàng hiện tại.
Chúng tương tự như các hàm tổng hợp **GROUP BY** ở chỗ chúng trải dài trên nhiều hàng. Nhưng thay vì các hàng được nhóm lại thành một như ở **GROUP BY** thì tất cả các hàng ở hàm **windown** vẫn xuất hiện ở đầu ra.
PostgreSQL có một cú pháp riêng cho lệnh gọi các hàm **windown** như sau:
```sql
hàm_windown(arg1, arg2,..) OVER (
   [PARTITION BY biểu_thức_phân_vùng]
   [ORDER BY biểu_thức_sắp_xếp [ASC | DESC] [NULLS {FIRST | LAST }]]
)
```
Trong cú pháp này:
`hàm_windown(arg1, arg2, ...)` 
*hàm_windown* là tên của hàm **windown**. Một số hàm **windown** không có đối số.

**ORDER BY** và **PARTITION BY** là hai mệnh đề con phổ biến nhất được sử dụng trong các hàm windown.

### Mệnh đề **PARTITION BY** 

Mệnh đề **PARTITION BY** chia các hàng thành nhiều nhóm hoặc phân vùng mà hàm **windown** được áp dụng. Mệnh đề **PARTITION BY** là tùy chọn. Nếu bạn bỏ qua mệnh đề **PARTITION BY**, hàm **windown** sẽ coi toàn bộ tập kết quả là một phân vùng duy nhất.

## 8.2. Row-number Function
Hàm **ROW_NUMBER** là một hàm **windown** gán một số nguyên liên tiếp cho mỗi hàng trong tập kết quả. Dưới đây minh họa cú pháp của hàm **ROW_NUMBER**:
```sql
    ROW_NUMBER() OVER(
        [PARTITION BY column_1, column_2,…]
        [ORDER BY column_3,column_4,…]
    )
```
Tập hợp các hàng mà hàm **ROW_NUMBER** hoạt động được gọi là **windown**.

Mệnh đề **PARTITION BY** chia các **windown** thành các tập hoặc phân vùng nhỏ hơn. Nếu bạn chỉ định mệnh đề **PARTITION BY**, số hàng ở mỗi phân vùng bắt đầu bằng một. Bởi vì mệnh đề **PARTITION BY** là tùy chọn cho hàm **ROW_NUMBER**, do đó bạn có thể bỏ qua nó. Lúc này, hàm **ROW_NUMBER** sẽ coi toàn bộ các **windown** nằm trong một phân vùng.

Mệnh đề **ORDER BY** bên trong mệnh đề **OVER** xác định thứ tự sắp xếp của các cột được gán.

Chúng ta sẽ sử dụng bảng products để kiểm tra chức năng của hàm **ROW_NUMBER** thông qua câu lệnh như sau:
```sql
    SELECT
    ROW_NUMBER() OVER() AS row_number,
    product_id, product_name,  
FROM products;
```
Với dữ liệu của bảng products như sau:
```
product_id    product_name
-----------------------------
8             Dell Vostro
5             HP Elite
2             HTC One
9             iPad
4             iPhone
```
Đầu ra sẽ là:
```
row_number    product_id    product_name
--------------------------------------------
1             8             Dell Vostro
2             5             HP Elite
3             2             HTC One
4             9             iPad
5             4             iPhone
```

## 8.3. Lag Function
Hàm **LAG** giúp bạn truy cập vào một hàng ở trước hàng hiện tại. Nói cách khác, từ hàng hiện tại, hàm **LAG** có thể truy cập dữ liệu của hàng trước. Hàm **LAG** sẽ rất hữu ích để so sánh các giá trị của hàng hiện tại và hàng trước.

Sau đây là mô tả cú pháp của hàm **LAG**:
```sql
    LAG(expression [,offset [,default_value]]) 
    OVER (
        [PARTITION BY partition_expression, ... ]
        ORDER BY sort_expression [ASC | DESC], ...
    )
```
Dưới đây là dữ liệu từ bảng sales:
```
year    group_id    amount
----------------------------
2018    1           1474.00
2018    2           1787.00
2018    3           1760.00
2018    3           1760.00
2019    1           1915.00
2019    2           1911.00
2019    3           1118.00
2020    1           1646.00
2020    2           1975.00
2020    3           1516.00
2020    4           1716.00
```

Ví dụ này sử dụng hàm **LAG** để trả về số tiền bán hàng của năm hiện tại và năm trước:
```sql
WITH cte AS (
    SELECT year, SUM(amount) amount
    FROM sales 
    GROUP BY year
    ORDER BY year
) 
SELECT 
    year, amount, 
    LAG(amount,1) OVER (ORDER BY year) previous_year_sales
FROM cte;
```
Kết quả trả về sẽ là:
```
year    amount     previous_year_sales
--------------------------------------
2018    6781.00    null
2019    4944.00    6781.00
2020    6853.00    4944.00
```

## 8.4. PARTITION BY
Ví dụ này sử dụng hàm **LAG** để so sánh doanh số của năm hiện tại với doanh số của năm trước của từng nhóm sản phẩm:
```sql
    SELECT  
        year, amount, group_id,
        LAG(amount,1) OVER ( PARTITION BY group_id ORDER BY year) previous_year_sales
    FROM sales;
```
Với dữ liệu của bảng sales như sau
```
year    group_id    amount
---------------------------------
2018    1           1474.00
2018    2           1787.00
2018    3           1760.00
2018    3           1760.00
2019    1           1915.00
2019    2           1911.00
2019    3           1118.00
2020    1           1646.00
2020    2           1975.00
2020    3           1516.00
2020    4           1716.00
```
Kết quả đầu ra sẽ là:
```
year    amount     group_id     previous_year_sales
----------------------------------------------------
2018    1474.00    1            null
2019    1915.00    1            1474.00
2020    1646.00    1            1915.00
2018    1787.00    2            null
2019    1911.00    2            1787.00
2020    1975.00    2            1911.00
2018    1760.00    3            null
2018    1760.00    3            1760.00
2019    1118.00    3            1760.00
2020    1516.00    3            1118.00
2020    1716.00    4            null
```
Trong ví dụ này:

- Mệnh đề **PARTITION BY** phân phối các hàng thành các nhóm sản phẩm (hoặc phân vùng) được chỉ định bởi group_id.
- Mệnh đề **ORDER BY** sắp xếp các hàng trong mỗi nhóm sản phẩm theo năm theo thứ tự tăng dần.
- Hàm **LAG** được áp dụng cho từng phân vùng để trả lại doanh số của năm trước.

## 8.5. Lead Function
Hàm **LEAD** cung cấp quyền truy cập vào một hàng theo hàng hiện tại ở mức bù vật lý đã chỉ định. Điều đó có nghĩa là từ hàng hiện tại, hàm **LEAD** có thể truy cập dữ liệu của hàng tiếp theo, hàng sau hàng tiếp theo, v.v. Hàm **LEAD** rất hữu ích để so sánh giá trị của hàng hiện tại với giá trị của hàng theo sau hàng hiện tại.

Dưới đây minh họa cú pháp của hàm **LEAD**:
```sql
    LEAD(biểu_thức[, phần_bù[, giá_trị_mặc_định]]) 
    OVER (
    [PARTITION BY biểu_thức_phân_vùng, ... ]
    ORDER BY biểu_thức_sắp_xếp [ASC | DESC], ...
    )
```
- *biểu_thức*: được ước tính theo hàng sau dựa trên phần bù được chỉ định từ hàng hiện tại. biểu_thức có thể là một cột, biểu thức, truy vấn con phải ước tính thành một giá trị duy nhất. Và nó không thể là một hàm **windown**.
- *phần_bù*: là số nguyên dương chỉ định số lượng hàng chuyển tiếp từ hàng hiện tại để truy cập dữ liệu. phần_bù có thể là biểu thức, truy vấn con hoặc cột. Giá trị bù mặc định là 1 nếu bạn không chỉ định nó.
- *giá_trị_mặc_định*: là giá trị trả về nếu phần bù vượt quá phạm vi của phân vùng. Giá trị mặc định là **NULL** nếu bạn bỏ qua nó.

Truy vấn sau đây sử dụng hàm **LEAD** để trả về số tiền bán hàng của năm hiện tại và năm tiếp theo:
```sql
WITH cte AS (
    SELECT year, SUM(amount) amount
    FROM sales
    GROUP BY year
    ORDER BY year
) 
SELECT 
    year, amount, 
    LEAD(amount,1) OVER (ORDER BY year) next_year_sales
FROM cte;
```
Với dữ liệu của bảng sales:
```
year    group_id    amount
-----------------------------
2018    1           1474.00
2018    2           1787.00
2018    3           1760.00
2018    3           1760.00
2019    1           1915.00
2019    2           1911.00
2019    3           1118.00
2020    1           1646.00
2020    2           1975.00
2020    3           1516.00
2020    4           1716.00
```
Kết quả đầu ra sẽ là:
```
year    amount     next_year_sales
-----------------------------------
2018    6781.00    4944.00
2019    4944.00    6853.00
2020    6853.00    null
```

## 8.6. First-value Function
Hàm **FIRST_VALUE** trả về giá trị nằm ở row đầu tiên trong phân vùng của tập kết quả.

Sau đây là cú pháp của hàm **FIRST_VALUE** :
```sql
    FIRST_VALUE(biểu_thức)  
    OVER ( 
        [PARTITION BY biểu_thức_phân_vùng, ... ]
        ORDER BY biểu_thức_sắp_xếp [ASC | DESC], ...
    )
```
Trong cú pháp này:

- *biểu_thức*: có thể là một biểu thức, cột hoặc truy vấn con trả về giá trị của hàng đầu tiên của phân vùng được sắp xếp của tập kết quả. Biểu thức phải trả về một giá trị duy nhất.

- *Mệnh đề **PARTITION BY***: chia các hàng trong một kết quả được đặt thành các phân vùng mà hàm **FIRST_VALUE** được áp dụng. Khi bạn không gọi đến mệnh đề **PARTITION BY**, hàm **FIRST_VALUE** xử lý toàn bộ tập kết quả dưới dạng một phân vùng..

- *Mệnh đề **ORDER BY***: chỉ định thứ tự sắp xếp các hàng trong mỗi phân vùng mà hàm **FIRST_VALUE** được áp dụng.

Câu lệnh sau sử dụng hàm **FIRST_VALUE** để trả về tất cả các sản phẩm và cả sản phẩm có giá thấp nhất:
```sql
    SELECT 
        product_id, product_name, group_id, price, 
        FIRST_VALUE(product_name) OVER(ORDER BY price) lowest_price
    FROM products;
```
Với dữ liệu của bảng products như sau:
```
product_id    product_name          price     group_id
------------------------------------------------------
1             Microsoft Lumia       200.00    1
2             HTC One               400.00    1
3             Nexus                 500.00    1
4             iPhone                900.00    1
5             HP Elite              1200.00   2
6             Lenovo Thinkpad       700.00    2
7             Sony VAIO             700.00    2
8             Dell Vostro           800.00    2
9             iPad                  700.00    3
10            Kindle Fire           150.00    3
11            Samsung Galaxy Tab    200.00    3
```
Đây là tập kết quả:
```
product_id    product_name          group_id    price     lowest_price
-------------------------------------------------------------------------
10            Kindle Fire           3           150.00    Kindle Fire
1             Microsoft Lumia       1           200.00    Kindle Fire
11            Samsung Galaxy Tab    3           200.00    Kindle Fire
2             HTC One               1           400.00    Kindle Fire
3             Nexus                 1           500.00    Kindle Fire
9             iPad                  3           700.00    Kindle Fire
6             Levono Thinkpad       2           700.00    Kindle Fire
7             Sony VAIO             2           700.00    Kindle Fire
8             Dell Vostro           2           800.00    Kindle Fire
4             iPhone                1           900.00    Kindle Fire
5             HP Elite              2           1200.00   Kindle Fire
```
Trong ví dụ này, ta có:

- Vì chúng ta đã bỏ qua mệnh đề **PARTITION BY** trong hàm **FIRST_VALUE**, nên hàm đã xử lý toàn bộ kết quả dưới dạng một phân vùng.
- Mệnh đề **ORDER BY** đã sắp xếp các sản phẩm theo giá từ thấp đến cao.
Hàm **FIRST_VALUE** được áp dụng cho toàn bộ tập kết quả và chọn giá trị trong cột *product_name* của hàng đầu tiên.

## 8.7. Rank Function
Hàm **RANK** gán thứ hạng cho mỗi hàng trong một phân vùng của tập kết quả.

Đối với mỗi phân vùng, thứ hạng của hàng đầu tiên là 1. Hàm **RANK** thêm số lượng hàng bị ràng buộc vào thứ hạng bị ràng buộc để tính thứ hạng của hàng tiếp theo, do đó các cấp bậc có thể không tuần tự. Ngoài ra, các hàng có cùng giá trị sẽ có cùng thứ hạng.

Sau đây minh họa cú pháp của hàm **RANK**:
```sql
    RANK() OVER (
        [PARTITION BY partition_expression, ... ]
        ORDER BY sort_expression [ASC | DESC], ...
    )
```
Trong cú pháp này:

- Đầu tiên, mệnh đề **PARTITION BY** phân phối các hàng của tập kết quả thành các phân vùng mà hàm **RANK** được áp dụng.
- Sau đó, mệnh đề **ORDER BY** chỉ định thứ tự các hàng trong mỗi phân vùng mà hàm được áp dụng

Hàm **RANK** có thể hữu ích để tạo báo cáo theo dạng *top*-N và *bottom*-N.

Với dữ liệu của bảng ranks

|c|
|-|
A
A
B
B
B
C
E
```sql
    SELECT c, RANK () OVER(ORDER BY c) rank_number 
    FROM ranks;
```
Đầu ra như sau
|c|rank_number|
|-|-----------|
|A|1|
|A|1|
|B|3|
|B|3|
|B|3|
|C|6|
|E|7|

Như bạn có thể thấy rõ từ đầu ra:

- Hàng thứ nhất và thứ hai nhận được cùng thứ hạng vì chúng có cùng giá trị A.
- Hàng thứ ba, thứ tư và thứ năm nhận được thứ hạng 3 vì hàm **RANK** bỏ qua thứ hạng 2 và tất cả chúng đều có cùng giá trị B.
## 8.8. Dense_rank Function
**DENSE_RANK** chỉ định thứ hạng cho mỗi hàng trong mỗi phân vùng của tập kết quả. 
Khác với hàm **RANK**, hàm **DENSE_RANK** trả về các giá trị xếp hạng liên tiếp.

Đối với mỗi phân vùng, hàm **DENSE_RANK** trả về cùng một thứ hạng cho các hàng có cùng giá trị.

Phần sau đây hiển thị cú pháp của hàm DENSE_RANK:
```sql
    DENSE_RANK OVER (
    [PARTITION BY biểu_thức_phân_vùng, ... ]
    ORDER BY biểu_thức_sắp_xếp [ASC | DESC], ...
    )
```
Hàm **DENSE_RANK** được áp dụng cho mọi hàng trong mỗi phân vùng được xác định bởi mệnh đề **PARTITION BY**, theo thứ tự sắp xếp được chỉ định bởi mệnh đề **ORDER BY**. Nó sẽ đặt lại thứ hạng khi vượt qua ranh giới phân vùng.

Mệnh đề **PARTITION BY** là tùy chọn. Nếu bạn bỏ qua nó, hàm **DENSE_RANK** sẽ coi toàn bộ tập kết quả là một phân vùng duy nhất. Ví dụ sau chỉ định thứ hạng cho mọi sản phẩm trong mỗi nhóm sản phẩm:
```sql
SELECT
    product_id, product_name, group_id, price,
    DENSE_RANK() OVER ( 
    PARTITION BY group_id
    ORDER BY price DESC
    ) price_rank 
FROM products;
```
```
product_id    product_name          group_id    price
-------------------------------------------------------
8             Dell Vostro           3           150
5             HP Elite              1           200
2             HTC One               3           200
9             iPad                  1           200
4             iPhone                1           145
10            Kindle Fire           3           250
6             Lenovo Thinkpad       2           400
1             Microsoft Lumia       2           500
3             Nexus                 2           700
11            Samsung Galaxy Tab    1           700
7             Sony VAIO             2           700
```
Kết quả đầu ra sẽ là:
```
product_id      product_name        group_id   price   price_rank
---------------------------------------------------------------
11              Samsung Galaxy Tab  1           700    1
5               HP Elite            1           200    2
9               iPad                1           200    2
4               iPhone              1           145    3
3               Nexus               2           700    1
7               Sony VAIO           2           700    1
1               Microsoft Lumia     2           500    2
6               Lenovo Thinkpad     2           400    3
10              Kindle Fire         3           250    1
2               HTC One             3           200    2
8               Dell Vostro         3           150    3
```

## 8.9. Ntile Function
Hàm PostgreSQL, **NTILE** cho phép bạn chia các hàng theo thứ tự trong phân vùng thành một số nhóm được xếp hạng nhất định có kích thước bằng nhau nhất có thể. Những nhóm được xếp hạng được gọi là *bucket*. Hàm **NTILE** gán cho mỗi nhóm một số bắt đầu từ 1. Đối với mỗi hàng trong một nhóm, hàm **NTILE** chỉ định một số nhóm đại diện cho nhóm mà hàng thuộc về. Cú pháp của hàm **NTILE** như sau:
```sql
    NTILE(buckets) OVER (
        [PARTITION BY biểu_thức_phân_vùng, ... ]
        [ORDER BY biểu_thức_sắp_xếp [ASC | DESC], ...]
    )
```
Hãy cùng kiểm tra cú pháp chi tiết:

Các *buckets* đại diện cho số lượng các nhóm được xếp hạng. Nó có thể là một số hoặc một biểu thức ước tính thành một giá trị nguyên dương (lớn hơn 0) cho mỗi phân vùng. Các *buckets* không được rỗng.

Mệnh đề **PARTITION BY** phân phối các hàng thành các phân vùng mà hàm được áp dụng. Mệnh đề **PARTITION BY** là tùy chọn. Nếu bạn bỏ qua nó, hàm sẽ xử lý toàn bộ tập kết quả dưới dạng một phân vùng duy nhất.

Mệnh đề **ORDER BY** sắp xếp các hàng trong mỗi phân vùng mà hàm được áp dụng. Mệnh đề **ORDER BY** là tùy chọn. Tuy nhiên, bạn nên luôn luôn sử dụng mệnh đề **ORDER BY** để có kết quả như mong đợi. Lưu ý rằng nếu số lượng hàng không chia hết cho các nhóm, hàm **NTILE** trả về các nhóm có hai kích thước với sự khác biệt một. Các nhóm lớn hơn luôn xuất hiện trước các nhóm nhỏ hơn theo thứ tự được chỉ định bởi mệnh đề **ORDER BY**.

Ví dụ này sử dụng hàm **NTILE** để chia các hàng trong bảng *sales_stats* thành hai phân vùng và 3 nhóm cho mỗi nhóm:
```sql
    SELECT 
        name, amount,
        NTILE(3) OVER(PARTITION BY year ORDER BY amount)
    FROM sales_stats;
```
Đối với dữ liệu của bảng sau:   `actual_sales`
```
year    name            amount
-----------------------------------
2018    Jack Daniel     150000.00
2018    Jane Johnson    110000.00
2018    John Doe        120000.00
2018    Stephane Heady  200000.00
2018    Yin Yang        30000.00
2019    Jack Daniel     180000.00
2019    Jane Johnson    130000.00
2019    John Doe        150000.00
2019    Stephane Heady  270000.00
2019    Yin Yang        25000.00
```
Đầu ra phải là:
```
name            amount      ntile
------------------------------------
Yin Yang        30000.00    1
Jane Johnson    110000.00   1
John Doe        120000.00   2
Jack Daniel     150000.00   2
Stephane Heady  200000.00   3
Yin Yang        25000.00    1
Jane Johnson    130000.00   1
John Doe        150000.00   2
Jack Daniel     180000.00   2
Stephane Heady  270000.00   3
```