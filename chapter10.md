**Chương 10. Những vấn đề chung trong sử dụng biến**
====================================================

Trong xây dựng thì việc bạn muốn hoàn thiện tốt nhất mọi yêu cầu về kiến trúc là bình thường nhưng sẽ không hiệu quả nếu bạn vẽ một bản thiết kế chi tiết quá mức cần thiêt. Và chương này sẽ nói đến một vấn đề rất nền tảng: Các "ngóc ngách" trong việc sử dụng biến.


Những thông tin trong phần này đặt biệt có giá trị với bạn nếu bạn là một lập trình viên có kinh nghiệm. Rất dễ để bắt đầu những thói quen nguy hiểm này trước khi bạn thật sự nhận ra con đường của mình và sau đó sử dụng chúng như một thói quen ngay cả khi bạn đã học được cách để tránh chúng. Một lập trình viên kinh nghiệm có thể tìm các thảo luận về Binding Time  trong [Binding Time](Link/Binding_Time.md) và sử dụng mỗi biến cho một mục đích trong [Using Each Variable for Exactly One Purpose](Link/UsingEachVariableforExactlyOnePurpose.md) thật sự là rất thú vị. Nếu bạn không chắc lắm là mình có phải là "một lập trình viên có kinh nghiệm" hay không  thì bạn có thể xem "Bài kiểm tra kỹ năng về dữ liệu" ở phần sau và tìm ra câu trả lời cho mình.

Suốt chương này tôi sẽ dùng từ "biến" để đề cập đến các đối tượng cũng như các kiểu dữ liệu dựng sẵn như là integer và array. Cụm từ "kiểu dữ liệu" nói chung cũng được đề cập là các kiểu dữ liệu dựng sẵn, và từ "data" sẽ nhắc tới đối tượng hoặc kiểu dữ liệu dựng sẵn.

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
```c++
 Ví dụ 10-1. C++ Ví dụ về  Khởi tạo vào thời điểm khai báo
 float studentGrades[ MAX_STUDENTS ] = { 0.0 };
```
**Khởi tạo biến gần vị trí nó được dùng lần đầu tiên**. Một số ngôn ngữ (ví dụ Visual Basic) không hỗ trợ việc khởi tạo biến khi chúng được khởi tạo. Bạn có thể thực hiện theo coding style như sau,  khai báo nhóm thánh 1 nhóm, khởi tạo nhóm thành 1 nhóm như ví dụ bên dưới. Làm như vậy tất cả đều xa việc sử dụng đầu tiên của các biến.

**Tham khảo chéo**

*Kiểm tra các tham số truyền vào cũng là một cách để bảo vệ chương trình. Chi tiêt tại chương 8*

>Phần này trong tài liệu gốc có dẫn link tới chương 8

```c++
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
```
Một cách luyện tập tốt hơn nữa là khởi tạo biến thật gần với vị trí mà lần đầu tiên biến được sử dụng giống như ví dụ bên dưới.

```vb
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
```
(1) total được khai báo và khởi tạo gần với vị trí nó được sử dụng đầu tiên
(2) done cũng được khai báo và khởi tạo gần với vị trí nó được sử dụng đầu tiên



Ví dụ thứ hai là tối ưu trong nhiều trường hợp.Trong thời gian thực thi, với cách viết như ví dụ thứ nhất thì biến `done` sẽ dễ bị hiểu là code có sử dụng, tức là `done` đã được thay đổi trước đó. Nếu đó không phải là trường hợp mà bạn lần đầu tiên viết chương trình, thì sau đó với nhiều những sự thay đổi nó sẽ bị như vậy. Vấn đề khác với ví dụ thứ nhất đó là cái việc ném hết những dòng code có chức năng khởi tạo biến lại với nhau sẽ tạo ra ấn tượng rằng tất cả các biến sẽ được dùng trong suốt đoạn chương trình đó từ đầu đến cuối, trong khi không phải như vậy - ví dụ như biến `done` chỉ được sử dụng trong đoạn cuối. Cuôi cùng, như một chương trình đã bị thay đổi (như nó sẽ bị như vậy, nếu chỉ bằng quá trình Debugging (gỡ lỗi)), các vòng lặp có thể được dựng xung quanh các dòng code mà nó  sử dụng  biến  `done`, và biến `done` sẽ phải khởi tạo lại (reinitialized).Trong trường hợp đó, code mà viết theo ví dụ thứ hai có thể có một số yêu cầu một số sự thay đổi nhỏ, còn code viết theo cách thứ nhất thì thiên về việc sinh ra lỗi.

