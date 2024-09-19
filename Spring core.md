### Câu hỏi: Làm sao để viết Functional Interface, Khi nào nó được dùng ?
- Câu trả lời: Functional Interface trong Java là một interface chỉ có một phương thức trừu tượng. Nó thường được sử dụng khi chúng ta muốn truyền một biểu thức lambda hoặc một reference đến một phương thức. Có thể khai báo bằng annotation `@FunctionalInterface`. Functional Interface thường được sử dụng trong các hàm xử lý sự kiện hoặc các tác vụ đơn giản trong các luồng xử lý song song.

### Câu hỏi: Lambda? Thường sử dụng Lambda khi nào ?
- Câu trả lời: Lambda Expression là một cách viết ngắn gọn giúp đơn giản hóa việc viết các lớp ẩn danh hoặc các interface đơn phương thức. Thường được dùng khi làm việc với các Functional Interface như Runnable, Callable, hoặc trong stream API để xử lý tập dữ liệu.

    ```Java
    // Ví dụ sử dụng Lambda với Runnable
    Runnable r = () -> System.out.println("Hello Lambda!");
    new Thread(r).start();
    ```
### Stream trong java là gì
- Stream là 1 API để xử lý dữ liệu tuân theo `phong cách lập trình hàm`. Stream không lưu trữ dữ liệu mà chỉ là một chuỗi các phép toán được thực thi trên một nguồn dữ liệu.Các phép toán trên Stream chỉ được thực thi khi bạn gọi một phép toán cuối cùng (terminal operation) như collect, forEach,...

- Stream giúp code ngắn gọn và rõ ràng, dồng thời cũng cung cấp các built-in function giúp dễ ràng hóa quá trình xử lý dữ liệu như filter, map, reduce....

- Stream không hỗ trợ thay đổi dữ liệu gốc


### Collection trong java

- `Là một cấu trúc dữ liệu`: Collection đại diện cho một tập hợp các đối tượng, có thể là các đối tượng đồng nhất hoặc không đồng nhất.
- `Lưu trữ và quản lý dữ liệu `: Collection được sử dụng để lưu trữ và quản lý dữ liệu trong suốt quá trình thực thi chương trình.
- Các loại Collection: List, Set, Map là những loại Collection phổ biến, mỗi loại có những đặc điểm và cách sử dụng riêng.
- `Thay đổi được`: Bạn có thể thêm, xóa, sửa đổi các phần tử trong một Collection.


### Câu hỏi: Sự khác nhau giữa Stream và Collection
- Câu trả lời: Stream là một API để xử lý dữ liệu tuần tự theo phong cách lập trình hàm, cho phép filter, map, reduce dữ liệu. Trong khi đó, Collection là các cấu trúc dữ liệu lưu trữ phần tử. Supplier cung cấp dữ liệu, Consumer tiêu thụ dữ liệu mà không trả lại kết quả, còn Predicate là biểu thức logic trả về giá trị boolean.

| **Tiêu chí**                   | **Stream**                                               | **Collection**                                          |
|---------------------------------|----------------------------------------------------------|---------------------------------------------------------|
| **Loại**                        | Được sử dụng để xử lý dữ liệu theo kiểu pipeline (luồng)  | Lưu trữ và quản lý các đối tượng trong bộ nhớ           |
| **Chế độ xử lý**                | Xử lý theo kiểu **lazily** (chỉ xử lý khi cần thiết)      | Xử lý dữ liệu **eagerly** (ngay khi thêm vào)           |
| **Chức năng**                   | Cung cấp các thao tác xử lý dữ liệu kiểu functional       | Chủ yếu để quản lý và thao tác dữ liệu (CRUD)            |
| **Tính thay đổi (Mutable)**     | Không hỗ trợ chỉnh sửa phần tử (immutable)                | Hỗ trợ thêm, xóa, sửa phần tử                           |
| **Kích thước**                  | Không lưu trữ dữ liệu, không có khái niệm kích thước      | Có kích thước rõ ràng (size)                            |
| **Nguồn dữ liệu**               | Có thể được tạo từ các nguồn khác nhau (Collection, I/O)  | Chỉ lưu trữ trong bộ nhớ                                |
| **Tính tuần tự hoặc song song** | Hỗ trợ xử lý tuần tự và song song với API song song       | Thường được xử lý tuần tự, không hỗ trợ song song       |
| **Hỗ trợ Iterator**             | Chỉ hỗ trợ iterator một lần (single-use)                  | Hỗ trợ iterator nhiều lần                               |
| **Tính kết thúc (Finite/Infinite)**| Có thể là luồng vô hạn (infinite stream)                | Luôn có kích thước hữu hạn (finite)                     |
| **Hoạt động**                   | Các phép biến đổi không thay đổi nguồn gốc                | Các phép biến đổi ảnh hưởng trực tiếp đến collection     |
| **Lazy Evaluation**             | Có, chỉ thực hiện khi cần                                  | Không, thực hiện ngay khi gọi                           |
| **Hỗ trợ lập trình song song**  | Có, với API đơn giản (`parallelStream()`)                 | Không hỗ trợ natively                                   |

