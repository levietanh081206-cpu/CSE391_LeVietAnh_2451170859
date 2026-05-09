# PHẦN A:
# Bài A1
|----------|---------------------------|---------------------------|--------------------|----------------|
| Position |  Vẫn chiếm chỗ trong flow |    Tham chiếu vị trí      |  Cuốn theo trang   | Use case       |
|----------|---------------------------|---------------------------|--------------------|----------------|
|  static  | Đúng vậy                  | Mặc định, nằm theo flow   |        Có          | Mặc định, không|
|          |                           | bình thường               |                    | cần viết       |
| relative | Đúng vậy                  | Dịch chuyển một khoảng    |        Có          | Làm anchor cho |
|          |                           | so với gốc                |                    | absolute con,  |
|          |                           |                           |                    | dịch nhẹ       |
| absolute | Bay khỏi flow             | Bám vào relative gần nhất |        Có          | Badge,dropdown,|
|          |                           |                           |                    | tooltip,overlay|
|  fixed   | Không                     | Bám vào VIEWPORT          |       Không        | Chat button,   |
|          |                           |                           |                    | cookie banner, |
|          |                           |                           |                    | header cố định |
|  sticky  | Đúng vậy                  | Mặc định, nằm theo flow   |    Đến khi chạm    | Sticky header, |
|          |                           |                           |       ngưỡng       | sticky table   |
|          |                           |                           |                    | header,sidebar |
|----------|---------------------------|---------------------------|--------------------|----------------|

- Absolute sẽ tham chiếu tới body khi phần tử đó không nằm trong bất kỳ thẻ nào khác, tương đương với việc không là con của phần tử nào khác.
- Absolute sẽ tham chiếu tới parent nếu nó có parent.
- "Nearest positioned ancestor" có lẽ là để chỉ thẻ parent trực tiếp của phần tử đấy, tức là phần tử ấy nằm ngay trong phần tử cha (parent ấy) chứ không quan tâm tới tất cả những thẻ khác mà cha nằm trong.

# PHẦN C
# Bài C1
- trường hợp 1 dùng flexbox vì layout của Navigation bar ngang là một layout theo chiều ngang nên cần co giãn linh hoạt cho phù hợp.
- trường hợp 2 dùng grid vì yêu cầu đó là 3 cột đều nhau.
- trường hợp 3 cần dùng kết hợp cả hai vì phải có grid để phân chia ranh giới cố định giữa sidebar và main, đồng thời phải có flexbox để có thể căn chỉnh nội dung bên trong main.
- trường hợp 4 cần grid vì yêu cầu là bốn cột thông tin, để cho cả bốn được phân loại đúng và tường minh thì nên dùng grid
- trường hợp 5 nên dùng flexbox vì dễ dàng căn chỉnh vị trí để style card, grid có phần hơi cứng nhắc và làm cho việc style card vừa khó vừa không đẹp

# Bài C2

- Lỗi 1: Cards không đều chiều cao — nút "Mua" bị nhảy lên/xuống
    .card-container { display: flex; flex-wrap: wrap; }
    .card { width: 30%; margin: 1.5%; }
    .card img { width: 100%; }
    .card h3 { font-size: 18px; }
    .card .btn { padding: 10px; }

--> Do tất cả các card đều là flexbox, tức là chúng điều chỉnh kích thước theo nội dung, vì vậy chúng không thể đều nhau do có thể có kích thước khác nhau. Mặt khác, do nút Mua nằm ngay dưới text nên khi nội dung text lệch nhau thì vị trí của nút mua cũng nhảy khác nhau.

- Lỗi 2: Muốn items nằm giữa cả ngang lẫn dọc trong container 100vh, nhưng item vẫn dính góc trái trên
    .hero {
        height: 100vh;
        display: flex;
    }
    .hero-content {
        text-align: center;
    }

--> Có lẽ là do hero-content nằm trong hero, vì vậy nên khi dùng "text-align: center" thì chỉ căn chỉnh vị trí bên trong hero-content mà thôi. Để căn chỉnh cho item nằm giữa trong container thì ta phại thêm vào class hero cả "text-align: center" để căn giữa theo trục dọc và "justify-content: center" để căn giữa theo trục ngang.

- Lỗi 3: Sidebar bị co lại khi content quá dài
    .layout { display: flex; }
    .sidebar { width: 250px; }
    .content { flex: 1; }

--> Lỗi này xả ra là bởi flexbox cho phép các box co lại để chen vào cho đủ chỗ, trong trường hợp này là do content quá lớn nên sidebar phải bị thu nhỏ lại để vừa với content. Để khắc phục việc này ta chỉ cần tắt ko cho sidebar co lại nữa bằng việc chỉnh thuộc tính "flex-shrink: 0"

