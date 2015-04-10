**Chương 10. Những vấn đề chung trong sử dụng biến**
====================================================

Trong xây dựng thì việc bạn muốn hoàn thiện tốt nhất mọi yêu cầu về kiến trúc là bình thường nhưng sẽ không hiệu quả nếu bạn vẽ một bản thiết kế chi tiết quá mức cần thiêt. Và chương này sẽ nói đến một vấn đề rất nền tảng: Các "ngóc ngách" trong việc sử dụng biến.


***Những thông tin trong chương này đặc biệt có giá trị với bạn nếu bạn là một lập trình viên có kinh nghiệm. Thật là dễ dàng để bắt đầu sử dụng những sự tập luyện mạo hiểm trước khi bạn nhận ra đầy đủ những sự lựa chọn và rồi sử dụng chúng ngoài thói quen của bạn ngay cả khi bạn đã biết cách để tránh chúng. Một lập trình viên kinh nghiệm có thể tìm các thảo luận về Binding Time trong Binding Time và sử dụng mỗi biến cho một mục đích trong Using Each Variable for Exactly One Purpose  thật sự là rất thú vị. Nếu bạn không chắc lắm là mình có phải là "một lập trình viên có kinh nghiệm" hay không  thì bạn có thể xem "Bài kiểm tra kỹ năng về dữ liệu" ở phần sau và tìm ra câu trả lời cho mình.***

> Đoạn trên mình không hiểu ý tác giả nên dịch không rõ lắm, biên tập sửa giúp mình với nhé. Nguyên văn tiếng anh:"The information in this chapter should be particularly valuable to you if you're an experienced programmer. It's easy to start using hazardous practices before you're fully aware of your alternatives and then to continue to use them out of habit even after you've learned ways to avoid them. An experienced programmer might find the discussions on binding time in Binding Time and on using each variable for one purpose in Using Each Variable for Exactly One Purpose particularly interesting. If you're not sure whether you qualify as an "experienced programmer," take the "Data Literacy Test" in the next section and find out."

> Theo như tài liệu của mình  cụm "Binding Time" với " Using Each Variable for Exactly One Purpose" có dẫn link đến 2 bài viết ngắn.

**10.1.Kĩ năng về dữ liệu (Data Literacy)**
-----------------

Bước đầu tiên để tạo dữ liệu một cách hiệu quả là phải biết loại dữ liệu nào sẽ được tạo ra. Sự am hiểu về kiểu dữ liệu là phần rất quan trọng trong chiếc hộp đồ nghề của một lập trình viên. Tất nhiên, một bài hướng dẫn về kiểu dữ liệu nằm ngoài phạm vi của cuốn sách này, nhưng "Bài kiểm tra kĩ năng về dữ liệu" (Data Literacy Test) sẽ giúp bạn nhận ra bạn cần học thêm về chúng bao nhiêu nữa.



**Và đây là bài Kiểm tra kĩ năng về dữ liệu (Data Literacy Test)**
---------------------------------------------
Bạn ghi điểm 1 vào cạnh cụm từ mà bạn thấy là quá quen thuộc, còn nếu bạn nghĩ bạn biết nghĩa cụm từ đó nhưng mà bạn vẫn không chắc chắn lắm, thì hãy ghi điểm 0.5. Bạn cộng số điểm lại và bạn sẽ hiểu được ý nghĩa số điểm đó dựa theo bảng dưới.
______abstract data type ( Kiểu dữ liệu trừu tượng)
______literal (Giá trị hằng)
______array (mảng)
______local variable (Biến cục bộ)
______bitmap
______lookup table
______boolean variable
______member data
______B-tree
______pointer (Con trỏ)
______character variable
______private
______container class (Lớp chứa)
______retroactive synapse
______double precision (Dấu phẩy động độ chính xác kép)
______referential integrity (Toàn vẹn tham chiếu)
______elongated stream
______stack (Ngăn xếp)
______enumerated type (Liệt kê)
______string (Chuỗi)
______floating point (dấu chấm động)
______structured variable
______heap
______tree
______index
______typedef
______integer
______union
______linked list
______value chain
______named constant
______variant(kiểu dữ liệu đa năng)
**______Tổng điểm**


