PHẦN A:
Bài A1:
type="text" <!--ô nhập text, dùng trong trang tra cứu thông tin-->
type="email" <!--ô nhập text, tự kiểm tra xem có @ không, dùng trong form đăng ký-->
type="passwords" <!--ô nhập text, ký tự bị ẩn đi, dùng trong form đăng ký-->
type="number" <!--ô nhập số, phía bên phải có hai mũi tên nhỏ để tăng giam bằng cách click vào, không thể nhập ký tự nào ngoài số, có thể dùng trong form tạo đơn hàng>
type="tel" <!--ô nhập text, tự kích hoạt bàn phím số trên điện thoại, có thể dùng trong form đăng ký-->
type="date" <!--ô nhập ngày tháng, chỉ có thể nhập ngày tháng năm theo format định sẵn (dd/mm/yyyy), có thể chọn ngày qua cửa sổ pop up được cung cấp theo, dùng trong form đăng ký tạm trú tạm vắng-->
type="color" <!--ô chọn màu, có thể dùng trong form vẽ tranh-->
type="range" <!--thanh trượt có giá trị, có thể dùng trong form text có tăng giảm cỡ chữ-->
type="file" <!--ô chọn file từ máy tính, có thể dùng trong trang cần đăng tải ảnh-->
type="url" <!--Ô nhập text, kiểm tra xem có phải url không, dùng trong form tìm kiếm trang web-->

Bài A2:

<!-- Trường hợp 1 -->
<input type="text" required value="">   <!-- User để trống -->
->không có gì xảy ra cả, vì input này không hề yêu cầu điều kiện gì

<!-- Trường hợp 2 -->
<input type="email" value="abc">        <!-- User gõ "abc" -->
->thông báo đây không phải là email, vì input này yêu cầu đầu vào phải có dạng một email

<!-- Trường hợp 3 -->
<input type="number" min="1" max="10" value="15"> <!-- User gõ 15 -->
->thông báo lỗi nhập dữ liệu, vì giá trị cho phép chỉ từ 1 đến 10

<!-- Trường hợp 4 -->
<input type="text" pattern="[0-9]{10}" value="abc123"> <!-- User gõ "abc123" -->
->thông báo lỗi nhập dữ liệu, vì chỉ nhận giá trị từ 0 đến 9 và phải gồm 10 số


<!-- Trường hợp 5 -->
<input type="password" minlength="8" value="123">  <!-- User gõ "123" -->
->thông báo lỗi nhập, vì đầu vào yêu cầu text phải ít nhất 8 chữ số.

Bài A3:
- <label for="email"> quan trong cho người dùng screen reader bởi nhờ có nó nên người sử dụng có thể biết được bản thân phải nhập vào một địa chỉ email và có thể tự động báo lỗi nếu người đó nhập sai
- vì thẻ field set và legend là dùng để tạo ra một khung viền và tiêu đề để nhóm lại một nhóm các thành phần nào đó, nó nên được sự dụng khi dev muốn người dùng hiểu rằng những thông tin họ cần nhập thuộc về một thực thể lớn hơn bao trùm lấy thông tin của những thứ bên trong, tránh gây hoang mang và khó hiểu cho người dùng
- thẻ arial-lable được dùng cho những phần tử có thể không có văn bản hiển thị, nó sẽ giúp cho những người khuyết tật (người dùng trình đọc màn hình) có thể biết được thông tin cần thiết để tương tác
- tuy nhiên không nên sử dụng arial-label trong những trường hợp nội dung cần hiển thị phải rõ ràng để hướng dẫn người sử dụng, bởi với một số người khuyết tật nhận thức, đôi khi họ sẽ hiểu sai và trở nên hoang mang vì không hiểu sao thông tin mình thấy lại khác thứ mình nghe. Mặt khác, việc sử dụng quá nhiều arial-label có thể dẫn tới việc khó bảo trì do dev có thể bị rối khi không biết nhãn đó đến từ đâu.

tham khảo: https://viblo.asia/p/cach-su-dung-thuoc-tinh-html-de-lam-cho-trang-web-va-ung-dung-cua-ban-de-truy-cap-hon-p1-qPoL7ZGNJvk

Bài A4:
- Thuộc tính loading="lazy" của thẻ <img> là một cách để trì hoãn việc load hình ảnh cùng lúc với trang web, ảnh chỉ được load khi người dùng lướt tới. Khi một trang web tải trang hình xuống, nếu ngay lập tức ra lệnh tải ảnh xuống thì sẽ mất rất nhiều thời gian để load cùng lúc những tấm ảnh xuống và người dùng cũng không thể ngay một lúc tiêu thụ hết ngay. Vì vậy, khi ta dùng loading="lazy" tốc độ trải nghiệm trang web sẽ tốt hơn và đi theo nhịp dùng của người sử dụng. Tuy nhiên, chúng ta không nên sử dụng loading="lazy" ở đầu của trang vì trình duyệt không hề biết trước kích thước ảnh cho đến khi load và bởi vậy nên sẽ có thể gây ra hiện tượng layout-shift (đẩy các nội dung xung quanh ra xa) gây ra khó chịu cho người dùng.

- Do không phải lúc nào trình duyệt cũng cung cấp định dạng video mà người thêm dùng, vậy nên thêm nhiều source cho thẻ <video> là một cách đảm bảo cho video muốn đăng tải có thể chạy mượt mà, do trình duyệt sẽ chọn nguồn đầu tiên mà nó hỗ trợ.
- Một số định dạng video phổ biến là: mp4, mvk, webm

- Thuộc tính alt của thẻ img cung cấp văn bản hiển thị thay cho hình ảnh nếu nó bị lỗi hoặc khi có googlebot đọc qua nó sẽ trở thành thứ giúp cho bot hiểu hình ảnh đó miêu tả thứ gì 
- Ba ví dụ alt tốt:
    - iPhone16
    - <tên ảnh ngắn gọn>+Dec
    - Q1-2026-GDP
tham khảo:
- https://topdev.vn/blog/kien-thuc-ve-lazy-loading-images-ma-ban-can-biet/
- https://developer.mozilla.org/en-US/docs/Web/HTML/Reference/Elements/video#usage_notes
- https://quantrimang.com/hoc/the-html-video-205569
- https://khoahoc.vietjack.com/question/1486759/thuoc-tinh-alt-trong-the-img-co-vai-tro-gi
- https://quantrimang.com/cong-nghe/the-alt-la-gi-172757

Bài A5:
- Cách một được sử dụng khi ta chỉ muốn hiển thị một hoặc bất kỳ tấm ảnh nào chúng ta muốn nó xuất hiện trên trang web. Ví dụ như ảnh background của cgv.vn.
- Cách hai được dùng khi chúng ta muốn một hình ảnh có thể để minh họa cho một thông tin nào đó cần thiết phải có hình ảnh bên cạnh. Ví dụ như quảng cáo của một sản phẩm nào đó trên trang bán hàng online.

