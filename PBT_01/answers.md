CÂU A1
1,
- Sau khi nhập link shoppe và nhấn Enter, trình duyệt sẽ chuyển đổi tên miền thành địa chỉ IP
- IP sau đó sẽ được gửi đi để tìm kiếm trang web trên mạng
- Sau khi tìm thấy, trình duyệt sẽ gửi đi một request GET để xem trang chủ
- Server sau khi nhận được request sẽ xử lý và gửi trả một response 200 OK
- Trình duyệt nhận được file trả về thì render lại lên màn hình

2,
Ảnh được đặt trong folder /screenshot
status code: StatusCode_shopee.vn.png
thời gian load trang: TotalLoadingTime_shopee.vn.png
request trả về file CSS: HTMLRequest_shopee.vn.png

tham chiếu: tuan1html5/01_introduction_html_universe.md

CÂU A2
<div class="header">
    <div class="logo">ShopTLU</div>
    <div class="menu">
        <div><a href="/">Trang chủ</a></div>
        <div><a href="/products">Sản phẩm</a></div>
    </div>
</div>
<div class="main">
    <div class="product">
        <div class="title">iPhone 16 Pro</div>
        <div class="price">25.990.000đ</div>
        <div class="image"><img src="iphone.jpg"></div>
    </div>
</div>
<div class="footer">© 2026 ShopTLU</div>

Đoạn code trên bị đánh giá thấp bởi nó đã chia các khối một cách thiếu sự rõ ràng dành cho google. Bởi vì có quá nhiều khối div đan xen vào nhau khiến cho google bị rối.

Ta có thể thấy một số lỗi ở đây:
- Phần header của trang web dùng div với class header trong khi có thể dùng tag header
- Phần body của trang web lại dùng div với class main thay vì tag main
- Phần footer của trang web dùng div với class footer thay vì tag footer
- Bên trong phần header thay vì khối div class menu có thể dùng tag menu
- Tag div với class product có thể dùng tag article
- Phần title dùng tag h2
- Phần price dùng tag h3
- Phần image dùng tag image

Sửa lỗi:
<header>
    <div class="logo">ShopTLU</div>
    <menu>
        <div><a href="/">Trang chủ</a></div>
        <div><a href="/products">Sản phẩm</a></div>
    </menu>
</header>
<main>
    <article class="product">
        <h2 class="title">iPhone 16 Pro</h2>
        <h3 class="price">25.990.000đ</h3>
        <image class="image"><img src="iphone.jpg"></image>
    </article>
</main>
<footer>© 2026 ShopTLU</footer>

tham chiếu: tuan1html5/04_visible_part_html.md

CÂU A3
đã được minh họa trong \screenshots\ExA3_illustrates.png

Ảnh được mô tả như trên đó là bởi khối đầu là <div>, khối này chiếm toàn bộ dòng thế nên hai <span> kế đó bị đẩy xuống dòng dưới. Trong khi đó, các khối <span> chỉ chiếm nội dung nên chúng không đẩy nhau xuống mà đứng cạnh nhau. Và tương tự như vậy khối <div> thứ 2 lại xuống dòng và hai line kế đó đứng cạnh nhau ở dòng kế dưới rồi lại tới khối <div> thứ 3. Bên cạnh đó, vì line "Inline 2 — nằm cạnh nhau" được đặt trong tag <strong> nên nó được in đậm.

tham chiếu: tuan1html5/04_visible_part_html.md

CÂU A4
với mỗi tag của table có ý sau đây:
- <thead> dùng để hiển thị tiêu đề cột
- <tbody> dùng để hiển thị các dữ liệu chính
- <tfooter> dùng để hiển thị tổng kết của table

lý do không sử dụng table để tạo layout là bởi:
- Nó làm hỏng ngữ nghĩa mà HTML hướng đến
- Bảng không thân thiện với người dùng vì nó khiến cho người dùng bị nhầm lẫn thứ tự đọc, trình bày không dễ hiểu
- Cấu trúc của table bị cứng nhắc, khiến cho nó khó thích ứng được với các thiết bị khác, đặc biệt là điện thoại di động, khiến cho trang web không dễ nhìn (xấu)

tham chiếu: https://www.quora.com/Why-is-it-considered-a-bad-practice-to-use-table-for-web-page-layout

Câu B3
Lỗi 1: Dòng 1 - Sai cú pháp, không tồn tại tag <DOCTYPE> - Đổi thành <DOCTYPE html>
Lỗi 2: Dòng 2 - Mở tag <html> nhưng không có đóng - Thêm </html> vào cuối cùng để đóng
Lỗi 3: Dòng 4 - Mở tag <title> nhưng không có đóng - Thêm </title> sau dòng "Trang web"
Lỗi 4: Dòng 8 - Sai cú pháp khi đóng tag <h1> - Sửa thành </h1>
Lỗi 5: Dòng 12 - Sai cú pháp khi đóng tag <a> - Sửa thành </a>
Lỗi 6: Dòng 21 - Sai cú pháp, không thể để hai tag móc chéo vào nhau - Đóng tag b trước rồi mới đóng p
Lỗi 7: Dòng 40 và 42 - Sai ngữ nghĩa dành cho google - đổi thành một tag khác, ví dụ là aside
Lỗi 8: Dòng 28 và 31 - Không có tag <thead> để tạo tiêu đề cho table - Tạo tag <thead> rồi đẩy các tiêu đề vào trong
Lỗi 9: Dòng 32 và 35 - Không có tag <tbody> để tạo tiêu đề cho table - Tạo tag <tbody> rồi đẩy các tiêu đề vào trong
Lỗi 10: Dòng 49 - Mở tag <p> nhưng không đóng - Thêm vào Đóng tag </p>