### Câu hỏi: So sánh Array List và LinkedList ?

| **Tiêu chí**                        | **ArrayList**                                          | **LinkedList**                                          |
|-------------------------------------|--------------------------------------------------------|---------------------------------------------------------|
| **Cấu trúc dữ liệu**                | Dựa trên mảng động (dynamic array)                     | Dựa trên danh sách liên kết đôi (doubly linked list)     |
| **Truy cập phần tử (get/set)**      | Nhanh hơn vì có thể truy cập ngẫu nhiên (O(1))         | Chậm hơn, phải duyệt qua các node từ đầu (O(n))         |
| **Thêm/xóa ở giữa**                 | Chậm hơn do cần dịch chuyển các phần tử (O(n))          | Nhanh hơn vì chỉ cần thay đổi liên kết (O(1))            |
| **Thêm/xóa ở cuối**                 | Nhanh, O(1) khi không cần mở rộng kích thước mảng       | Nhanh, O(1) vì chỉ cần thay đổi liên kết                 |
| **Thêm/xóa ở đầu**                  | Chậm, O(n) do phải dịch chuyển các phần tử              | Nhanh, O(1) vì chỉ cần thay đổi liên kết                 |
| **Bộ nhớ sử dụng**                  | Ít tốn bộ nhớ hơn vì chỉ lưu trữ dữ liệu                | Tốn bộ nhớ hơn do cần lưu trữ cả liên kết giữa các node  |
| **Tính năng**                       | Tốt cho các thao tác truy xuất và thêm phần tử cuối     | Tốt cho các thao tác thêm/xóa ở đầu hoặc giữa danh sách  |
| **Thích hợp sử dụng**               | Khi cần truy cập ngẫu nhiên thường xuyên               | Khi cần thêm/xóa ở đầu, giữa hoặc cuối thường xuyên      |
| **Chi phí khi mở rộng**             | Khi vượt quá dung lượng, cần tạo mảng mới và copy dữ liệu | Không cần copy dữ liệu, chỉ cần tạo node mới            |
| **Duyệt (iteration)**               | Tốt với ListIterator và truy cập theo chỉ số (index)    | Chậm hơn khi duyệt qua vì không hỗ trợ truy cập chỉ số trực tiếp |

### Câu hỏi: So sánh List và Set ?

| **Tiêu chí**                    | **List**                                                | **Set**                                                 |
|----------------------------------|---------------------------------------------------------|---------------------------------------------------------|
| **Cấu trúc**                     | Cho phép lưu trữ các phần tử theo thứ tự                | Không đảm bảo thứ tự lưu trữ phần tử                    |
| **Phần tử trùng lặp**            | Cho phép phần tử trùng lặp                              | Không cho phép phần tử trùng lặp                        |
| **Truy cập theo chỉ số (index)** | Có thể truy cập phần tử thông qua chỉ số (index)        | Không hỗ trợ truy cập theo chỉ số                       |
| **Thứ tự phần tử**               | Duy trì thứ tự thêm vào                                 | Không duy trì thứ tự thêm vào (ngoại trừ `LinkedHashSet`)|
| **Hiệu suất tìm kiếm**           | Tìm kiếm chậm hơn vì phải duyệt qua toàn bộ danh sách (O(n)) | Tìm kiếm nhanh hơn, đặc biệt trong `HashSet` (O(1))      |
| **Thao tác thêm/xóa**            | Chậm hơn khi thêm/xóa phần tử giữa danh sách (O(n))     | Nhanh hơn khi thêm/xóa phần tử (O(1) cho `HashSet`)      |
| **Sử dụng**                      | Dùng khi cần lưu trữ các phần tử có thứ tự hoặc cần truy cập qua chỉ số | Dùng khi cần lưu trữ các phần tử duy nhất, không trùng lặp|
| **Triển khai phổ biến**          | `ArrayList`, `LinkedList`, `Vector`                     | `HashSet`, `LinkedHashSet`, `TreeSet`                   |


