# PHẦN 1. PHÂN TÍCH: CƠ CHẾ "GOOGLE SEARCH CỦA BẢNG TÍNH" THÔNG QUA AUTOFILTER
| Tiêu chí | Công cụ tìm kiếm google search | tính năng autofilter trên excel
| Đầu vào | Nhập từ khóa tìm kiếm vào thanh Search Box | Nhập điều kiện vào ô Search trong menu thả xuống của cột hoặc chọn tiêu chí (Equals, Contains, Greater Than...) |
| Cơ chế truy vấn | Quét toàn bộ cơ sở dữ liệu trang web index để lọc các kết quả phù hợp nhất với từ khóa | Quét toàn bộ các bản ghi (Records/Dòng) trong bảng dữ liệu để ẩn đi các dòng không khớp và chỉ giữ lại các dòng thỏa mãn điều kiện |
| Xử lý đa điều kiện | Kết hợp nhiều từ khóa (Boolean Search: AND, OR) |Lọc lồng ghép trên nhiều cột cùng lúc (Ví dụ: Lọc cột Mức độ = Cao AND cột Loại mã độc = Emotet) |
|Độ chính xác | Hỗ trợ tìm kiếm chính xác từ khóa hoặc theo chuỗi con | Hỗ trợ lọc theo Text Filter (Begins With, Contains), Number Filter hay Date Filter rất linh hoạt |
# PHẦN 2. TRIỂN KHAI: BÁO CÁO NETGUARD HOÀN CHỈNH
## Word 
 ### A. Thiết lập cấu trúc
  1. Tổng quan sự cố an ninh ( heading 1 )
   1.1 bối cảnh và tóm tắt executive ( heading 2 )
   1.2 Thống kê mức độ nghiêm trọng ( heading 2 )
  2. Phân tích chi tiết nhật ký hệ thống ( heading 1 )
    2.1 Nhật ký cảnh bảo thô từ threat monitoring ( heading 2 )
    2.2 Phương pháp chuẩn hóa và đối soát mã độc ( heading 2 )
  3. DANH SÁCH MÃ ĐỘC & NGUY CƠ PHÁT HIỆN (Heading 1)
    3.1 Phân tích mã độc Emotet (Heading 2)
    3.2. Phân tích mã độc Lokibot (Heading 2)
    3.3. Phân tích công cụ Cobalt Strike (Heading 2)
  4. ĐÁNH GIÁ TÁC ĐỘNG & LỘ TRÌNH ỨNG CỨU (Heading 1)
    4.1. Mức độ ảnh hưởng hạ tầng IP nội bộ (Heading 2)
    4.2. Khuyến nghị khắc phục & Phòng thủ 3 tầng (Heading 2)
B. Quy trình khởi tạo Mục lục Tự động (Auto TOC)
Đặt con trỏ chuột tại trang đầu tiên của báo cáo.

Vào thẻ References 
→ Table of Contents 
→ Chọn mẫu Automatic Table 1.

Quy tắc nhảy số trang chính xác khi tài liệu mở rộng:

Khi thêm nội dung làm tài liệu dài lên hàng chục trang, nhấp chuột phải vào bảng Mục lục 
→ Chọn Update Field.

Chọn Update entire table để Word đồng bộ lại toàn bộ số trang và tên tiêu đề mới.
2. EXCEL – NỐI & CHUẨN HÓA DỮ LIỆU BẰNG VLOOKUP VÀ TRIM
Để chuyển đổi từ 1. Dữ liệu cảnh báo thô sang 3. Báo cáo cuối cùng cho khách hàng, ta thực hiện kết nối với 2. Bảng định nghĩa loại mã độc trên Excel.

A. Cấu trúc 2 Bảng Dữ liệu (Chuẩn Database)
Bảng 1: Nhật ký cảnh báo thô (Sheet: NhatKySystem)

Cột A: Thời gian (Ví dụ: 2024-05-20 08:15:23)

Cột B: Nguồn (Ví dụ: 192.168.1.10)

Cột C: IP đích (Ví dụ: 10.0.0.5)

Cột D: Loại mã độc (ID) (Ví dụ: MDL_1023  - bị lẫn khoảng trắng)

Cột E: Tên mã độc 
→ Cột cần tra cứu tự động

Cột F: Mô tả 
→ Cột cần tra cứu tự động

Cột G: Mức độ 
→ Cột cần tra cứu tự động

Bảng 2: Bảng định nghĩa loại mã độc (Sheet: DanhMucMadoc)

Cột A: Mã loại (MDL_1023, MDL_2045, MDL_3099)

Cột B: Tên mã độc (Emotet, Lokibot, Cobalt Strike)

Cột C: Mô tả (Banking Trojan, Info Stealer, Penetration Tool)

Cột D: Mức độ mặc định (Cao, Trung bình, Cao)
