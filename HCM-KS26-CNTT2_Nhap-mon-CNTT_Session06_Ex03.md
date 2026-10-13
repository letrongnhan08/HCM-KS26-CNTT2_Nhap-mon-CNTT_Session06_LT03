Bài 3 : Thống kê sự cố TIMEOUT trên máy chủ

Phần 1:

Vẽ sơ đồ pipeline

|Lọc tệp , Tìm kiếm từ khóa (Select-String)<br /> - Quét nội dung tệp log<br /> - Lọc các dòng chứa từ khóa "TIMEOUT"|
|-|
|Lọc từ khóa loại trừ bẫy dữ liệu (Where-Object)<br /> - Lọc bỏ các dòng chứa "NOT TIMEOUT"|
|Đếm kết quả (.Count)<br /> - Tập hợp đối tượng mang theo thuộc tính .Count<br /> - Trả về duy nhất 1 con số tổng|



Phần 2: viết lại câu lệnh

(Get-Content \*.log | Select-String "TIMEOUT") | Where-Object { $\_ -notmatch "NOT TIMEOUT" }