### Câu hỏi: So sánh Abstract class và Interface?
- Câu trả lời: Abstract class có thể chứa cả phương thức đã triển khai và chưa triển khai, còn Interface chỉ chứa các phương thức trừu tượng (trước Java 8). Kể từ Java 8, Interface có thể chứa các phương thức mặc định và phương thức tĩnh. Abstract class phù hợp khi các lớp con cần chia sẻ các phương thức hoặc trạng thái chung.

### Câu hỏi: Map, hashCode(), equals()
- Câu trả lời: Map là một cấu trúc dữ liệu lưu trữ các cặp key-value. Phương thức `hashCode()` được sử dụng để sinh ra mã băm cho đối tượng, trong khi `equals()` kiểm tra sự bằng nhau giữa hai đối tượng. Khi override `equals()`, cần phải override `hashCode()` để đảm bảo tính nhất quán khi dùng đối tượng đó trong các cấu trúc dữ liệu như HashMap.

### Câu hỏi: LifeCycle của Thread
- Câu trả lời: Thread có các trạng thái sau: New, Runnable, Blocked, Waiting, Timed Waiting, và Terminated. Chu kỳ này mô tả quá trình tạo, chạy và kết thúc của một luồng (Thread) trong Java.

    ```Java
    // Ví dụ tạo thread đơn giản
    Thread t = new Thread(() -> System.out.println("Thread running"));
    t.start();
    ```

### Câu hỏi: So sánh Comparable và Comparator
- Câu trả lời: Comparable được sử dụng để xác định thứ tự tự nhiên của các đối tượng bằng cách implement phương thức `compareTo()`. Comparator cho phép bạn định nghĩa nhiều cách so sánh khác nhau giữa các đối tượng bằng cách implement `compare()`. Sử dụng Comparator khi muốn sắp xếp đối tượng theo nhiều tiêu chí.

    ```Java
    class Person implements Comparable<Person> {
        int age;
        public int compareTo(Person p) { return this.age - p.age; }
    }
    ```

### Câu hỏi: Deadlock trong thread là gì, làm sao để ngăn chặn deadlock
- Câu trả lời: Deadlock xảy ra khi hai hay nhiều thread bị kẹt chờ lẫn nhau giữ khóa. Để ngăn chặn, có thể sử dụng các cơ chế như: sử dụng `tryLock()` với thời gian timeout, hoặc đảm bảo thứ tự khóa nhất quán.

### Câu hỏi: Mutex problem solving
- Câu trả lời: Mutex là cơ chế để đảm bảo chỉ một thread có thể truy cập tài nguyên chung tại một thời điểm. Để giải quyết vấn đề Mutex, sử dụng các kỹ thuật như synchronized block hoặc ReentrantLock trong Java.

### Câu hỏi: Thread pool trong Java?
- Câu trả lời: Thread pool là tập hợp các thread được quản lý sẵn, giúp thực thi các tác vụ mà không cần tạo thread mới mỗi khi có yêu cầu. Thread pool giúp tối ưu hiệu suất và quản lý số lượng luồng trong ứng dụng.

### Câu hỏi: String pool trong Java?
- Câu trả lời: String pool là tập hợp các chuỗi được lưu trữ và quản lý trong bộ nhớ heap. Khi tạo một chuỗi mới bằng cách khai báo trực tiếp, Java sẽ kiểm tra xem chuỗi đó có trong String pool hay chưa, nếu có, sẽ dùng lại thay vì tạo mới, giúp tiết kiệm bộ nhớ.

    ```Java
    String s1 = "Hello";
    String s2 = "Hello";  // s1 và s2 trỏ đến cùng một đối tượng trong String pool
    ```

### Câu hỏi: Nêu khái niệm Immutable và Mutable?
- Câu trả lời: Immutable (bất biến) là đối tượng không thể thay đổi sau khi đã được tạo ra, ví dụ như String trong Java. Mutable (có thể thay đổi) là các đối tượng có thể sửa đổi được sau khi khởi tạo, ví dụ như StringBuilder.

