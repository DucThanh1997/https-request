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
- Request header
| Name        | Description           | Example  |
| ------------- |:-------------:| -----:|
| A-IM | Chấp nhận biến thao tác cho các request | A-IM: feed|
| Accept | Đề cập đến các kiểu dữ liệu cho phép trong phần response | Accept: text/html|
| Accept-Charset | Đề cập đến kiểu charset mà được chấp nhận | Accept-Charset: utf-8 |
| Accept-Datetime | Chấp nhận khoảng thời gian cho phép | Accept-Datetime: Thu, 31 May 2007 20:35:00 GMT	|
| Accept-Encoding | Chấp nhận các kiểu mã hóa | Accept-Encoding: gzip, deflate |
| Accept-Language | Danh sách các ngôn ngữ chấp nhận | Accept-Language: en-US |
| Access-Control-Request-Method, Access-Control-Request-Headers | Khai báo các method request từ 1 domain khác | Access-Control-Request-Method: GET|
| Authorization | là chỗ để nhét token vào | Authorization: Basic QWxhZGRpbjpvcGVuIHNlc2FtZQ== |
| Cache-Control | để chỉ định các lệnh phải tuân theo tất cả các cơ chế caching dọc trong suốt quá trình response. | Cache-Control: no-cache |
| Connection | Kiểm soát các option cho kết nối hiện tại và list ra các hop-by-hop field | Connection: keep-alive, Connection: Upgrade |
| Content-Length | Chiều dài của request body trong hệ bát phân | Content-Length: 348 | 
| Content-MD5 | chuỗi kí tự được mã hóa từ content length bởi base64 Md5 | Content-MD5: Q2hlY2sgSW50ZWdyaXR5IQ== |
| Content-Type | Kiểu dữ liệu của phần thân request | Content-Type: application/x-www-form-urlencoded |
| Cookie | 1 Http-Cookie trước đó được gửi bởi server bằng Set-Cookie | Cookie: $Version=1; Skin=new; |
| Date | date và time khi messages được bắt đầu | Date: Tue, 15 Nov 1994 08:12:31 GMT |  
| Expect | Chỉ ra các hành vi mà client yêu cầu server làm | Expect: 100-continue | 
| Forwarded | Mở ra thông tin ban đầu của khách hàng kết nối với Server web thông qua proxy HTTP. | Forwarded: for=192.0.2.60;proto=http;by=203.0.113.43 Forwarded: for=192.0.2.43, for=198.51.100.17 |
| From | Email của người gửi request | 	From: user@example.com |
| Host | Tên miền của server và Tcp port number | Host: en.wikipedia.org:8080 Host: en.wikipedia.org |
| HTTP2-Settings | Yêu cầu nâng cấp từ HTTP / 1.1 lên HTTP / 2 PHẢI bao gồm chính xác một header field Cài đặt HTTP2. Header field HTTP2-Settings là Header field dành riêng cho connection, bao gồm các tham số điều khiển kết nối HTTP / 2, được cung cấp theo dự đoán của server mà chấp nhận yêu cầu nâng cấp. | HTTP2-Settings: token64 |
| If-Match | Chỉ thực hiện hành động nếu thực thể mà client cung cấp khớp với thực thể tương tự trên máy chủ. Điều này chủ yếu dành cho các phương thức như PUT để cập nhật tài nguyên nếu nó chưa được sửa đổi kể từ lần cuối người dùng cập nhật nó. | If-Match: "737060cd8c284d8af7ad3082f209582d" |
| If-Modified-Since | Cho phép trả lại 304 Không sửa đổi nếu nội dung không thay đổi từ 1 khoảng thời gian. | If-Modified-Since: Sat, 29 Oct 1994 19:43:31 GMT |
| If-None-Match | Cho phép trả lại 304 Không sửa đổi nếu nội dung không thay đổi từ 1 khoảng thời gian. | If-None-Match: "737060cd8c284d8af7ad3082f209582d" |
| If-Range | Nếu thực thể không thay đổi, hãy gửi cho tôi phần mà tôi đang thiếu; nếu không, gửi cho tôi toàn bộ thực thể mới. | If-Range: "737060cd8c284d8af7ad3082f209582d" | 
| If-Unmodified-Since | Chỉ gửi phản hồi nếu thực thể chưa được sửa đổi kể từ một thời điểm cụ thể. | If-Unmodified-Since: Sat, 29 Oct 1994 19:43:31 GMT | 
| Max-Forwards | Giới hạn số lần messages có thể được chuyển tiếp qua proxy hoặc cổng. | Max-Forwards: 10 |
| Origin | Khởi tạo request cross-origin resource sharing | Origin: http://www.example-social-network.com |
| Pragma | Các field cụ thể cho việc triển khai có thể có nhiều effect trong chuỗi response request. | Pragma: no-cache |
| Proxy-Authorization | Authorization Credentials để kết nối với proxy. | Proxy-Authorization: Basic QWxhZGRpbjpvcGVuIHNlc2FtZQ== |
| Range | Request only part of an entity. Bytes are numbered from 0. | Range: bytes=500-999 |
| Referer | Đây là địa chỉ của trang web trước đó có liên kết đến trang hiện được yêu cầu. | Referer: http://en.wikipedia.org/wiki/Main_Page |
| TE | Các mã hóa chuyển giao mà user agent sẵn sàng chấp nhận: điều tương tự với header response field. | TE: trailers, deflate |
| User-Agent | tên trình duyệt và hệ điều hành | User-Agent: Mozilla/5.0 (X11; Linux x86_64; rv:12.0) Gecko/20100101 Firefox/12.0 |
| Upgrade | Yêu cầu server nâng cấp lên giao thức khác. Không được sử dụng trong HTTP / 2 | Upgrade: h2c, HTTPS/1.3, IRC/6.9, RTA/x11, websocket | 
| Via | Thông báo cho Server của proxy những yêu cầu nào đã được gửi | Via: 1.0 fred, 1.1 example.com (Apache/1.1) |
| Warning | Một cảnh báo chung về các vấn đề có thể xảy ra với thực thể. | Warning: 199 Miscellaneous warning |


