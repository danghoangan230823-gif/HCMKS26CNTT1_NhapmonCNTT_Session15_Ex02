# Quản lý quyền truy cập báo cáo tài chính
## 1. Bản thiết kế phân quyền an toàn (Access Control Matrix)
----
| **Đối tượng/Vai trò** | **Mức quyền đề xuất**| **Lý do và Phạm vi thao tác an toàn**|
|---|---|---| 
|**Ứng viên bên ngoài**| No Access (Thu hồi toàn bộ) |Tuyệt đối không cấp quyền xem hay chỉnh sửa thông tin nhân sự nội bộ.|
|**Trưởng bộ phận (Hiring Managers)** | Commenter (chế độ Suggesting) | Chỉ được phép đọc và để lại bình luận hoặc đề xuất (Suggesting Mode) để góp ý CV, không có quyền sửa trực tiếp hoặc tải/copy dữ liệu gốc.
|**Trưởng phòng Nhân sự (HR Manager)** | Editor (hoặc Owner) | Quản lý toàn bộ tệp, nên có thẻ chỉnh sữa được,và duyệt các đề xuất từ các người khác
|**Nhân viên Nhân sự (HR Staff)** | Viewer / Editor (giới hạn) | Chỉ có thể xem, và nhập dữ liệu m theo phân công, không có quyền chia sẻ link ra bên ngoài
## 2. Kịch bản xử lý sự cố (3 bước khi dữ liệu bị chia sẻ sai quyền)
### Bước 1: Ngắt quyền truy cập ngay lập tức (Revoke Access)
- Vào ngay cài đặt chia sẻ (Share settings) của tệp trên nền tảng lưu trữ (Google Drive/SharePoint).

- Xóa ngay đường link công khai hoặc gỡ quyền Editor của đối tượng ngoài (ứng viên).

- Chuyển trạng thái liên kết chia sẻ từ "Anyone with the link" sang "Restricted" (Chỉ những người được thêm thủ công mới truy cập được).
### Bước 2: Rà soát nhật ký hoạt động (Access Audit Log)
- Truy cập Admin Console hoặc mục Activity / Version History của file để kiểm tra xem tài khoản/email của ứng viên đó đã mở file, thao tác, tạo bản sao (Make a copy), hay tải xuống (Download) hay chưa.

- Ghi nhận mốc thời gian (timestamp) từ lúc link bị phát tán đến lúc thu hồi quyền để đánh giá mức độ rò rỉ.
### Bước 3: Siết chặt bảo mật & Khắc phục (Harden & Remediate)
- Bật tính năng chặn sao chép, tải xuống và in đối với tất cả Viewer/Commenter.
- Báo cáo sự cố lên IT Security và liên hệ ứng viên yêu cầu cam kết bảo mật (nếu dữ liệu đã bị tải về).