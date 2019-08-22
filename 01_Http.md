# Http

## Định nghĩa
HTTP là viết tắt của “HyperText Transfer Protocol”, hay còn gọi là giao thức truyền tải siêu văn bản. 
Tức là nó dùng để chuyển và nhận dữ liệu mỗi khi có yêu cầu.

## Client và Server
Client tức là cái mà chúng ta sử dụng để yêu cầu truy cập nội dung của trang web, ví dụ như dùng điện thoại, laptop. Còn server cũng là một máy tính nhưng nó mạnh hơn client rất nhiều, được thuê hoặc dựng bởi những người chủ trang web. 

Việc client và server giao tiếp với nhau thì cần phải có mạng, cũng giống như việc bạn muốn giao tiếp với hotgirl thì cần dùng tiền vậy đó.

## Http Header
HTTP header là phần đầu của HTTP (head là đầu rồi) trong mỗi request mà client gửi tới server cũng như response của server gửi về cho client.

Mỗi khi truy cập vô một url thì chúng ta sẽ thực hiện gửi và nhận nhiều HTTP request nên đồng thời cũng gửi và nhận nhiều HTTP header kèm theo.

Bởi vì được “gửi và nhận bởi client và server” nên HTTP header sẽ chứa thông tin chủ yếu về client và server. Cụ thể là thông tin của trình duyệt, thông tin cấu hình server, ngày tháng, thông tin về request page, kiểu dữ liệu truyền tải,…

### Http Header chứa gì
- Host: tên trang web
- User-Agent: Là thông tin về browser
- Accept: là kiểu dữ liệu sẽ nhận được từ response
- Accept-Encode: là nơi khai báo kiểu mã hóa nội dung mà request chấp nhận, nếu server trả về nội dung mã hóa khác với kiểu mã hóa đã khai báo thì tất nhiên là client sẽ không nhận rồi.
- Cookie: là nơi chứa thông tin được mã hóa dùng để gửi lên server (sau khi đã được website gửi về để lưu trữ trước đó). Mà đã mã hóa thì dĩ nhiên nó quan trọng, còn việc chứa thông tin gì thì do website quy định nên mình cũng không biết được. Ngoài ra session đôi khi sẽ dựa vào cookie để giúp server phân biệt ai là người đang gửi request.
- Upgrade-Insecure-Requests: là cảnh báo của trình duyệt đối với những giao thức http vì hiện nay nó đã không còn an toàn và có nguy cơ bị đánh cắp dữ liệu (đặc biệt là thông tin đăng nhập, tài khoản ngân hàng). Cách tốt nhất hiện nay là nâng cấp lên https để dữ liệu truyền tải được an toàn hơn.

## HTTP response header
| Name        | Description           | Example  |
| ------------- |:-------------:| -----:|
| A-IM | Chấp nhận biến thao tác cho các request | A-IM: feed|
| Accept | Đề cập đến các kiểu dữ liệu cho phép trong phần response | Accept: text/html|
| Accept-Charset | Đề cập đến kiểu charset mà được chấp nhận | Accept-Charset: utf-8 |
| Accept-Datetime | Chấp nhận khoảng thời gian cho phép | Accept-Datetime: Thu, 31 May 2007 20:35:00 GMT	|
| Accept-Encoding | Chấp nhận các kiểu mã hóa | Accept-Encoding: gzip, deflate |
| Accept-Language | Danh sách các ngôn ngữ chấp nhận | Accept-Language: en-US |
| Access-Control-Request-Method, Access-Control-Request-Headers | Khai báo các method request từ 1 domain khác | Access-Control-Request-Method: GET|














































