Câu A1:
Để nhúng vào HTML ta có 3 cách: inline (trong dòng), internal (trong file), external (trong một file css ngoài)
Trong đó:
- inline:
    - VD:
        <h1 style="color=red; height=50%;">Đây là tiêu đề</h1>
    - Ưu điểm là dễ dùng, nhanh gọn và thuận tiện khi cần phải đối phó với những tình huống bắt buộc
    - Nhược điểm là khó bảo trì, khó tìm khi cần sửa và không thể tái sử dụng
    - Chỉ nên dùng tại những khối hoặc line dùng một lần, hoặc dùng trong những tình huống chưa biết phải phải xử lý như nào thì có thể dùng tạm

- internal:
    - VD:
        <head>
            <style>
                h1 { color: #2563eb; font-size: 32px; }
            </style>
        </head>

        <main> <h1>Đây là tiêu đề</h1> </main>
    
    - Ưu điểm dễ sửa chữa hơn inline và đã có thể tái sử dụng nhiều lần
    - Nhược điểm là vẫn chỉ có thể sử dụng trong một trang cố định, không dùng được cho các website có nhiều trang web
    - Thường chỉ dùng cho các trang đơn, tức các website có một trang web, hoặc các bản prototype của các trang web đang trong quá trình phát triển

- external:
    - VD:
        <head>
            <link rel="stylesheet" href="styles.css">
        </head>

        bên trong style.css có: h1 { color: #2563eb; font-size: 32px; }

    - Ưu điểm là có thể chỉnh sửa, có thể dùng lại nhiều lần trong nhiều file khác nhau
    - Nhược điểm là trình duyệt sẽ phải tải thêm file css bên ngoài dẫn đến việc bị trễ hình ảnh, trình duyệt sẽ hiển thị trang HTML thô trước khi có trang hoàn chỉnh với css
    - Thường xuyên dùng trong nhiều dự án khác nhau nhưng có thể không cần thiết với những trang web nhỏ hoặc các bài tập dành cho sinh viên

- Đối với một element được dùng tới ba cách, đầu tiên ta xem xét bên trong head thì nó sẽ tuân theo quy tắc inline > internal > external với độ mạnh giảm dần. Tuy nhiên, khi không xét tới bên trong head nữa hoặc là đó là hai style css cùng cấp thì độ "mạnh yếu" lại bị phụ thuộc vào việc cái nào được biên dịch trước cái nào được biên dịch sau, do trình biên dịch sẽ đọc từ trên xuống dưới, vì vậy cái nào xuất hiện trước sẽ được hiểu trước nhưng khi gặp cái tiếp theo thì nó sẽ bị ghi đè và cái cuối cùng là thứ xuất hiện trên màn hình.

Câu A2:
1. h1                           → Chọn: <h1>ShopTLU</h1>
2. .price                       → Chọn: <p class="price">25.990.000đ</p> và <p class="price">45.990.000đ</p>
3. #app header                  → Chọn:
    <header class="top-bar dark">
        <h1>ShopTLU</h1>
        <nav>
            <a href="/" class="active">Home</a>
            <a href="/products">Products</a>
            <a href="/about">About</a>
        </nav>
    </header>
4. nav a:first-child             → Chọn: <a href="/" class="active">Home</a>
5. .product.featured h2         → Chọn:
    <article class="product featured">
        <h2>MacBook Pro</h2>
        <p class="price">45.990.000đ</p>
        <p>Mô tả sản phẩm...</p>
    </article>
6. article > p                  → Chọn: <p class="price">25.990.000đ</p> và <p>Mô tả sản phẩm...</p> và <p class="price">45.990.000đ</p> và <p>Mô tả sản phẩm...</p>
7. a[href="/"]                  → Chọn: <a href="/" class="active">Home</a>
8. .top-bar.dark h1              → Chọn: <h1>ShopTLU</h1>

Câu A3:

/* Trường hợp 1: content-box (mặc định) */
.box-1 {
    width: 400px;
    padding: 20px;
    border: 5px solid black;
    margin: 10px;
}
→ Chiều rộng hiển thị = 450px
→ Không gian chiếm trên trang = 470px

/* Trường hợp 2: border-box */
.box-2 {
    box-sizing: border-box;
    width: 400px;
    padding: 20px;
    border: 5px solid black;
    margin: 10px;
}
→ Chiều rộng hiển thị = 400px
→ Kích thước content thực tế = 450px
→ Không gian chiếm trên trang = 420px

/* Trường hợp 3: Margin collapse */
.box-a { margin-bottom: 25px; }
.box-b { margin-top: 40px; }
→ Khoảng cách giữa box-a và box-b = 40px
→ Giải thích tại sao KHÔNG PHẢI 65px -> đó là do hiện tượng margin collapse đã xảy ra, hiện tượng này chỉ xảy ra khi Giữa hai block elements nằm dọc không có border/padding giữa chúng hoặc Margin con với margin cha khi cha không có border/padding/overflow

/* trong trường hợp Nếu .box-a có margin-bottom: -10px và .box-b có margin-top: 40px, thì khoảng cách vẫn sẽ bằng 40px vì vẫn tuân theo quy tắc của margin collapse

Câu A4:
1,
|       |  #id  |  .class  |  tag  |
|   A   |   0   |    0     |   1   | = 001
|   B   |   0   |    1     |   0   | = 010
|   C   |   1   |    0     |   0   | = 100
|   D   |   0   |    1     |   1   | = 011

2, màu của element là màu đỏ

3, màu của element là màu cam

4, màu của element là màu đen

Câu B1:
Các loại Selector được dùng là:
- unversal selector: *

- type selector:
    - body
    - header
    - table
    - footer

- class selector:
    - .profile-picture 
    - .introduce-para

- id selector:
    - #about_me
    - #skill

- combination selector:
    - footer aside
    - footer aside label
    - footer h6
    - table th
    - nav a
    - footer aside .info .first-half
    - footer aside .info .second-half
    - nav a:hover
    - nav a .active
    - tr:nth-child(odd)
    - tr:hover

Câu B2:
Phần 1
Hộp 1 (content-box): chiều rộng thực tế = 350 px
Hộp 2 (border-box): chiều rộng thực tế = 300 px

Giải thích: Điều này xảy ra là nhờ thiết lập "box-sizing: border-box" của box2. Với box1, chiều rộng của nó không thực sự là 300px mà là 300px của nội dung bên trong + 20x2px của hai padding + khoảng 5x2px của border xung quanh, tức là 350px. Còn box2 do có thiết lập trên nên nó đã tự co lại phần content bên trong để sao cho phù hợp với padding và border bên ngoài, thành ra tổng của chúng cộng lại chính xác là 300px.

Phần 2
Khi có border-box thì: (225px + 15px*2)[box3] + (450px +20px*2)[box4] + (225px +15px*2)[box5] = 1000px = 1000px [container]

Khi không có borber-box: 

Câu B3:
thứ tự các rule với specificity từ thấp tới cao là:
- * { color: blue; } /*1, 000*/ 
- p { color: red; } /*2, 001*/
- *.text { color: violet; } /*3, 010*/
- .text { color: green; } /*4, 010*/
- p.text { color: purple; } /*5, 011*/
- #demo { color: orange; } /*6, 100*/
- p#demo { color: pink; } /*7, 101*/
- .text#demo { color: brown; } /*8, 110*/
- p.text#demo { color: gray; } /*9, 111*/
- p { color: black !important;} /*10, vô hạn*/

element cuối cùng có màu đen bởi vì giá trị của rule thứ 10 là mạnh nhất do có "!important".

dù cho có thay đổi thứ tự rule trong specificity.css thì kết quả cũng không hề đổi do giá trị speficity của các rule là không đổi và trình biên dịch thì phải đọc xong specificity.css thì mới in dựa theo nó.

Câu C1:
- chiều rộng thực tế của side-bar là 300px + 20px*2 + 1px*2 = 342px
- chiều rộng thực tế của content là 660px + 30px*2 + 1px*2 = 722px
- lý do layout bị vỡ là do kích thước thực tế mà layout phải chứa là 342 + 720 = 1060px, vượt quá khả năng chứa chiều rộng của layout vốn chỉ có 960px chiều rộng
- ta có hai cách sửa đó là dùng border-box hoặc giảm kích thước padding (hoặc width) của side-bar và content xuống sao cho kích thước vừa với 960px

