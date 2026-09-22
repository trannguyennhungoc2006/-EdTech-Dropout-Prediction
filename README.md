# -EdTech-Dropout-Prediction
Đồ án nhóm: Khai phá chuỗi hành vi học tập dự báo nguy cơ bỏ học

<h1>BẢNG TỪ ĐIỂN DỮ LIỆU (DATA DICTIONARY)</h1>
<h2>Phụ trách tiền xử lý: Data Engineer (Lê Hoàng Vy) - Tuần 01</h2>
Tên file dữ liệu đầu ra: sequence_dataset_cleaned.csv

<h3>1. Cấu trúc tập dữ liệu</h3>
Tập dữ liệu đầu ra bao gồm các cột sau:
<ul>
<li>id_student: Mã định danh duy nhất của sinh viên.</li>

<li>sequence: Chuỗi sự kiện hành vi của sinh viên, được gom nhóm theo từng tuần học. Các hành vi trong cùng một tuần được đặt trong ngoặc nhọn {...}, các tuần nối tiếp nhau tạo thành chuỗi trong ngoặc nhọn <...> (Ví dụ: <{V_home}, {D_forum, V_quiz}>).</li>

<li>final_result: Nhãn phân loại trạng thái cuối cùng của sinh viên (Pass, Distinction, Fail, Withdrawn).</li>
</ul>
<h3>2. Quy ước mã hóa hành vi (Activity Encoding)</h3>
Các log tương tác thô đã được làm sạch và mã hóa thành các ký hiệu ngắn gọn để tối ưu hóa bộ nhớ khi chạy SPADE/PrefixSpan. Chi tiết mã hóa như sau:

<img width="543" height="661" alt="image" src="https://github.com/user-attachments/assets/45eb311a-e8ae-4775-b87b-2fbdd7d081a8" />

<h3>3. Quy tắc xử lý dữ liệu (Data Cleaning Rules)</h3>
<ul>
<li>Missing Values: Các lượt click không xác định được giữ nguyên hoặc điền giá trị mặc định, không xóa bỏ dòng dữ liệu để đảm bảo tính toàn vẹn của chuỗi.</li>

<li>Time-binning: Các mốc thời gian (cột date âm) diễn ra trước khi khóa học bắt đầu đều được quy về ngày 0 (tuần đầu tiên) để không làm đứt gãy chuỗi sự kiện.</li>
</ul>
