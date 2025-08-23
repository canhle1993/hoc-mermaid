# Test Mermaid trên GitHub
## Biểu đồ đầu tiên của tôi
```mermaid
graph LR
    A[Bắt đầu] --> B[GitHub tự động hỗ trợ]
    B --> C[Không cần cài đặt]
    C --> D[Xem ngay kết quả]

    %% Tô màu từng node (hình chữ nhật vuông)
    style A fill:#4CAF50,stroke:#2E7D32,stroke-width:2px,color:white
    style B fill:#2196F3,stroke:#1565C0,stroke-width:2px,color:white
    style C fill:#FFC107,stroke:#FFA000,stroke-width:2px,color:black
    style D fill:#FF5722,stroke:#E64A19,stroke-width:2px,color:white
```
```mermaid
graph LR
A[VS Code] --> B[Extension]
B --> C[Mermaid hoạt động]
```

Cú pháp cơ bản:

```mermaid
graph TD
A[Bước 1] --> B[Bước 2]
B --> C[Bước 3]
```

Các hình dạng node:

```mermaid
graph TD
A[Hình chữ nhật]
B(Hình bo góc)
C([Hình stadium])
D[[Hình đặc biệt]]
E[(Database)]
F((Hình tròn))
G{Hình thoi}
H{{Hình lục giác}}
I[/Hình thang/]
J[\Hình thang ngược\]
```

Các loại mũi tên:

```mermaid
graph LR
A --> B
A --- C
A -.-> D
A ==> E
A -.- F
A === G
```

Thêm text trên mũi tên:

```mermaid
graph LR
A -->|Có| B
B -->|Không| C
C -.Có thể.-> D
D ==Chắc chắn==> E
```

Thêm text trên mũi tên:

```mermaid
sequenceDiagram
participant A as Người dùng
participant B as Hệ thống
participant C as Database
A->>B: Đăng nhập
B->>C: Kiểm tra user
C-->>B: Thông tin user
B-->>A: Đăng nhập thành công
```

Kích hoạt (Activation):

```mermaid
sequenceDiagram
Alice->>+John: Xin chào John
John-->>-Alice: Chào Alice
```

Vòng lặp và điều kiện:

```mermaid
sequenceDiagram
User->>System: Login
alt Đăng nhập thành công
System-->>User: Welcome
else Sai mật khẩu
System-->>User: Error
end
loop Kiểm tra mỗi 5 phút
System->>Database: Health check
end
```

CLASS DIAGRAM - Biểu đồ lớp

```mermaid
classDiagram
class User {
-String id
-String email
+login()
+logout()
}
class Admin {
-String role
+deleteUser()
}
User <|-- Admin : Kế thừa
```

STATE DIAGRAM - Biểu đồ trạng thái

```mermaid
stateDiagram-v2
[*] --> Chờ
Chờ --> Xử_lý : Bắt đầu
Xử_lý --> Hoàn_thành : Thành công
Xử_lý --> Lỗi : Thất bại
Hoàn_thành --> [*]
Lỗi --> Chờ : Thử lại
Lỗi --> [*] : Hủy
```

ER DIAGRAM - Biểu đồ quan hệ thực thể

```mermaid
erDiagram
KHACH_HANG ||--o{ DON_HANG : dat
DON_HANG ||--|{ CHI_TIET : co
SAN_PHAM ||--o{ CHI_TIET : trong
KHACH_HANG {
string ma_kh PK
string ten
string email
string sdt
}
DON_HANG {
string ma_don PK
string ma_kh FK
date ngay_dat
float tong_tien
}
SAN_PHAM {
string ma_sp PK
string ten_sp
float gia
int ton_kho
}
```

GANTT CHART - Biểu đồ Gantt

```mermaid
gantt
title Kế hoạch dự án
dateFormat YYYY-MM-DD
section Phân tích
Khảo sát :done, a1, 2024-01-01, 7d
Thiết kế :active, a2, after a1, 10d
section Phát triển
Backend :b1, 2024-01-15, 20d
Frontend :b2, after b1, 15d
section Testing
Test :c1, after b2, 10d
Deploy :milestone, after c1, 0d
```

PIE CHART - Biểu đồ tròn

```mermaid
pie title Thị phần sản phẩm
"Sản phẩm A" : 45
"Sản phẩm B" : 25
"Sản phẩm C" : 20
"Khác" : 10
```

Vẽ flowchart quy trình đăng ký

1.

```mermaid
graph TD
```

Bước 2: Thêm các bước

```mermaid
graph TD
Start[Bắt đầu]
Input[Nhập thông tin]
Validate{Kiểm tra}
Success[Thành công]
Error[Lỗi]
End[Kết thúc]
```

Bước 3: Nối các bước

```mermaid
graph TD
Start[Bắt đầu]
Input[Nhập thông tin]
Validate{Kiểm tra hợp lệ?}
Success[Tạo tài khoản]
Error[Hiện lỗi]
End[Kết thúc]
Start --> Input
Input --> Validate
Validate -->|Hợp lệ| Success
Validate -->|Không hợp lệ| Error
Success --> End
Error --> Input
```

