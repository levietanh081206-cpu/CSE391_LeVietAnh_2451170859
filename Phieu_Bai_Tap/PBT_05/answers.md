# PHẦN A:
## Bài A1:
- 1: <meta name="viewport" content="width=device-width, initial-scale=1.0">
--> thuộc tính name xác định loại thông tin mà thẻ meta sẽ xung cấp cho thẻ meta
--> giá trị viewport là để xác định loại thông tin mà thẻ meta sẽ cung cấp là về viewport của thiết bị
--> thuộc tính content xác định các thiết lập cụ thể cho loại thông tin thẻ meta cung cấp
--> giá trị width=device-width thiết lập để viewport rộng bằng chiều dài thiết bị truy cập
-- giá trị initial-scale=1.0 thiết lập giá trị thu phóng ban đầu là 100%

- 2: Nếu thiếu dòng đó, điện thoại sẽ giả định trang rộng 980px (như desktop), từ đó thu nhỏ lại làm cho chữ bé xíu, đó là một UX tệ.

- 3:
--> Sự khác nhau cốt lõi nhất của Mobile-first và Dekstop-first đó là nằm ở tư duy phát triển. Với Mobile-first thì chúng ta sẽ xây dựng giao diện cho Mobile trước rồi sau đó mở rộng thêm các điều chỉnh, tính năng dành cho Desktop sau. Còn đối với Dekstop ta sẽ làm giao diện cho desktop trước rồi mới tìm cách thu gọn rồi co nhỏ lại cho vừa với mobile.

--> ví dụ cho Mobile:
/* 1. Code cho mobile trước (không cần @media) */
.product-grid {
    display: grid;
    grid-template-columns: 1fr;
    gap: 16px;
}

/* 2. Thêm complexity khi màn hình rộng hơn */
@media (min-width: 768px) {
    .product-grid {
        grid-template-columns: repeat(2, 1fr);   /* 2 cột tablet nhỏ */
    }
}

--> ví dụ cho Desktop
/* 1. Code cho desktop trước (không cần @media) */
.product-grid {
    display: grid;
    grid-template-columns: repeat(4, 1fr);     /* 4 cột desktop lớn */
    gap: 16px;
}

@media (max-width: 768px) {
    .product-grid {
        grid-template-columns: repeat(3, 1fr);   /* 3 cột desktop */
    }
}

- lý do mobile-first tốt hơn là vì
    - mobile tải css ít hơn, chỉ cần tải css cho mobile nếu truy cập bằng mobile.
    - giúp cho lập trình viên tường minh hơn trong tư duy lập trình khi phải tập trung vào nội dung cần lập trình trước thay cho việc phải style css để căn chỉnh khung hình.
    - Google và performance tools đánh giá cao hơn.

## Bài A2:
- bảng breakpoint chuẩn:

| Kích thước pixel |  thiết bị đại diện  | số cột hiển thị |
|------------------|---------------------|-----------------|
|     > 576px      |      iPhone Se      |        1        |
|    <= 576px      |     iPhone Plus     |        2        |
|    >= 768px      |      iPad dọc       |       2-3       |
|    >= 992px      |     Laptop nhỏ      |        4        |
|    >= 1200px     | Desktop, laptop lớn |       4-6       |
|    >= 1400px     |     Màn hình 4K     |       4-6       |

## Bài A3:
| Chiều rộng màn hình |    .container width     |
|---------------------|-------------------------|
|  375px (iPhone SE)  |           395px         |
|        600px        |	          560px         |
|        800px        |	          740px         |
|        1000px       |	          980px         |
|        1400px       |	         1160px         |