Trên đây là một ví dụ cho **Nguyên Tắc Tiệm Cận**: giữ những hành động có liên quan ở gần nhau. Ta có thể áp dụng nguyên tắc này để giữ những comment gần với code mà được chúng giải thích, hoặc là giữ sự thiết lập vòng lặp gần vòng lặp, nhóm các câu lệnh trong 1 dòng code, và còn rất nhiều trường hợp để áp dụng nguyên tắc này nữa.

**Tham khảo chéo**

*Chi tiết về Nguyên tắc tiệm cận xem thêm tại phần Phạm vi biến*
>Phần này có dẫn link đến chương 4

Thật là lý tưởng nếu như việc khai báo và định nghĩa mỗi biến gần nơi mà chúng lần đầu tiên sử dụng. Một sự khai báo có thể thiết lập được kiểu của biến. Một sự định nghĩa có thể gán biến một giá trị đặc biệt nào đó. Ở những ngôn ngữ mà hỗ trợ điều này, như là C++ hay là Java, các biến có thể được khai báo và định nghĩa gần với nơi mà lần đầu tiên chúng được dùng. Tất nhiên còn tốt hơn nữa nếu mỗi biến có thể được định nghĩa cũng thời điểm với lúc mà nó được khai báo:

```java
    Example 10-4. ví dụ Java có cách khởi tạo biến rất tuyệt

    int accountIndex = 0;
    // code đang sử dụng accountIndex
    ...

    double total = 0.0;       <-- 1
    // code đang sử dụng total
    ...

    boolean done = false;       <-- 2
    // code đang sử dụng done
    while ( ! done ) {
    ...
```
**Sử dụng `final` hoặc là `const` khi có thể**.Với những biến (hằng) mà được khai báo bằng `final` trong Java hoặc `const` trong C++, bạn có thể bảo vệ biến của bạn ngay từ khi bạn khởi tạo cho nó một giá trị nào đó. Từ khóa `final` và `const` rất có ích để định nghĩa hằng số của class, các tham số chỉ nhập vào (input-only), và bất kể những biến cục bộ nào mà bạn muốn chúng  không hề thay đổi sau khởi tạo.

**Tham khảo chéo**

*Chi tiết về việc giữ những hành động giống nhau lại gần nhau bạn có thể xem thêm tại Statements Whose Order Doesn't Matter*

>Phần này cũng có dẫn link đến một bài viết

Và hãy đặc biệt chú ý đến phần các biến đếm và các biến tích chữ. Những biến như là `i`, 	`j`, `k`,`sum` và `total` thường được sử dụng như các biến đếm, biến tích trữ. Lỗi cơ bản trong lập trình là việc quên mất không reset các biến đếm trước khi sử dụng chúng tiếp ở lần sau.

**Khởi tạo các dữ liệu thành viên của class trong constructor của nó**. Đơn giản như một biến trong đoạn chương trình có thể được khởi tạo trong mỗi đoạn chương trình, một dữ liệu của class có thể khởi tạo trong constructor của nó. Nếu bộ nhớ cấp phát trong constructor, nó có thể được thả tự do trong destructor .

**Kiểm tra lại xem có quên khởi tạo lại biến hay không**. Bạn hãy tự hỏi mình xem  biến có cần phải khởi tạo lại không, có thể bởi vì một vòng lặp trong đoạn chương trình phải dùng biến nhiều lần hoặc vì biến cần giữ giá trị của nó giữa các lời gọi  và cần được reset giữa các lần gọi. Nếu nó cần được khởi tạo lại, thì hãy chắc chắn rằng câu lệnh khởi tạo đó nằm trong phần code mà nó được nhắc lại.

**Khởi tạo named constants một lần duy nhất; khởi tạo các biến với mã thực thi** Nếu bạn đang dùng những biến mà nó giống named constants thì cũng không sao nếu viết code cho chúng khởi tạo một lần, ở đầu chương trình. Để làm điều này, khởi tạo chúng trong thủ tục Startup(). Khởi tạo các biến đúng trong mã thực thi được gần với nơi nó đã được sử dụng. Một trong những sự thay đổi chương trình phổ biến nhất đó là thay đổi đoạn chương trình đó lúc đầu chỉ dùng một lần thành dùng nhiều lần. Các biến đó được khởi tạo trong program-level (cấp độ chương trình) Startup(), sẽ không bị khởi tạo lại lần nữa trong suốt đoạn chương trình đó.
>Đoạn này dịch khá khó, nguyên văn tiếng anh:"Initialize named constants once; initialize variables with executable code. If you're using variables to emulate named constants, it's OK to write code that initializes them once, at the beginning of the program. To do this, initialize them in a Startup() routine. Initialize true variables in executable code close to where they're used. One of the most common program modifications is to change a routine that was originally called once so that you call it multiple times. Variables that are initialized in a program-level Startup() routine aren't reinitialized the second time through the routine."