### Câu hỏi: Nêu hiểu biết về Heap và Stack?
- Câu trả lời: Heap là vùng nhớ được sử dụng để lưu trữ các đối tượng động (new), trong khi Stack là vùng nhớ dùng để lưu trữ các biến cục bộ và lời gọi hàm theo cơ chế LIFO (Last In, First Out). Stack có kích thước cố định, trong khi heap có thể thay đổi.

### Câu hỏi: OOP là gì? Các tính chất của OOP?
- Câu trả lời: OOP (Object-Oriented Programming) là lập trình hướng đối tượng, gồm 4 tính chất chính: Encapsulation (đóng gói), Inheritance (kế thừa), Polymorphism (đa hình), và Abstraction (trừu tượng hóa).

### Câu hỏi: Access modifier trong Java?
- Câu trả lời: Access modifier xác định phạm vi truy cập của các thành phần trong lớp. Các mức gồm: `public`, `protected`, `default` (gói) và `private`. `public` cho phép truy cập ở mọi nơi, `private` chỉ trong chính lớp đó, `protected` truy cập trong cùng package và các lớp con, trong khi `default` chỉ cho phép truy cập trong cùng package.

### Câu hỏi: Final, finally, finalize trong Java?
- `final` là từ khóa dùng để khai báo biến không thay đổi, phương thức không override, và lớp không kế thừa. 
- `finally` là khối mã luôn được thực thi sau try-catch, dùng để dọn dẹp tài nguyên. 
- `finalize()` là phương thức được gọi trước khi đối tượng bị garbage collector thu gom.

### Câu hỏi: Optional trong Java?
- Câu trả lời: Optional là một class giới thiệu trong Java 8, giúp tránh lỗi NullPointerException bằng cách bọc giá trị có thể null và cung cấp các phương thức để xử lý trường hợp giá trị có hoặc không tồn tại.

    ```Java
    Optional<String> name = Optional.ofNullable(null);
    name.ifPresent(System.out::println);  // không in ra gì vì giá trị null
    ```


### Giải thích về Generics trong Java

Generics là một tính năng trong Java cho phép các lớp, interface và phương thức hoạt động với các kiểu dữ liệu tham số hóa. Thay vì làm việc với các kiểu cụ thể, bạn có thể sử dụng các tham số kiểu để viết mã chung hơn và có tính linh hoạt cao hơn.

**Lợi ích của Generics:**
- **Type Safety**: Giúp phát hiện lỗi kiểu dữ liệu tại thời điểm biên dịch.
- **Code Reusability**: Tạo ra các lớp và phương thức có thể dùng lại cho nhiều kiểu dữ liệu khác nhau mà không cần viết lại mã.
- **Avoiding Type Casting**: Loại bỏ việc ép kiểu thủ công, vì kiểu dữ liệu đã được xác định trước tại compile time.

Ví dụ về Generics:

```Java
// Ví dụ về sử dụng Generics trong lớp
public class Box<T> {
    private T value;

    public void set(T value) {
        this.value = value;
    }

    public T get() {
        return value;
    }
}

```

### Tại sao lại sử dụng final?

Khi một lớp được đánh dấu là final, không lớp nào khác có thể kế thừa từ lớp đó. Điều này đảm bảo rằng lớp của bạn sẽ không bị thay đổi thông qua kế thừa và hành vi của nó sẽ được bảo toàn

- `Bảo vệ tính toàn vẹn của lớp`: Ngăn chặn việc các lớp con vô tình hoặc cố ý thay đổi hành vi của lớp cha.
- `Tăng hiệu suất`: Đôi khi, trình biên dịch có thể tối ưu hóa mã của các lớp `final` tốt hơn.
- `Làm rõ ý định thiết kế`: Cho biết rõ rằng lớp này không được thiết kế để làm lớp cơ sở cho các lớp khác.

### Phân biệt giữa Checked và Unchecked Exceptions.

