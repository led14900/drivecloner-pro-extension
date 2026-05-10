# DriveCloner Pro Extension Chrome

DriveCloner Pro là Extension Chrome giúp sao chép thư mục Google Drive nhanh chóng, tiện lợi.

Extension phù hợp khi bạn cần nhân bản trọn vẹn một thư mục Drive từ tài khoản khác sang tài khoản hoặc thư mục đích của mình mà không phải tải xuống rồi upload lại thủ công. Ứng dụng giữ cấu trúc thư mục, bỏ qua tệp đã tồn tại để hạn chế trùng lặp, hiển thị tiến trình clone và lưu lịch sử ngay trên trình duyệt này để dễ theo dõi.

## Tải extension

1. Mở trang GitHub: https://github.com/led14900/drivecloner-pro-extension
2. Bấm nút `Code` màu xanh.
3. Chọn `Download ZIP`.
4. Giải nén file ZIP vừa tải về máy.
5. Sau khi giải nén, bạn sẽ thấy thư mục `extension`. Đây là thư mục cần nạp vào Chrome.

## Cài vào Chrome

1. Mở Chrome.
2. Gõ `chrome://extensions/` vào thanh địa chỉ.
3. Bật công tắc `Developer mode` ở góc phải phía trên.
4. Bấm `Load unpacked`.
5. Chọn đúng thư mục `extension` đã giải nén.
6. Sau khi cài xong, bấm icon extension trên thanh công cụ Chrome để mở DriveCloner Pro.

Nếu không thấy icon, bấm biểu tượng mảnh ghép Extensions trên Chrome rồi ghim DriveCloner Pro ra thanh công cụ.

## Cấu hình Google Drive API

Làm theo các bước dưới đây để lấy `OAuth Client ID` và dán vào extension.

### 1. Tạo project

Vào https://console.cloud.google.com/ rồi tạo project mới hoặc chọn project có sẵn.

### 2. Bật Google Drive API

Mở `APIs & Services` > `Library`, tìm `Google Drive API`, rồi bấm `Enable`.

### 3. Tạo OAuth Client ID

1. Mở `Google Auth platform` > `Clients`.
2. Bấm `Create client`.
3. Chọn loại `Web application`.
4. Mở DriveCloner Pro > tab `Cài đặt`.
5. Copy `Redirect URI của extension`.
6. Dán Redirect URI vào `Authorized redirect URIs`.
7. Tạo client và copy `OAuth Client ID`, thường kết thúc bằng `.apps.googleusercontent.com`.

Nếu Google yêu cầu cấu hình trước khi tạo client, điền tên app, email liên hệ và chọn `External` khi dùng Gmail cá nhân. Với `Publishing status`, chọn `In production` nếu muốn dùng nhiều tài khoản; chọn `Testing` thì tài khoản đăng nhập phải nằm trong `Test users`.

### 4. Lưu và test kết nối

1. Dán `OAuth Client ID` vào tab `Cài đặt`.
2. Bấm `Lưu`.
3. Bấm `Test kết nối`.
4. Chọn tài khoản Google và cấp quyền Drive.

Khi bấm `Test kết nối`, extension sẽ xin quyền Drive để clone thư mục bằng link nguồn/đích. Nếu Google hiện cảnh báo app chưa xác minh, hãy tiếp tục theo luồng xác nhận của Google.

## Cách sử dụng

1. Mở tab `Clone`.
2. Dán link thư mục Drive nguồn vào ô `URL thư mục nguồn`.
3. Dán link thư mục Drive đích vào ô `URL thư mục đích`.
4. Bấm `Bắt đầu`.
5. Theo dõi tiến trình và kết quả trong phần `Lịch sử Clone`.

Lịch sử được chia theo tab để dễ xem. Mỗi tab hiển thị tối đa 20 lịch sử.

## Dữ liệu được lưu ở đâu

Extension lưu cài đặt và lịch sử clone trên trình duyệt này.

Điều này có nghĩa là:

1. Dữ liệu nằm trong trình duyệt Chrome hiện tại.
2. Khi dùng máy khác, trình duyệt khác hoặc tài khoản Chrome khác, bạn sẽ không thấy lịch sử này.
3. Lịch sử clone không được gửi lên server riêng.
4. Drive access token chỉ dùng trong phiên hiện tại, thường còn hiệu lực khoảng 1 tiếng và không được lưu vào lịch sử.
5. Extension hiển thị đồng hồ đếm ngược token để bạn biết thời gian còn lại trước khi cần cấp quyền lại.

## Lỗi thường gặp

### Không đăng nhập được Google

Kiểm tra lại:

1. Nếu OAuth app đang `Testing`, email Google của bạn đã nằm trong `Test users`.
2. OAuth Client ID đã copy đúng.
3. Redirect URI trong Google Cloud giống hệt Redirect URI hiển thị trong extension.
4. Google Drive API đã được bật trong đúng project chứa OAuth Client ID.

### Không thấy thư mục sau khi clone

Kiểm tra quyền truy cập của tài khoản Google đang dùng. Tài khoản đó cần có quyền đọc thư mục nguồn và quyền ghi vào thư mục đích.

### Muốn dùng trên máy khác

Cài extension lại trên máy đó và cấu hình lại OAuth Client ID. Lịch sử cũ không tự đồng bộ sang máy khác vì dữ liệu chỉ lưu trên trình duyệt hiện tại để riêng tư hơn.

## Chi tiết liên hệ

Phạm Ngọc Tú  
Website: https://airender.vn/  
Phone/Zalo: 0896009111