Câu B4
- Trong trang tiki.vn có 3 thẻ sematic là head ở đầu (nằm ẩn phía sau trang web), body ở thân (bao gồm toàn bộ phần hiển thị trên trang web) và main ở bên trong body (hiển thị các phần thông tin chính). Ảnh chụp màn hình tương ứng là headTag_tiki.vn.png, bodyTag_tiki.vn.png, mainTag_tiki.png trong thư mục screenshots
- Ngoài các thẻ sematic trên, còn có những thẻ non-sematic khác, trong đó có hai thẻ là <div class="sc-4a670bf7-0 iujNlz"> hiển thị một thanh bar với các mục cam kết và khuyến mại ở trên và <div class ="sc-dcf63fc3-1 jdXJsQ"> hiển thị một hộp chứa thông tin liên lạc với nhân viên hỗ trợ của tiki. Ảnh chụp màn hình tương ứng là divClassVoucher_tiki.vn.png và contactDiv_tiki.png

Câu C1
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Đây là shopee đè tem!</title>
</head>
<body>
    <header>
        <nav aria-label="breadcrumb"> <!--dùng nav vì đây là điều hướng-->
            <a href="#home">Chi tiết sản phẩm</a>
            <a href="#phones">Đánh giá</a>
            <a href="#iPhone16">Sản phẩm liên quan</a>
        </nav>
    </header>

    <main> <!--tạo ra một mục khác nằm dưới header-->
        <section id="iPhone16"> <!--tạo một section riêng cho thông tin tổng quát của sản phẩm-->
            <article> <!--ảnh của sản phẩm được đặt vào một bên nên đặt vào một article riêng-->
                <img src="https://placehold.co/300x200">
                <img src="https://placehold.co/300x200">
                <img src="https://placehold.co/300x200">
                <img src="https://placehold.co/300x200">
                <img src="https://placehold.co/300x200">
            </article>

            <article> <!--đây là dành cho thông tin sán phẩm-->
                <h3>iPhone 16</h3> <!--đây là tiêu đề sản phẩm nên đặt trong h3-->
                <p>Giá: <b>29.990.000 VND</b></p> <!--các phần dưới chỉ dùng p để hiển thị đoạn văn-->
                <p>Đánh giá: 4.5/5 sao</p>
                <p>Đây là mô tả chi tiết về sản phẩm iPhone 16.</p>
            </article>
        </section>

        <section> <!--để cho trang web được đẹp và dễ nhìn, tách riêng phần thông số kỹ thuật mà không phải ai cũng xem xuống-->
            <h3>Thông số kỹ thuật</h3>
            <ol> <!--dùng ol vì các thông số của sản phẩm là danh sách có thứ tự-->
                <li>CPU: A18 Bionic</li>
                <li>RAM: 8 GB</li>
                <li>Storage: 128 GB</li>
                <li>Display: 6.1 inch Super Retina XDR</li>
            </ol>
        </section>

        <section id="reviews"> <!--tạo một section riêng cho phần đánh giá của khách hàng-->
            <h3>Đánh giá của khách hàng</h3>
            <article> <!--mỗi đánh giá của khách hàng sẽ được đặt trong một article riêng cho dễ nhìn-->
                <p><b>Nguyễn Văn A:</b> Sản phẩm rất tốt, đáng tiền!</p>
            </article>

            <article>
                <p><b>Trần Thị B:</b> Mình rất hài lòng với chất lượng của iPhone 16.</p>
            </article>

            <article>
                <p><b>Lê Văn C:</b> Sản phẩm có thiết kế đẹp và hiệu năng mạnh mẽ.</p>
            </article>
        </section>

        <section id="related_products"> <!--tạo một section riêng cho phần sản phẩm liên quan-->
            <h3>Sản phẩm liên quan</h3>
            <article> <!--mỗi sản phẩm liên quan sẽ được đặt trong một article riêng cho dễ nhìn-->
                <img src="https://placehold.co/300x200">
                <p><b>iPhone 16 Pro:</b> Giá: 39.990.000 VND</p>
            </article>

            <article>
                <img src="https://placehold.co/300x200">
                <p><b>iPhone 16 Pro Max:</b> Giá: 49.990.000 VND</p>
            </article>

            <article>
                <img src="https://placehold.co/300x200">
                <p><b>iPhone 15:</b> Giá: 19.990.000 VND</p>
            </article>
        </section>
    </main>

    <footer>
        <p>&copy; 2024 Shopee. All rights reserved.</p>
    </footer>
</body>
</html>

