# -EdTech-Dropout-Prediction
Đồ án nhóm: Khai phá chuỗi hành vi học tập dự báo nguy cơ bỏ học

BẢNG TỪ ĐIỂN DỮ LIỆU (DATA DICTIONARY)
Dự án: Khai phá chuỗi hành vi học tập (OULAD) bằng SPADE & PrefixSpan
Phụ trách tiền xử lý: Data Engineer (Thành viên 1)
Tên file dữ liệu đầu ra: sequence_dataset_cleaned.csv

1. Cấu trúc tập dữ liệu
Tập dữ liệu đầu ra bao gồm các cột sau:

id_student: Mã định danh duy nhất của sinh viên.

sequence: Chuỗi sự kiện hành vi của sinh viên, được gom nhóm theo từng tuần học. Các hành vi trong cùng một tuần được đặt trong ngoặc nhọn {...}, các tuần nối tiếp nhau tạo thành chuỗi trong ngoặc nhọn <...> (Ví dụ: <{V_home}, {D_forum, V_quiz}>).

final_result: Nhãn phân loại trạng thái cuối cùng của sinh viên (Pass, Distinction, Fail, Withdrawn).

2. Quy ước mã hóa hành vi (Activity Encoding)
Các log tương tác thô đã được làm sạch và mã hóa thành các ký hiệu ngắn gọn để tối ưu hóa bộ nhớ khi chạy SPADE/PrefixSpan. Chi tiết mã hóa như sau:

<img width="543" height="661" alt="image" src="https://github.com/user-attachments/assets/45eb311a-e8ae-4775-b87b-2fbdd7d081a8" />

3. Quy tắc xử lý dữ liệu (Data Cleaning Rules)
Missing Values: Các lượt click không xác định được giữ nguyên hoặc điền giá trị mặc định, không xóa bỏ dòng dữ liệu để đảm bảo tính toàn vẹn của chuỗi.

Time-binning: Các mốc thời gian (cột date âm) diễn ra trước khi khóa học bắt đầu đều được quy về ngày 0 (tuần đầu tiên) để không làm đứt gãy chuỗi sự kiện.

Xong bước này là cậu có thể tự tin gói ghém file dữ liệu CSV kèm theo bảng mô tả này để bàn giao cho các đồng đội phụ trách thuật toán rồi! Cậu kiểm tra lại xem trong bài code của cậu có phát sinh thêm mã hành vi nào khác cần tớ bổ sung vào bảng này không?
