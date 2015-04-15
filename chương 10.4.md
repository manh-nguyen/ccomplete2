#10.4 Phạm vi biến
"Phạm vi biến" là cách nói về sự tổ chức của biến: nó phổ biến như thế nào ? Phạm vi, hay tầm nhìn đều ám chỉ quy mô mà biến được biết đến và có thể được nhắc đến thông qua chương trình. Biến cục bộ chỉ được biết đến trong một phần của chương trình- vòng lặp hay các vòng lặp nhỏ và những trường hợp đặc biệt. Biến toàn cục có thể sử dụng được nhiều nơi trong chương trình- ví dụ như một bảng thông tin nhân viên được sử dụng xuyên suốt chương trình, hoặc những trường hợp đặc biệt.

Các ngôn ngữ khác nhau xử lí phạm vi biến theo nhiều cách khác nhau. Ở vài ngôn ngữ nguyên thủy, tất cả các biến đều là toàn cục. Bạn không thể kiểm soát các phạm vi của biến và điều đó tạo nên nhiều vấn đề. Ở C++ các ngôn ngữ tương tự, biến có thể được gọi dù trong ngoặc ( một đoạn code được đóng bởi ngoặc đơn), hoặc một phần code, class ( và có thể lấy được từ nhiều classes ), hoặc cả chương trình. Trong Java và C#, biến có thể được gọi từ package hay namespace ( tính đóng gói của classes).

Phần tiếp theo sẽ hướng dẫn sử dụng phạm vi biến.

##Hướng dẫn sử dụng biến cục bộ

**Đoạn code được nhắc đến về biến là"window of vulnerability"- cơ hội tấn công cái gì đó trong tình trạng nguy hiểm.** Trong cửa sổ, code mới có thể được thêm vào, khi đó bạn có thể quên khai báo biến hoặc ai đó đọc code có thể quên giá trị của biến được gán. Cách tốt nhất là xác địch ví trí của biến được nhắc đến bằng cách giữ vị trí của biến gần nhau.
> nên dịch window of vulnerability như thế nào 


Ý tưởng vị trí của biến là một điều hiển nhiên, nhưng ý tưởng đó chỉ giúp về hình thức bên ngoài. Cách để sắp xếp các biến có thể gần nhau như thế nào là khoảng cách của biến trong máy tính. Đây là ví dụ:

``` Ví dụ 10-5. ví dụ về khoảng cách biến trong Java

a=0;

b=0;

c=0;

a= b + c;

```
Trong trường hợp này, 2 dòng ....

```
> không biết dịch chữ span


Ví dụ 10-6. ví dụ

> thiếu


###Tìm hiểu thêm

Để có thêm thông tin về sắp xếp biến, xem Software Engineering Metrics and Models ( conte, Dunsmore, and Shen 1986).

Khoảng cách trung bình được tính toán dựa trên khoảng cách cá nhân. Trong ví dụ 2, với b, (1+0)/2 bằng giá trị trung bình là 0.5. Khi mà bạn gọi các biến gần nhau, bạn có thể giúp người đọc code của bạn tập trung vào phần đó hơn.Nếu bạn gọi biến cách xa nhau, bạn sẽ bắt người đọc lục tung cả chương trình. Vì thế lợi ích chính của việc sắp xếp biến gần nhau là tăng khả năng đọc code rõ ràng và dễ hiểu hơn.

##Giữ cho biến " sống " trong thời gian ít nhất

Khái niệm liên quan đến phạm vi của biến còn được gọi là " thời gian tồn tại", tổng số dòng lệnh mà biến được sử dụng. Biến tồn tại từ dòng lệnh đầu tiên mà nó được gọi đến và nó kết thúc ở dòng lệnh cuối cùng mà nó được gọi đến.

Không giống như phạm vi biến, thời ian tồn tại của biến không ảnh hướng bơi bao nhiêu lần biến được sử dụng từ lần đầu tới lần cuối mà biến được gọi ra. Nếu biến được gọi lần đầu tiên ở dòng thứ nhất và lần cuối cùng ở dòng 25 thì nó sẽ tồn tại trong 25 dòng lệnh. Nếu chỉ có 2 dòng trong đó biến được sử dụng thì nó có phạm vi trung bình là 23 dòng lệnh. Nếu biến đã được dùng ở mỗi dòng từ dòng 1 đến 25, nó sẽ có phạm vi biến là 0 dòng lệnh ....

....

.....
> thiếu thiếu

##Tính toán thời gian tồn tại của biến

Bạn có thể hình thành khái niệm thời gian tồn tại của biến bằng cách đếm số dòng giữa lần đầu và lần cuối gọi biến ( bao gồm cả lần đầu và lần cuối). Đây là ví dụ về thời gian tồn tại biến quá dài

```
Ví dụ 10-7.

1 // khởi chạy mọi biến

2 recordIndex= 0;

3 total = 0;

4 done = false;

	...

26 while ( recordIndex < recordCount ) {

27 ...

28 recordIndex = recordIndex +1;    **<--1**

	...

64 while (!done) {

	...

69 if ( total > projectedTotal ) { 		**<--2**

70 	done=true;			**<--3**

(1) lần cuối gọi recordIndex.

(2) lần cuối gọi total.

(3) lần cuối gọi done.
```

Đây là thời gian tồn tại cho các biến trong ví dụ này:
----------
| recordIndex | ( line 28 - line 2 + 1 ) = 27 |
|-------|------|
| total | ( line 69 - line 3 + 1 ) = 67 |
|done | ( line 70 - line 4 + 1 ) = 67|
|Average Live Time | ( 27 + 67 + 67 ) / 3 ≈ 54|

Ví dụ trên được sửa lên bên dưới để nhận thấy biến có thể được gọi gần nhau hơn

```
Ví dụ 10-8. ví dụ về biến java với thời gian tồn tại ngắn

	...
25	recordIndex =0;		<--1
26



....

```


(1)
(2)

Đây là thời gian tồn tại của biến trong ví dụ:

>**chèn bảng**

Như đã thấy, ví dụ thứ 2 tốt hơn ví dụ thứ nhất bởi khởi tạo biến được biểu diễn gần nhau ở nơi biến được sử dụng. 

