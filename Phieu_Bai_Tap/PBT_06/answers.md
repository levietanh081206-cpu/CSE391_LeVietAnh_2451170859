# PHẦN A:
## Câu A1:

|   kích thước   |     < 768px     | 768px - 991px |   ≥ 992px    |
|----------------|-----------------|---------------|--------------|
|   Kích thước   |        1        |       2       |      4       |
|   Box layout   |        4        |       4       |      4       |

- col-md-6 là class thuộc bootstrap trong đó style element thành cột chiếm 6 ô của class cha có row.
- không cần viết col-sm-12 là bởi vì khi viết col-12 thì mặc định ban đầu của nó sẽ được thiết lập là một elem chiếm 12 ô của class cha row, cho đến khi chạm được các thiết lập khác: "col-md-6 col-lg-3", việc thêm sm vào làm cho việc bị thừa

## Câu A2:
1. class "d-none d-md-block" sẽ khiến cho elem được thiết lập bình thường sẽ ẩn, cho đến khi web được truy cập vào bằng một thiết bị có kích cỡ từ medium (từ tablet đổ lên) thì sẽ được hiển thị dưới dạng block.

2. 5 spacing utilities (margin/padding) là:
    - mt-3 là class trong đó quy định margin top của elem mà thuộc class đó là 3rem
    - px-4 là class trong đó quy định padding chiều ngang của elem mà thuộc class đó là 4rem
    - mb-auto là class trong đó quy định margin bottom của elem mà thuộc class đó là tự động
    - my-50 là class trong đó quy định margin dọc của elem mà thuộc class đó là 50% box cha của nó
    - pb-75% là class trong đó quy định padding bottom của elem mà thuộc class đó là 75% box cha của nó

3. sự khác nhau giữa .container, .container-fluid, .container-md là:
    - .container thì kích thước ngang là max-width theo breakpoint, vị trí là center và padding
    - .container-fluid kích thức ngang chiếm trọn chiều ngang khung hình
    - .container-md thì Full width dưới md, có max-width từ md trở lên