Và đây là bảng để bạn xem ý nghĩa số điểm của mình:
-----------------
|Điểm|Ý nghĩa|
|---------|--------|
|0-14| Bạn đang bắt đầu trở thành một lập trình viên (Beginning), có thể bạn đang trong năm đầu tiên của môn khoa học máy tính trong trường hoặc bạn đang tự học một ngôn ngữ đầu tiên. Bạn có thể học thêm nhiều nữa bằng cách đọc một trong số những quyển sách được liệt kê ở phần phụ ở dưới. Nhiều diễn tả về kĩ thuật trong phần này của cuốn sách hướng tới những lập trình viên vào loại Advanced (loại trên Beginning), và bạn sẽ hiểu được nhiều từ chúng hơn sau khi bạn đọc ít nhất một quyển trong những quyển sách kia.|
|15-19    |Bạn là một lập trình viên vào loại trung bình hoặc một lập trình viên có kinh nghiệm nhưng mà lại đã quên mất khá nhiều. Dù nhiều khái niệm có thể khá quen thuộc với bạn nhưng cũng rất có ích cho bạn nếu bạn đọc những quyển sách được liệt kê ở dưới.|
|20-24|Bạn là một lập trình viên thuộc loại expert rồi đấy. Không chừng bạn đã có những cuốn sách ở list dưới đây trên giá sách ấy chứ.|
|25-29|Bạn biết nhiều về các kiểu dữ liệu hơn cả tôi luôn. Bạn hãy cân nhắc viết một cuốn sách về vi tính cho mình đi. (và nhớ gửi tôi một bản copy nhé) |
|30-32|Haha cái đồ khoa trương. Những thuật ngữ "elongated stream," "retroactive synapse," và "value chain" không hề được nhắc tới là những kiễu dữ liệu - chính tôi tạo ra chúng đấy. Hãy đọc phần ***"thành thật trong tri thức"*** ở chương 33 nhé! |

   

>"thành thật trong tri thức" là mình dịch từ tên của phần Intellectual Honesty chương 33, để cho đồng bộ thì bạn dịch chương 33 thì chú ý chỗ này nhé.

**Tài liệu bổ sung cho Các kiểu dữ liệu**
-----------------------------------------

Những cuốn sách này là nguồn thông tin rất tốt về các kiểu dữ liệu:

Cormen, H. Thomas, Charles E. Leiserson, Ronald L. Rivest. Introduction to Algorithms. New York, NY: McGraw Hill. 1990.

Sedgewick, Robert. Algorithms in C++, Parts I-IV, 3d ed. Boston, MA: Addison-Wesley, 1998.

Sedgewick, Robert. Algorithms in C++, Part V, 3d ed. Boston, MA: Addison-Wesley, 2002.

**10.2.Making Variable Declarations Easy**
-------------------------------------
Phần này sẽ nói về cách sắp xếp khai báo các biến. Hẳn là đây là một công việc không quá phức tạp, và bạn có thể nghĩ rằng nó quá là vặt vãnh, không đáng để dành hẳn một mục trong cuốn sách này. Tuy nhiên, bạn dành nhiều thời gian để  khai báo biến, và phát triển những thói quen tốt thì bạn có thể tiết kiệm được thời gian và cả sự bực dọc trong suốt vòng đời dự án.

***Tham khảo chéo***

*Chi tiết về việc bố trí khai báo biến bạn có thể tham khảo "Laying Out Data Declarations" trong " Laying Out Individual Statements", Commenting Data Declarations" trong "Commenting Techniques"*
 

> Phần này trong bản gốc có dẫn link đến những quyển sách/bài viết đó.

