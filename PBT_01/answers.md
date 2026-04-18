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