Response header
| Name        | Description           | Example  |
| ------------- |:-------------:| -----:|
| Access-Control-Allow-Origin, Access-Control-Allow-Credentials, Access-Control-Expose-Headers, Access-Control-Max-Age, Access-Control-Allow-Methods, Access-Control-Allow-Headers | CHỉ ra các website tham gia vào các request | Access-Control-Allow-Origin: * |
| Accept-Patch | Chỉ định định dạng tài liệu nào mà Server này hỗ trợ | Accept-Patch: text/example;charset=utf-8 |
| Accept-Ranges | Kiểu nội dung  mà Server này hỗ trợ thông qua byte serving | Accept-Ranges: bytes |
| Age | Độ tuổi của đối tượng đã ở khi nằm trong cache proxy theo giây | Age: 12 |
| Allow | Chỉ ra các phương thức hợp lệ cho một tài nguyên cụ thể. Được sử dụng cho 405 Method not allowed | Allow: GET, HEAD |
| Alt-Svc | Server sử dụng header "Alt-Svc" (nghĩa là Dịch vụ thay thế) để chỉ ra rằng tài nguyên của nó cũng có thể được truy cập tại một vị trí mạng khác (Server hoặc cổng) hoặc sử dụng giao thức khác. Thay vào đó, khi sử dụng HTTP / 2, các Server nên gửi khung ALTSVC|
 Alt-Svc: http/1.1="http2.example.com:8001"; ma=7200 |