**Implicit Declarations (Khai báo ẩn)**
---------------
Một số ngôn ngữ có hỗ trợ khai báo ẩn. Ví dụ, nếu bạn sử dụng một biến trong Microsoft Visual Basic mà không khai báo nó, thì compiler (trình biên dịch) sẽ tự động khai báo cho bạn ( tất nhiên là phụ thuộc cả vào cài đặt của compiler).

Khai báo ẩn là một trong những tính năng nguy hiểm nhất trong bất kì ngôn ngữ nào. Nếu bạn lập trình trong Visual Basic, thì bạn sẽ thấy khó chịu khi cố hình dung ra sao *acctNo* lại không có giá trị đúng và rồi nhận ra rằng *acctNum* bị khởi tạo lại về 0. Những nhầm lẫn kiểu như vậy rất dễ gặp phải khi ngôn ngữ của bạn không bắt buộc phải khai báo biến.

 **KEY POINT**
--------------

Nếu bạn đang lập trình với một ngôn ngữ yêu cầu bạn phải khai báo biến thì bạn sẽ phải gặp 2 sai lầm trước khi mà chương trính nó "cắn" bạn . Đầu tiên, bạn phải đặt cả acctNum và acctNo vào trong thân của đoạn chương trình. Rồi bạn phải khai báo cả hai biến đó vào trong đoạn chương trình đó.
>Đoạn này không rõ ý tác giả, nguyên văn là:"If you're programming in a language that requires you to declare variables, you have to make two mistakes before your program will bite you. First you have to put both acctNum and acctNo into the body of the routine. Then you have to declare both variables in the routine"


Thế này thì khá khó để bạn gặp sai lầm, và nó sẽ loại bỏ hầu hết những vấn đề về biến đồng nghĩa ( synonymous-variables). Những ngôn ngữ yêu cầu bạn khai báo dữ liệu thật rõ ràng, thực chất là nó yêu cầu bạn cẩn thận hơn trong việc sử dụng dữ liệu, đó chính là tác dụng lớn nhất của chúng. Thế giờ tôi phải làm gì khi ngôn ngữ đó hỗ trợ khai báo ẩn? Đây là một số gợi ý cho bạn:

**Tắt khai báo ẩn**. Một số trình biên dịch cho phép tắt khai báo ẩn.  Ví dụ, trong Visual Basic bạn có thể dùng câu lệnh *Option Explicit*, câu đó sẽ bắt bạn phải khai báo toàn bộ các biến trước khi bạn sử dụng chúng.

**Khai báo  tất cả các biến**. Khi bạn gõ một biến mới, hay khai báo nó, dù cho compiler không yêu cầu, điều này có thể không giúp bạn bắt được tất cả các lỗi nhưng nó có thể bắt được một trong số chúng.

**Sử dụng quy ước đặt tên**. Thiết lập một quy ước đặt tên cho những hậu tố chính (suffixes) như là Option Explicit và No để bạn không sử dụng 2 biến khi bạn chỉ muốn dùng có một.
>Đoạn này không ổn lắm

***Tham khảo chéo***

*Chi tiết về việc chuẩn hóa viết tắt, xem "General Abbreviation Guidelines" trong Creating Short Names That Are Readable.*
>Phần này trong bản gốc có dẫn link đến các bài viết

Kiểm tra lại tên biến. Sử dụng những gợi ý mà compiler hoặc trình tiện ích nào đó tạo ra. Nhiều compiler có thể liệt kê tất cả các biến trong chương trình, cho phép bạn nhận ra cả acctNum và acctNo. Chúng cũng chỉ ra những biến bạn khai báo nhưng lại không dùng.

**10.3.Hướng dẫn khởi tạo biến**
================================

**KEYPOINT**
------------

Khai báo dữ liệu không tốt là một trong những lí do gây lỗi lớn nhất trong lập trình. Phát triển các kĩ năng tránh những vấn đề về khởi tạo biến có thể tiết kiệm rất nhiều thời gian sửa lỗi.

Lỗi khi khởi tạo biến có thể đến từ một biến có giá trị ban đầu mà bạn không mong muốn nó có. Dưới đây là một số khả năng:

 

 - Biến từ đầu đã chưa hề được gán giá trị. Giá trị của nó có thể là bất kì giá trị nào trong bộ nhớ từ khi khởi động chương trình.

