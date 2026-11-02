# BÁO CÁO THIẾT KẾ CHROME PROFILE VÀ HỆ THỐNG BOOKMARK AN TOÀN
## I. BÁO CÁO PHÂN TÍCH KIẾN TRÚC ĐA PROFILE
### 1. Phân tích nguyên nhân Session Conflict

Việc nhiều nhân viên sử dụng chung một Chrome Profile khiến các dữ liệu trình duyệt như **Cookies, Session, History, Bookmarks và Extensions** được lưu chung trong cùng User Data Directory.

Khi người dùng đăng nhập các tài khoản khác nhau, Cookie phiên có thể bị thay đổi hoặc xung đột, dẫn đến tài khoản CarePulse bị đăng xuất giữa chừng.

**Giải pháp:** Sử dụng các Chrome Profile riêng biệt để mỗi người hoặc mỗi mục đích có vùng dữ liệu độc lập.

### 2. Thiết kế mô hình 3 Profile
Profile
Mục đích
Theme
Dữ liệu lưu trữ
**Work**
Làm việc với CarePulse
Xanh dương
Cookies, History, Bookmarks, Extensions công việc
**Personal**
PTIT, GitHub và nhu cầu cá nhân
Xanh lá
Cookies, History, Bookmarks, Extensions cá nhân
**Sandbox/Test**
Kiểm thử website và phần mềm
Cam
Cookies, History, Bookmarks, Extensions thử nghiệm
Việc phân tách này giúp hạn chế xung đột phiên đăng nhập và giảm nguy cơ dữ liệu cá nhân lẫn với dữ liệu công việc.
# II. THIẾT KẾ HỆ THỐNG BOOKMARK VÀ QUY TRÌNH AN TOÀN
### 3. Cấu trúc cây Bookmark
Thiết lập trong **Bookmark Manager (**`**Ctrl + Shift + O**`**)**:
```
 01_CarePulse_Clinic
    - CarePulse
    - Cổng BHYT
    - Hồ sơ bệnh nhân

 02_Pharma_Portal
   - Dược thư Quốc gia
   - Tra cứu thuốc
   - Cổng thông tin dược

 03_Medical_Tools
   - Google Dịch
   - Công cụ tính BMI
   - Công cụ tính liều thuốc
```

Cách tổ chức này giúp nhân viên nhanh chóng tìm được tài nguyên cần thiết, tránh tình trạng thanh Bookmark có quá nhiều liên kết lộn xộn.

### 4. Áp dụng Favicon-Only

Đối với 4 website thường xuyên sử dụng gồm **CarePulse, Cổng BHYT, Dược thư và Google Dịch**, thực hiện:

1.  Mở **Bookmark Manager**.
    
2.  Chọn Bookmark cần chỉnh sửa.
    
3.  Chọn **Edit**.
    
4.  Xóa phần **Tên/Name**, chỉ giữ lại URL.
    
5.  Bookmark sẽ hiển thị chủ yếu bằng biểu tượng favicon.
    

Nhờ vậy có thể đưa nhiều website lên thanh Bookmark mà không làm thanh công cụ bị tràn.

# III. XỬ LÝ BẪY AN NINH

### 5. Guest Profile hay Incognito?

Khi đoàn thanh tra hoặc khách mượn máy trong khoảng 30 phút, nên sử dụng **Guest Profile** thay vì mở trực tiếp Profile Work.

**Lý do:**

-   Không truy cập trực tiếp vào dữ liệu công việc của Profile Work.
    
-   Không làm lẫn History, Bookmark và Session công việc.
    
-   Sau khi kết thúc có thể đóng Guest để loại bỏ dữ liệu phiên duyệt.
    

**Không sử dụng tài khoản cá nhân để bật Cloud Sync trên máy trạm y tế.** Nếu bật đồng bộ, dữ liệu như History, Bookmark, mật khẩu hoặc các dữ liệu trình duyệt khác có thể được đồng bộ lên tài khoản cá nhân, làm tăng nguy cơ rò rỉ thông tin.

## IV. KẾT LUẬN

Mô hình **3 Chrome Profile: Work – Personal – Sandbox/Test** giúp tách biệt dữ liệu và hạn chế xung đột phiên đăng nhập. Hệ thống Bookmark được phân loại theo chức năng giúp tăng tốc độ tìm kiếm tài nguyên. Kết hợp **Guest Profile và kiểm soát Cloud Sync** sẽ giúp máy tính phòng khám an toàn hơn khi được sử dụng chung bởi nhiều nhân viên.


