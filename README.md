TextView là một View cho phép hiển thị text trên màn hình. TextView có thể tùy chỉnh cỡ chữ, font chữ, màu sắc,...

Khai báo 1 TextView

Trong xml:
```xml
<TextView

	android:id="@+id/text_view"
    android:layout_width="wrap_content"
    android:layout_height="wrap_content"
    android:text="ITMC Android Course" />
```

Lấy TextView từ layout bằng Java
```java
TextView tv = findViewById(R.id.text_view);
```

Một số thuộc tính của TextView

## 1, ID

ID dùng để phân biệt giữa các View với nhau
```xml
android:id="@+id/text_view"
```

2. Kích thước

`android:layout_width` thiết lập chiều rộng và
`android:layout_height` thiết lập chiều cao cho TextView

Giá trị gồm 3 loại:
 - `match_parent`: kích thước sẽ được mở rộng bằng với kích thước tối đa mà ViewGroup cha có thể chứa.
 - ```wrap_content```: kích thước vừa đủ để vừa với nội dung bên trong của TextView
 - giá trị cụ thể: vd `android:layout_width="100dp"`
 hoặc giá trị lấy từ dimens.xml

```xml
<resources>
    <dimen name="text_view_width">100dp</dimen>
</resources>
```
```xml
android:layout_width="@dimen/text_view_width"
```

3. Vị trí của chữ trong TextView
```android:gravity``` xác định vị trí tương đối của chữ trong TextView, giá trị có thể là `top`, `bottom`, `left`, `right`, `center`, ....

VD: 
```android:gravity="center"```
Hoặc các giá trị tương ứng có thể kết hợp với nhau:

VD: 
```android:gravity"bottom|right"```
![Gravity](https://github.com/VinhVIP/blog/blob/gh-pages/img/tv_gravity.png?raw=true)

4. Gán text cho TextView

`android:text="Xin chào!"`
hoặc lấy text từ resource được định nghĩa trong strings.xml
```xml
<resources>
    <string name="hello">Xin chào!</string>
</resources>
```

```android:text="@string/hello"```

5. Thiết lập màu chữ

```android:textColor="#ff0000"```
hoặc lấy mã màu từ resource được định nghĩa trong colors.xml
```xml
<resources>
    <color name="red">#ff0000</string>
</resources>
```

```android:textColor="@color/red"```

6. Thiết lập kiểu chữ

`android:textStyle` bao gồm 3 giá trị: `bold`, `italic`, `normal`
Các giá trị cũng có thể kết hợp với nhau, vd kiểu chữ đậm và in nghiêng:
```android:textStyle="bold|italic"```

7. Thiết lập cỡ chữ

`android:textSize` có thể nhận các giá trị theo đơn vị như sp, dp, px,...
```android:textSize="18sp"```


8. Thiết lập font chữ

`android:fonFamily` dùng để thiết lập font chữ hiển thị cho text, một số font có sẵn như: `sans-serif`, `monospace`, `casual`, `cursive`, ...

9. Link

Nội dung của TextView có thể là đường dẫn 1 trang web, địa chỉ email, số điện thoại,... TextView cho phép ta hiển thị các link đó nổi bật hơn bằng cách thêm đường kẻ chân.

`android:autoLink` thiết lập các kiểu giá trị nhận để highlight, bao gồm `web`, `phone`, `map`, `email`, `none`, `all`.

`android:linksClickable="true"` cho phép ta click vào đường dẫn link, mặc định giá trị là true.

`android:textColorLink` thiết lập màu sắc của đường dẫn, mặc định là màu colorAccent.

![link trong TextView](https://github.com/VinhVIP/blog/blob/gh-pages/img/tv_link.png?raw=true)

10. Drawable

TextView cho phép thiết lập nền là drawable, sử dụng các thuộc tính `android:drawableLeft`, `android:drawableRight`, `android:drawableTop`, `android:drawableBottom` để thiết lập drawable vào bên trái, phải, trên, dưới nội dung text của TextView
Drawable có thể tạo từ Vector Asset hoặc từ code xml sử dụng shape drawble.

VD: Tạo 1 hình chữ nhật 100x15 có màu hồng - `drawable/line.xml`

```xml
<?xml version="1.0" encoding="utf-8"?>
<shape xmlns:android="http://schemas.android.com/apk/res/android"
    android:shape="rectangle">
    <size android:height="15dp" android:width="100dp" />
    <solid android:color="#ff00ff" />
</shape>
``` 

```xml
android:drawableLeft="@drawable/ic_cloud"
android:drawableRight="@drawable/ic_cloud"
android:drawableTop="@drawable/line"
android:drawableBottom="@drawable/line"
android:drawablePadding="10dp"
```

`android:drawablePadding` dùng để thiết lập khoảng cách giữa drawable là nội dung text.

![Drawable](https://github.com/VinhVIP/blog/blob/gh-pages/img/tv_drawable.png?raw=true)

11. Màu nền

`android:background` dùng để thiết lập màu nền cho TextView, background có thể là mã màu hoặc drawable

VD: 
```android:background="#f0f0f0"```
hoặc: 
```android:background="@drawable/line"```

12. Margin

android:layout_margin dùng để thiết lập căn lề bên ngoài xung quanh của TextView, hoặc có thể thiết lập căn lề cho từng phía như `android:layout_marginLeft`, `android:layout_marginRight`, `android:layout_marginTop`, `android:layout_marginBottom`, 
`android:layout_marginVertical`, `android:layout_marginHorizontal`,...

VD: 
```android:layout_margin="10dp"```

13. Padding

`android:padding` dùng để thiết lập khoảng cách giữa viền biên ngoài của TextView với nội dung text bên trong của TextView, có thể thiết lập theo từng phía tương tự với margin

VD: 
```android:padding="10dp"```