| **Tiêu chí**                    | **Checked Exceptions**                                  | **Unchecked Exceptions**                                |
|----------------------------------|---------------------------------------------------------|---------------------------------------------------------|
| **Kiểm tra tại**                 | Được kiểm tra tại thời điểm biên dịch (compile-time)    | Được kiểm tra tại thời điểm runtime                     |
| **Lớp cha**                      | Kế thừa từ `java.lang.Exception` (ngoại trừ `RuntimeException`) | Kế thừa từ `java.lang.RuntimeException`                 |
| **Ví dụ**                        | `IOException`, `SQLException`, `FileNotFoundException`  | `NullPointerException`, `ArrayIndexOutOfBoundsException`, `ArithmeticException` |
| **Bắt buộc xử lý**               | Phải được xử lý hoặc khai báo trong phương thức với `throws` | Không bắt buộc phải xử lý hoặc khai báo                 |
| **Mục đích**                     | Dùng cho các lỗi có thể dự đoán và khắc phục được       | Dùng cho các lỗi lập trình, thường là lỗi không thể dự đoán hoặc khó khắc phục |
| **Xử lý**                        | Phải sử dụng `try-catch` hoặc khai báo `throws`         | Không yêu cầu bắt buộc sử dụng `try-catch`               |
| **Thời điểm phát sinh**          | Thường xảy ra do các điều kiện ngoại cảnh như tệp tin không tồn tại hoặc lỗi mạng | Thường xảy ra do các lỗi lập trình, chẳng hạn như chia cho 0 hoặc truy cập mảng ngoài giới hạn |

### Khi nào thì sử dụng extends và super trong Generics?

| **Tiêu chí**          | **`extends`**                                              | **`super`**                                               |
|-----------------------|-------------------------------------------------------------|------------------------------------------------------------|
| **Sử dụng khi**       | Để khai báo một kiểu giới hạn trên hoặc dưới một lớp hoặc interface  | Để khai báo một kiểu có thể là lớp cha của một lớp cụ thể |
| **Ký hiệu**           | `<? extends T>`: Giới hạn kiểu đối tượng là một lớp con của `T` hoặc là chính `T` | `<? super T>`: Giới hạn kiểu đối tượng là một lớp cha của `T` hoặc là chính `T` |
| **Đọc dữ liệu**       | Có thể đọc dữ liệu từ danh sách nhưng chỉ có thể đọc dữ liệu dưới dạng `T` hoặc `T` (tức là không biết chính xác kiểu dữ liệu) | Có thể đọc dữ liệu dưới dạng `Object` vì không biết chính xác kiểu dữ liệu  |
| **Ghi dữ liệu**       | Không thể ghi dữ liệu vào danh sách vì không biết chính xác kiểu dữ liệu | Có thể ghi dữ liệu vào danh sách (đặc biệt khi kiểu cụ thể là `T`) |
| **Ví dụ sử dụng**     | `List<? extends Number>`: Có thể chứa `Integer`, `Double`, v.v. nhưng không thể thêm bất kỳ giá trị nào vào danh sách này | `List<? super Integer>`: Có thể chứa `Integer` và các lớp cha của `Integer`, có thể thêm `Integer` vào danh sách này |


### Sự khác biệt giữa `List<Object>` và `List<?>` là gì? 

| **Tiêu chí**                       | **`List<Object>`**                                        | **`List<?>`**                                             |
|------------------------------------|---------------------------------------------------------|---------------------------------------------------------|
| **Khai báo**                       | `List<Object>`: Danh sách có thể chứa bất kỳ loại đối tượng nào | `List<?>`: Danh sách có thể chứa bất kỳ loại đối tượng nào, nhưng loại đối tượng cụ thể không được biết |
| **Thêm phần tử**                  | Có thể thêm bất kỳ loại đối tượng nào                  | Không thể thêm phần tử vào danh sách vì không biết kiểu đối tượng cụ thể |
| **Truy cập phần tử**              | Có thể truy cập và thao tác với các phần tử như `Object` | Có thể đọc các phần tử, nhưng không thể thực hiện thao tác cụ thể (phải cast về kiểu cụ thể) |
| **Lấy kiểu đối tượng**            | Có thể lấy kiểu đối tượng cụ thể từ `List<Object>`     | Không thể lấy kiểu đối tượng cụ thể từ `List<?>`     |
| **Sử dụng với Generics**           | Có thể sử dụng các phương thức generics với `List<Object>` | Thường dùng trong trường hợp generic wildcard (`List<?>`) để viết mã linh hoạt |
| **Khả năng mở rộng**               | Có thể mở rộng thành `List<String>`, `List<Integer>`, v.v. | Không thể mở rộng thành các kiểu cụ thể vì kiểu đối tượng không được biết |
| **Ví dụ sử dụng**                  | `List<Object> list = new ArrayList<>();`                | `List<?> list = new ArrayList<String>();`              |






