 
## Phần 1. Chiếc cốc nước: vì sao AI quên Lượt 1

Context Window của AI giống một chiếc cốc có dung lượng cố định, đo bằng token. Mỗi lượt chat là một lần rót nước vào cốc: câu hỏi của khách rót một chút, câu trả lời của AI rót thêm một chút, và AI trả lời dông dài thì mỗi lượt rót rất nhiều. Chat 40 lượt về rau củ mà AI cứ dài dòng là 32.000 token tích tụ dần, tới một lúc cốc đầy 100% thì nước mới tràn vào phải đẩy nước cũ tràn ra ngoài, và phần tràn ra trước luôn là phần rót sớm nhất, tức Lượt 1 chứa tên Trần Văn B với mã đơn #MTX-9988.


## Phần 2. Hai phương án  

- Thao tác người dùng: chia phiên theo chủ đề, xong chủ đề nào mở phiên mới thay vì nhồi 45 lượt vào một cốc; khi chuyển phần quan trọng như thông tin đơn hàng thì chốt lại thành một dòng ngắn tên, mã đơn, chi nhánh rồi dán lại vào cuối phiên, nước chốt mới sẽ đè lên chỗ cũ; đồng thời yêu cầu AI "trả lời ngắn gọn dưới 100 từ" để giảm tốc độ rót

- Thiết kế hệ thống: trước mỗi lượt mới, hệ thống tự tóm tắt phần hội thoại cũ thành bản ghi chốt tên khách, mã đơn, tình trạng rồi thay thế dữ liệu thô, giúp cốc luôn còn chỗ trống; hoặc trích xuất trước các thông tin bắt buộc lưu vào database rồi bơm lại vào đầu mỗi prompt kiểu "Khách hàng: XXX, đơn #MTX-9988" để thông tin này không bao giờ tràn; kèm cảnh báo tự động khi phiên đạt 80% dung lượng để mở phiên mới kịp lúc

 
