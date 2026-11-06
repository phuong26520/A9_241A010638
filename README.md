Lab A9 - Adapter và ListView - Thực đơn quán ăn

Thông tin sinh viên: Nguyễn Hoài Phương - MSSV 241A010638 - Lớp LTTTBDD - Môn INT4211.

Mô tả ngắn gọn

App Thực đơn quán ăn hiển thị 5 món ăn với ảnh, tên, mô tả và giá bằng ListView. Có thể thêm món, chạm để xem tên món, giữ lâu để xóa. Khi xóa hết, app hiện thông báo thực đơn trống.

Cấu trúc chính

app/src/main/java/vn/edu/vhu/ltdd/a9listview/: các file MainActivity.java, MonAn.java và MonAnAdapter.java.
app/src/main/res/layout/: giao diện chính và giao diện một dòng món ăn.
app/src/main/res/drawable/: ảnh của 5 món ăn.

Các chức năng đã làm

- Hiển thị món ăn bằng ListView và adapter tự viết.
- Dùng ViewHolder để tái sử dụng dòng khi cuộn; ghi Logcat mỗi khi tạo dòng mới.
- Kiểm tra tên và giá trước khi thêm món lên đầu danh sách.
- Chạm vào món để hiện tên; giữ lâu để xóa món.
- Hiện thông báo khi danh sách không còn món nào.

Bài nâng cao đã làm

NC1 - Tìm kiếm món ăn

Bài yêu cầu lọc danh sách theo tên ngay khi gõ. Mình thêm ô edtTimKiem vào màn hình chính và dùng TextWatcher để theo dõi chữ người dùng nhập. Trong MainActivity, hàm locDanhSach() duyệt danh sách gốc danhSach, lấy các món có tên chứa từ khóa rồi đưa vào danhSachHienThi. Adapter đọc danhSachHienThi và được gọi notifyDataSetChanged() để cập nhật màn hình.

Hai danh sách được giữ riêng nên tìm kiếm không xóa món khỏi dữ liệu gốc. Khi xóa từ khóa, các món còn lại trong thực đơn hiện lại. Khi giữ lâu để xóa trong lúc tìm kiếm, app lấy đúng món được chọn từ ListView, xóa khỏi danhSach rồi lọc lại.

NC4 - Thống kê thực đơn

Bài yêu cầu hiện tổng số món và tổng giá trị. Mình thêm TextView tvThongKe và hàm capNhatThongKe() trong MainActivity. Hàm này đếm số món trong danhSach, cộng giá của từng món rồi dùng MonAn.dinhDangGia() để hiển thị tổng tiền có dấu chấm phân cách.

Thống kê được cập nhật lúc mở app, sau khi thêm hoặc xóa món và khi lọc danh sách. Số liệu tính theo toàn bộ thực đơn gốc, không chỉ các món đang hiện trong kết quả tìm kiếm.

Cách chạy và kiểm thử

Mở project A9_241A010638 trong Android Studio rồi chạy app. Kiểm tra thao tác thêm, chạm, giữ lâu để xóa, tìm kiếm và thống kê. Mở Logcat lọc A9_241A010638 để xem các dòng "inflate dòng mới" khi cuộn.