**Sử dụng cài đặt cho trình biên dịch để nó tự động khởi tạo tất cả các biến** (nếu trình biên dịch của bạn có hỗ trợ tính năng này). Tôi tin tưởng vào tính năng khá đặc biệt này, tuy nhiên có thể bạn sẽ gặp vấn đề khi mang code đó sang máy khác, compiler khác, nên hay chắc rằng tài liệu của bạn có ghi cái cài đặt trình biên dịch này.

**Hãy tận dụng lợi thế của các cảnh báo của trình biên dịch.** Nhiều trình biên dịch cảnh báo bạn rằng bạn quên khởi tạo biến.

**Kiểm tra lại các tham số truyền vào là hợp lệ.** Một cách khác để khởi tạo biến đó chính là kiểm tra tính hợp lệ của tham số truyền vào. Trước khi bạn gán giá trị truyền vào có bất kì cái gì, hãy chắc chắn rằng nó hợp lệ.

**Tham khảo chéo**

*Chi tiết về kiểm tra tham số truyền vào tham khảo Protecting Your Program from Invalid Inputs, và phần cuối của Chapter 8. *
>phần này có dẫn 2 link

**Sử dụng trình kiểm tra truy cập bộ nhớ để kiểm tra con trỏ bị lỗi**. Trong một số hệ điều hành, nó sẽ kiểm tra con trỏ tham chiếu không hợp lệ. Trong một số hệ điều hành khác, bạn sở hữu nó, bạn không phải sử hữu nó mãi, tuy nhiên, vì bạn có thể mua trình kiểm tra truy cập bộ nhớ (memory-access checkers) và nó sẽ kiểm tra các con trỏ cho bạn.
>Chỗ này dịch không ổn lắm, Use the compiler setting that automatically initializes all variables. If your compiler supports such an option, having the compiler set to automatically initialize all variables is an easy variation on the theme of relying on your compiler. Relying on specific compiler settings, however, can cause problems when you move the code to another machine and another compiler. Make sure you document your use of the compiler setting; assumptions that rely on specific compiler settings are hard to uncover otherwise.""

**Khởi tạo bộ nhớ làm việc khi bắt đầu chương trình**. Khởi tạo bộ nhớ làm việc cho một giá trị đã biết nó sẽ để lộ ra những vấn đề về khởi tạo. Ví dụ như sau:

- Bạn có thể sử dụng **một bộ nạp bộ nhớ thiết lập trước**(preprogram memory filler) với một giá trị tiên đoán được. Giá trị 0 là lựa chọn tốt cho một số mục đích  vì nó chắc chắn rằng những con trỏ chưa được khởi tạo sẽ chỏ đến bộ nhớ thấp (low memory), làm cho chúng dễ bị phát hiện ra hơn khi mà chúng được sử dụng. Với vi xử lí Intel, 0xCC là một giá trị khá tốt để sử dụng vì nó là một máy mã  cho một breakpoint interrupt; nếu bạn đang chạy code trong một debugger và cố gắng thi hành dữ liệu của bạn hơn là code của bạn, thì bạn sẽ ngập chìm trong breakpoint. Một ích lợi khác của giá trị 0xCC là nó rất dễ dàng nhận ra trong memory dump - và nó ít khi được sử dụng với lí do chính thống.
Ngoài ra, Brian Kernighan và Rob Pike cũng gợi ý sử dụng hằng số 0xDEADBEEF để nạp vào bộ nhớ (filler memory) để dễ nhận biết và sửa lỗi. (1999)
>Đoạn này cũng có chỗ không ổn

- Nếu bạn đang sử dụng filler memory ( là những hằng số giống 2 hằng số trên), bạn có thể hay đổi giá trị bạn sử dụng để nạp vào bộ nhớ nhiều lần. "Rung lắc" chương trình của bạn như vậy đôi lúc sẽ tìm ra được những vấn đề ẩn, mà nếu như môi trường nền không thay đổi, ta không thể phát hiện ra nó.

- Bạn có thể khởi tạo bộ nhớ làm việc vào thời điểm khởi động. Ngược lại mục đích có lợi cho việc sử dụng một preprogram memory filler để làm lộ ra  những sai sót, mục đích của kĩ thuật này là làm ẩn chúng. Bằng cách nạp bộ nhớ làm việc với những giá trị giống nhau trong mọi thời điểm, bạn bảo đảm được rằng chương trình của bạn sẽ không bị hỏng bởi những thay đổi trong bộ nhớ khi khởi động chương trình (startup memory).
