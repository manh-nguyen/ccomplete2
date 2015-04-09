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