## Bài A4:
- Variable($primary-color): tính năng này cung cấp cho dev "biến" để có thể tái sử dụng nhiều lần trong css, khi đó với việc đổi thuộc tính mà "biến" đang chứa sẽ làm cho tất cả những phần tử đang dùng thuộc tính của "biến" thay đổi đồng bộ, đổi một lần sửa toàn bộ.
- Nesting (viết CSS lồng nhau): tính năng này cho phép dev có thể truy cập và style các phần tử con của phần tử đang được chọn bởi selector. Với cách nào, dev có thể hình dung một cách toàn cảnh mục mình đang style và dễ dàng biết được mình đang làm gì với phần tử nào trong phần tử nào.
- Mixins (@mixin, @include): tương tự như cách hoạt động của các hàm trong các ngôn ngữ khác, tính năng này cho phép dev tái sử dụng những hàm đã được style đối với những phần tử có đặc điểm thiết kế giống nhau, từ đó tiết kiệm thời gian và công sức của người lập trình.
- @extend / Inheritance: tương tự, scss cũng cung cấp một tính năng để tạo các lớp thừa kế, từ đó có thể tiếp kiệm thời gian và phù hợp với overide

- Lý do scss không thể chạy trên trình duyệt là:
    - trình duyệt tuân theo các tiêu chuẩn của CSS/HTML/JS để xác định cách hoạt động, nhưng scss lại chỉ là một bộ tiền xử lý mà sau đó sẽ được biên dịch trở thành CSS. Việc sử dụng đồng thời cả hai sẽ làm mờ đi ranh giới giữa công cụ và quá trình render hình ảnh.
    - scss có các tính năng và hệ sinh thái khác với CSS/HTML/JS, muốn browser dùng cả scss với các ngôn ngữ trên sẽ cần một quá trình dài để tạo ra các đặc tả tương thích được với nhau.
    - Tiền xử lý bị giới hạn bởi I/O và CPU (nhập tệp, ánh xạ, thực thi hàm). Chạy các tác vụ này trong trình duyệt sẽ làm tăng chi phí khi chạy, ngữ nghĩa bộ nhớ đệm không nhất quán và tính không thể đoán trước về thời điểm/vị trí diễn ra quá trình chuyển đổi (thời gian biên dịch so với thời gian máy khách).
    - SCSS còn cho phép nhập tệp, tải về mạng và các hàm/plugin do người dùng định nghĩa. Việc thực thi logic tiền xử lý tùy ý trong trình duyệt sẽ làm tăng khả năng bị tấn công và làm phức tạp việc bảo mật về sanbox và quyền riêng tư.

Nguồn tham chiếu: https://www.quora.com/Why-dont-browsers-support-SASS-LESS-natively

- Để chuyển từ SASS/SCSS sang CSS, ta cần phải cài đặt trình biên dịch sass (Dart Sass) sang css
- Sau đó, tạo một file pakage.json để khởi chạy dự án thông npm.
- Trong file pakage.json, ta thêm dòng "start": "sass src/scss:public"

Nguồn tham chiếu: https://viblo.asia/p/sassscss-huong-dan-setup-cho-nguoi-moi-bat-dau-PAoJe6d1L1j

# PHẦN B:
## Bài B3
--------------------
Watching...
--------------------
Change detected - 5/10/2026, 4:06:18 PM
_component.scss
--------------------
Generated:
d:\Coding\CSE391_LeVietAnh_2451170859\Phieu_Bai_Tap\PBT_05\scss\style.css.map
d:\Coding\CSE391_LeVietAnh_2451170859\Phieu_Bai_Tap\PBT_05\scss\style.css

# PHẦN C:
## Bài C1
- Ở bản mobile:
    - thanh sidebar được thu gọn vào thành hamburger
    - để thực hiện hao tác tìm kiếm thì phải ấn vào biểu tượng "tìm kiếm"
    - nội dung được thu gọn thành một cột để hiển thị video dài và hai cột để hiển thị video ngắn

- Ở bản tablet:
    - thanh sidebar được thêm vào
    - thêm thanh tìm kiếm trên header để có thể trực tiếp tìm kiếm nội dung
    - thêm biểu tượng của tính năng tìm kiếm bằng giọng nói và thông báo
    - nội dung hiển thị tăng lên thành hai cột cho video dài và ba cột cho video ngắn
    - font không thay đổi

- Ở bản desktop:
    - phần lớn giống tablet
    - thanh sidebar được nới rộng ra để hiển thị thêm thông tin
    - nội dung hiển thị tăng lên thành 3 cột cho video dài và năm cột cho video ngắn