Vẽ tương tác API
Vẽ sequence diagram gọi API

```mermaid
sequenceDiagram
participant C as Client
participant S as Server
participant D as Database
C->>S: Request (GET /users)
activate S
S->>D: Query SELECT
activate D
D-->>S: Data rows
deactivate D
S-->>C: Response (JSON)
deactivate S
```

BÀI TẬP 3: Thiết kế class OOP

```mermaid
classDiagram
class NhanVien {
-String maNV
-String hoTen
-double luong
+tinhLuong()
+inThongTin()
}
class QuanLy {
-double phuCap
+duyetDon()
}
class NhanVienBanHang {
-double doanhSo
+tinhHoaHong()
}
NhanVien <|-- QuanLy
NhanVien <|-- NhanVienBanHang
```

Hệ thống E-commerce

```mermaid
graph TB
subgraph "Frontend"
Web[Website]
Mobile[Mobile App]
end
subgraph "Backend"
API[API Gateway]
Auth[Auth Service]
Product[Product Service]
Order[Order Service]
Payment[Payment Service]
end
subgraph "Database"
UserDB[(User DB)]
ProductDB[(Product DB)]
OrderDB[(Order DB)]
end
subgraph "External"
PayGate[Payment Gateway]
Ship[Shipping API]
Email[Email Service]
end
Web --> API
Mobile --> API
API --> Auth
API --> Product
API --> Order
API --> Payment
Auth --> UserDB
Product --> ProductDB
Order --> OrderDB
Payment --> PayGate
Order --> Ship
Order --> Email
style Web fill:#e1f5fe
style Mobile fill:#e1f5fe
style API fill:#fff3e0
style Auth fill:#f3e5f5
style Product fill:#f3e5f5
style Order fill:#f3e5f5
style Payment fill:#f3e5f5
```

Quy trình vay vốn ngân hàng

```mermaid
flowchart TD
Start([Khách hàng có nhu cầu vay])
Consult[Tư vấn viên tư vấn]
Docs[/Chuẩn bị hồ sơ/]
Submit[Nộp hồ sơ]
Review{Thẩm định}
Approve{Phê duyệt?}
Sign[Ký hợp đồng]
Disburse[Giải ngân]
Reject[Từ chối]
Supplement[Bổ sung hồ sơ]
End([Kết thúc])
Start --> Consult
Consult --> Docs
Docs --> Submit
Submit --> Review
Review -->|Đầy đủ| Approve
Review -->|Thiếu| Supplement
Supplement --> Submit
Approve -->|Đồng ý| Sign
Approve -->|Không| Reject
Sign --> Disburse
Disburse --> End
Reject --> End
style Start fill:#c8e6c9
style End fill:#ffcdd2
style Approve fill:#fff9c4
style Review fill:#fff9c4
```

Luồng xác thực 2FA

```mermaid
sequenceDiagram
autonumber
actor User
participant App
participant Server
participant SMS
participant DB
User->>App: Nhập username/password
App->>Server: POST /login
Server->>DB: Kiểm tra credentials
DB-->>Server: User valid
Server->>SMS: Gửi OTP
SMS-->>User: SMS: Mã OTP 123456
Server-->>App: Yêu cầu OTP
User->>App: Nhập OTP
App->>Server: POST /verify-otp
Server->>DB: Kiểm tra OTP
alt OTP đúng
DB-->>Server: OTP valid
Server->>Server: Tạo JWT token
Server-->>App: Token + Success
App-->>User: Đăng nhập thành công
else OTP sai
DB-->>Server: OTP invalid
Server-->>App: Error
App-->>User: OTP không đúng
end
Note over User,DB: Quá trình xác thực 2 lớp hoàn tất
```

MẸO VÀ THỦ THUẬT

1. Thêm màu sắc

```mermaid
graph TD
A[Node A]:::classGreen
B[Node B]:::classRed
C[Node C]:::classBlue
A --> B
B --> C
classDef classGreen fill:#9f6,stroke:#333,stroke-width:2px
classDef classRed fill:#f96,stroke:#333,stroke-width:2px
classDef classBlue fill:#69f,stroke:#333,stroke-width:2px
```

2. Subgraph lồng nhau

```mermaid
graph TB
subgraph "Hệ thống"
subgraph "Frontend"
A[React]
B[Vue]
end
subgraph "Backend"
C[Node.js]
D[Python]
end
end
A --> C
B --> D
```

3. Note và comment

```mermaid
graph LR
A[Start] --> B[Process]
B --> C[End]
A -.->|Note| D[This is a note]
%% This is a comment - won't show
```

4. Đánh số tự động

```mermaid
sequenceDiagram
autonumber
Alice->>John: Message 1
John-->>Alice: Message 2
Alice->>John: Message 3
```




