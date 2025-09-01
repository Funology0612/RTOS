# Task trong RTOS 
* Một task là một đoạn chương trình (hàm) được thiết kế để chạy độc lập trong hệ thống
* Mỗi task có:
  * Stack riêng (dùng cho biến cục bộ, lưu context khi chuyển task)
  * Priority (độ ưu tiên): RTOS sẽ chọn task ưu tiên cao hơn để chạy trước
  * Trạng thái: Ready, Running, Blocked, Suspended...
* RTOS sẽ **quản lý và chuyển đổi** giữa các task (context switching) để tạo cảm giác như nhiều việc chạy song song (thực chất là đa nhiệm thời gian)

## Ví dụ thực tế
* Giả sử bạn có một hệ thống STM32 cần:
  * Task 1: Đọc cảm biến nhiệt độ mỗi 1 giây
  * Task 2: Điều khiển LED nhấp nháy mỗi 500 ms
  * Task 3: Gửi dữ liệu UART sang PC

## Ưu điểm của RTOS
* Tách biệt chức năng: mỗi công việc chạy độc lập, dễ bảo trì
* Đáp ứng real-time: nhờ ưu tiên, task quan trọng (ví dụ ngắt an toàn) sẽ luôn được xử lý trước
* Đa nhiệm: nhiều tác vụ "cùng chạy" trên một vi điều khiển

# Các trạng thái củ Task
* Running: đang được CPU thực thi
* Ready: sẵn sàng chạy, chờ CPU
* Blocked: đang chờ sự kiện (ví dụ chờ UART, chờ delay)
* Suspended: bị dừng bởi lập trình viên

![example](word-image-11065-1.jpeg)
