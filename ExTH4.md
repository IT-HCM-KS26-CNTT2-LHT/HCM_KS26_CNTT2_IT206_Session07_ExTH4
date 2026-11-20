# [Bài thực hành 4] Sử dụng Feynman Prompt để học kiến thức lập trình

## 1. Prompt hoàn chỉnh (CREATE)

```
[C – Context]
Tôi là sinh viên CNTT năm nhất, vừa học xong OOP trong Java (Class, Object,
Attribute, Method, Constructor). Tôi nhớ định nghĩa nhưng chưa chắc đã hiểu.

[R – Request]
Làm gia sư kiểm tra mức độ hiểu OOP của tôi.

[E – Explanation]
- Không giải thích toàn bộ kiến thức từ đầu.
- Chỉ hỏi MỘT câu mỗi lượt.
- Sau mỗi câu trả lời: đánh giá và chỉ ra điểm chưa chính xác.
- Nếu tôi sai: không đưa đáp án, đưa ví dụ đời thường rồi yêu cầu tôi giải thích lại bằng ngôn ngữ đơn giản.
- Tối thiểu 5 câu hỏi.

[A – Action]
1. Hỏi Class, yêu cầu tôi giải thích bằng lời của mình.
2. Đánh giá. Nếu chưa hiểu: ví dụ thực tế, tôi giải thích lại.
3. Làm tương tự với Object, Attribute, Method, Constructor.
4. Cuối buổi: tổng kết phần đã hiểu và chưa hiểu.

[T – Tone]
Thân thiện, kiên nhẫn, tiếng Việt đơn giản.

[E – Extras]
Dùng ví dụ Java. Cuối buổi xuất bảng: Khái niệm | Mức độ hiểu | Cần ôn.
Bắt đầu bằng câu hỏi về Class.
```

## 2. Bản ghi hội thoại (mẫu, khi nộp hãy tự chạy và chụp màn hình)

| Câu | AI hỏi | SV trả lời | AI đánh giá |
|---|---|---|---|
| 1 | Class là gì? | "Là khuôn mẫu tạo ra các thứ giống nhau." | Hiểu một phần: chưa nói khuôn mẫu chứa gì. Hãy nghĩ đến bản vẽ nhà, em giải thích lại. |
| | | "Class mô tả thông tin và hành động chung, như bản vẽ ghi số phòng, màu sơn." | Hiểu tốt. |
| 2 | Object khác Class thế nào? | "Object giống Class." | Chưa hiểu: bản vẽ và ngôi nhà, cái nào ở được? Em giải thích lại. |
| | | "Class là bản vẽ, Object là ngôi nhà xây từ đó. Một Class tạo nhiều Object." | Hiểu tốt. |
| 3 | Attribute là gì? | "Là đặc điểm của đối tượng, như `name`, `age`." | Hiểu tốt. |
| 4 | Method là gì? | "Là hành động như `study()`." | Hiểu tốt. Bổ sung: method thường dùng attribute của object. |
| 5 | Constructor là gì? | "Là hàm tạo object, chạy khi gọi `new`." | Hiểu một phần: chưa nói nó làm gì. Ví dụ: điện thoại mới được cài sẵn tên máy. Em giải thích lại. |
| | | "Nó gán giá trị ban đầu cho attribute." | Hiểu tốt. |

**Tổng kết:** Em nắm tốt Attribute, Method. Class, Object, Constructor cần ôn thêm sự khác nhau giữa Class và Object.

## 3. Bảng đánh giá mức độ hiểu

| Khái niệm | Lần đầu | Sau khi giải thích lại | Cần ôn |
|---|---|---|---|
| Class | Một phần | Tốt | Class chứa attribute và method |
| Object | Chưa hiểu | Tốt | Phân biệt với Class |
| Attribute | Tốt | Tốt | Không |
| Method | Tốt | Tốt | Method dùng attribute |
| Constructor | Một phần | Tốt | Gán giá trị ban đầu |

## 4. Ví dụ Class và Object

```java
class Student {
    String name;                       // attribute
    Student(String name) {             // constructor
        this.name = name;
    }
    void study() {                     // method
        System.out.println(name + " đang học");
    }
}

Student a = new Student("An");         // object 1
Student b = new Student("Bình");       // object 2
```

Một Class `Student`, tạo được nhiều Object (An, Bình), mỗi Object có dữ liệu riêng.

## 5. Tự giải thích lại OOP

Class là bản vẽ mô tả một loại đối tượng. Object là sản phẩm thật tạo từ bản vẽ đó, một Class tạo được nhiều Object. Attribute là đặc điểm (tên, tuổi). Method là việc đối tượng làm được (học, chạy). Constructor chạy khi dùng `new` để gán giá trị ban đầu cho attribute.