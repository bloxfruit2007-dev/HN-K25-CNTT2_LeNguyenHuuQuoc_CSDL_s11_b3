1. Xác định dữ liệu và đề xuất tham số

Dữ liệu đầu vào: ứng dụng cần gửi cho cơ sở dữ liệu "tổng chi phí" và "diện bệnh nhân". do đó, ta sử dụng 2 tham số đầu vào là p_totalCost và p_patientType.

Dữ liệu đầu ra: cơ sở dữ liệu cần trả về "số tiền cuối cùng" và "thông báo trạng thái". do đó, ta sử dụng 2 tham số đầu ra là p_finalAmount và p_statusMessage để ứng dụng có thể lấy kết quả về.

2. Giải pháp và các bước thực hiện

Giải pháp: xây dựng một stored procedure đóng vai trò như một cỗ máy tính toán, nhận 2 biến đầu vào, xử lý logic rẽ nhánh bằng if-else và nhả kết quả ra 2 biến đầu ra.

Bước 1: dùng if để kiểm tra chốt chặn đầu tiên. nếu p_totalCost nhỏ hơn 0, gán ngay số tiền bằng 0 và trả về thông báo lỗi, sau đó kết thúc nhánh logic.

Bước 2: nếu chi phí lớn hơn hoặc bằng 0, tiếp tục dùng logic rẽ nhánh kiểm tra p_patientType.

Bước 3: thực hiện phép nhân tương ứng (0.2 cho bhyt, 0.9 cho vip, 1.0 cho thuong) và lưu vào p_finalAmount. đồng thời gán thông báo thành công cho p_statusMessage.