**Tham khảo chéo**
*Test sơ bộ dựa trên sự khai báo biến và sử dụng các mẫu có sẵn, hãy xem "Data-Flow Testing" trong Bag of Testing Tricks.*
>Phần này trong tài liệu gốc có dẫn link tới các bài viết

 - Giá trị của biến lỗi thời. Biến đã được gán một giá trị tại một số thời điểm, nhưng giá trị đó không còn hợp lệ nữa.

 - Một phần của biến được gán giá trị còn một phần thì không
 
Trường hợp cuối này thường có một số biến thể. Bạn có thể khai báo một số thành viên trong đối tượng nhưng không phải tất cả chúng. Bạn có thể quên mất không chỉ định bộ nhớ và rồi khởi tạo "biến" con trỏ chưa được khởi tạo. Nghĩa là bạn thực sự chọn một cách ngẫu nhiên  một phần của bộ nhớ máy tính và gán chúng một số giá trị. Nó có thể là bộ nhớ chứa dữ liệu. Nó có thể là bộ nhớ chứa code. Nó có thể là bộ nhớ chứa hệ điều hành. Triệu chứng của những vấn đề về con trỏ thay đổi theo thời gian nên lỗi về con trỏ khó sửa hơn bất kì lỗi nào khác.

Sau đây sẽ là hướng dẫn để tránh các vấn đề về khởi tạo:

**Khởi tạo mỗi biến khi nó đã được khai báo.** Đây là một hình thức không hề tốn kém để bảo vệ cho chương trình.  Nó là một chính sách bảo hiểm rất tốt cho những lỗi khởi tạo. Ví dụ dưới đây đảm bảo rằng `studentGrades` sẽ bị khởi tạo lại một thời điểm bạn gọi đoạn chương trình chứa nó.

    Ví dụ 10-1. C++ Ví dụ về  Khởi tạo vào thời điểm khai báo
    float studentGrades[ MAX_STUDENTS ] = { 0.0 };
**Khởi tạo biến gần vị trí nó được dùng lần đầu tiên**. Một số ngôn ngữ (ví dụ Visual Basic) không hỗ trợ việc khởi tạo biến khi chúng được khởi tạo. Bạn có thể thực hiện theo coding style như sau,  khai báo nhóm thánh 1 nhóm, khởi tạo nhóm thành 1 nhóm như ví dụ bên dưới. Làm như vậy tất cả đều xa việc sử dụng đầu tiên của các biến.

**Tham khảo chéo** 
*Kiểm tra các tham số truyền vào cũng là một cách để bảo vệ chương trình. Chi tiêt tại chương 8*

>Phần này trong tài liệu gốc có dẫn link tới chương 8

     Example 10-2. 
    
    ' declare all variables
    Dim accountIndex As Integer
    Dim total As Double
    Dim done As Boolean
    
    ' initialize all variables
    accountIndex = 0
    total = 0.0
    done = False
    ...
    
    ' code using accountIndex
    ...
    
    ' code using total
    ...
    
    ' code using done
    While Not done
       ...

Một cách luyện tập tốt hơn nữa là khởi tạo biến thật gần với vị trí mà lần đầu tiên biến được sử dụng giống như ví dụ bên dưới.

    Example 10-3. Visual Basic Example of Good Initialization
    
    Dim accountIndex As Integer
    
    accountIndex = 0
    ' code using accountIndex
    ...
    
    Dim total As Double
    total = 0.0       <-- 1
    ' code using total
    ...
    
    Dim done As Boolean
    done = False       <-- 2
    ' code using done
    While Not done
    ...
    (1) total được khai báo và khởi tạo gần với vị trí nó được sử dụng đầu tiên
    (2) done cũng được khai báo và khởi tạo gần với vị trí nó được sử dụng đầu tiên

Ví dụ thứ hai là tối ưu trong một số trường hợp.