| Cache-Control | Thông báo cho tất cả các cơ chế lưu trữ từ máy chủ đến máy khách xem chúng có thể lưu trữ đối tượng này không. Nó được đo bằng giây | Cache-Control: max-age=3600 | 
| Connection | Các control option cho kết nối hiện tại và danh sách các respond field hop-by-hop. [12] Không được sử dụng với HTTP / 2. | Connection: close |
| Content-Disposition | Để hiển thi hộp thoại "Tải xuống tệp" cho loại MIME đã biết với định dạng nhị phân hoặc đề xuất tên tệp cho nội dung động. Trích dẫn là cần thiết với các ký tự đặc biệt. | Content-Disposition: attachment; filename="fname.ext" |
| Content-Encoding | Các loại mã hóa được sử dụng trên dữ liệu. Xem nén HTTP. | Content-Encoding: gzip |
| Content-Language | Ngôn ngữ tự nhiên hoặc ngôn ngữ của đối tượng dự định có nội dung kèm theo | Content-Language: da |
| Content-Length | length của response body đo bằng octet | Content-Length: 348 |
| Content-Location | Một vị trí thay thế cho dữ liệu được trả về | Content-Location: /index.htm |
| Content-MD5 | chuỗi kí tự được mã hóa từ content length bởi base64 Md5 | Content-MD5: Q2hlY2sgSW50ZWdyaXR5IQ== | 
| Content-Range | Khoảng của 1 phần dữ liệu trên full-body message | Content-Range: bytes 21010-47021/47022 |
| Content-Type | type của nội dung | Content-Type: text/html; charset=utf-8 |
| Date | date và time message được gửi | Date: Tue, 15 Nov 1994 08:12:31 GMT |
| Delta-Base | Chỉ ra thẻ được mã hóa delta của thực thể phản hồi | Delta-Base: "abc" |
| Expires | Cung cấp ngày / thời gian sau đó phản hồi được coi là hết hạn | Expires: Thu, 01 Dec 1994 16:00:00 GMT |
| IM | Thao tác với biến áp dụng cho response | IM: feed|
| Last-Modified | Ngày sửa đổi cuối cùng cho đối tượng được yêu cầu | Last-Modified: Tue, 15 Nov 1994 12:45:26 GMT |
| Link | Được sử dụng để thể hiện mối quan hệ được với các tài nguyên khác | Link: </feed>; rel="alternate" |
| Location | Được sử dụng trong chuyển hướng hoặc khi một tài nguyên mới đã được tạo. | Example 1: Location: http://www.w3.org/pub/WWW/People.html, Example 2: Location: /pub/WWW/People.html | 
| P3P | Trường này được cho là đặt default P3P, dưới dạng P3P: CP = "your_compact_policy". Tuy nhiên nếu P3P không được đặt, [50] hầu hết các trình duyệt đều không thực hiện đầy đủ, rất nhiều trang web đặt trường này bằng fake policy text, đủ để đánh lừa sự tồn tại của chính sách P3P và cấp quyền cho cookie của bên thứ ba. | P3P: CP="This is not a P3P policy! See https://en.wikipedia.org/wiki/Special:CentralAutoLogin/P3P for more info." |
| Pragma | Các field cụ thể cho việc triển khai có thể có nhiều effect trong chuỗi response request. | Pragma: no-cache |
| Proxy-Authenticate | Yêu cầu xác thực để truy cập proxy. | Proxy-Authenticate: Basic | 
| Public-Key-Pins | Ghim HTTP public key, thông báo hash of website's authentic TLS certificate | Public-Key-Pins: max-age=2592000; pin-sha256="E9CZ9INDbd+2eRQozYqqbQ2yXLVKB9+xcprMF+44U1g="; | 
| Retry-After | Nếu một thực thể tạm thời không có sẵn, Retry-After sẽ hướng dẫn client thử lại sau. Giá trị có thể là một khoảng thời gian xác định (tính bằng giây) hoặc ngày | Example 1: Retry-After: 120, Example 2: Retry-After: Fri, 07 Nov 2014 23:59:59 GMT | 
| Server | Tên của server | Server: Apache/2.4.1 (Unix) | 
| Set-Cookie | An HTTP cookie | Set-Cookie: UserID=JohnDoe; Max-Age=3600; Version=1 |
| Strict-Transport-Security | HSTS policy thông báo cho client HTTP thời gian lưu trữ cache trong bao lâu và liệu điều này có áp dụng cho tên miền phụ hay không. | Strict-Transport-Security: max-age=16070400; includeSubDomains |
| Trailer | Giá trị chung của Trailer cho biết tập hợp các header field có mặt trong đoạn giới thiệu của một thông điệp được mã hóa bằng  chunked transfer coding. | Trailer: Max-Forwards |
| Transfer-Encoding | Hình thức mã hóa được sử dụng để chuyển thực thể một cách an toàn tới người dùng. Các phương thức được xác định hiện tại là: chunked, compress, deflate, gzip, identity. Không được sử dụng với HTTP / 2 | Transfer-Encoding: chunked |
| Tk | Tracking Status header, giá trị được đề xuất để gửi phản hồi cho một DNT (không theo dõi), các giá trị có thể: "!" — under construction | Tk: ? |




 






































