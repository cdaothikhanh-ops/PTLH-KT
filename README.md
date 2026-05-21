# Phân Tích Và Lập Báo Cáo Đánh Giá Rủi Ro (Risk Assessment)

## Tổng Quan Dự Án
Trong bối cảnh các cuộc tấn công mạng nhắm vào ứng dụng Web ngày càng tinh vi, việc chủ động nhận diện lỗ hổng và đánh giá tác động là bước đi sống còn để bảo vệ tài sản thông tin của doanh nghiệp. Dự án này tập trung nghiên cứu, xây dựng quy trình và thực hiện **Đánh giá rủi ro an ninh thông tin (Risk Assessment)** cho một hệ thống Web mô phỏng.

Dự án áp dụng các tiêu chuẩn quốc tế uy tín kết hợp với các công cụ kiểm thử tự động để phát hiện, phân tích và xếp hạng rủi ro, từ đó đề xuất các giải pháp giảm thiểu tối ưu cho hệ thống.

---

## Khung Phương Pháp Luận Sử Dụng
Quy trình đánh giá rủi ro trong dự án được xây dựng dựa trên sự kết hợp giữa các tiêu chuẩn và mô hình quản trị an toàn thông tin chuẩn hóa:
1. **NIST SP 800-30 Rev 1:** Hướng dẫn nền tảng để thực hiện các bước đánh giá rủi ro (Nhận diện mối đe dọa, lỗ hổng, xác định khả năng xảy ra và mức độ tác động).
2. **ISO/IEC 27005:** Khung quản lý rủi ro an ninh thông tin, hỗ trợ thiết lập bối cảnh và định hướng xử lý rủi ro cho doanh nghiệp.
3. **OWASP Top 10:** Danh mục 10 lỗ hổng bảo mật ứng dụng Web nguy hiểm nhất hiện nay, đóng vai trò làm cơ sở phân loại và đánh giá mức độ nghiêm trọng của các lỗ hổng tìm thấy.

---

## Công Cụ Và Môi Trường Thực Nghiệm
* **Môi trường mô phỏng:** Triển khai các ứng dụng Web có chủ đích chứa lỗ hổng (DVWA/WebGoat hoặc hệ thống Web Lab) để tiến hành thực nghiệm an toàn.
* **OWASP ZAP (Zed Attack Proxy):** Công cụ quét lỗ hổng tự động và bán tự động chủ lực được sử dụng để dò tìm các điểm yếu bảo mật (như SQL Injection, Cross-Site Scripting - XSS, Broken Authentication,...).
* **Kiểm thử thủ công (Manual Testing):** Phối hợp kiểm tra lại kết quả từ công cụ tự động nhằm loại bỏ các cảnh báo sai (False Positives) và đánh giá sâu hơn logic nghiệp vụ của ứng dụng.

---

## Quy Trình Đánh Giá & Xử Lý Rủi Ro

### 1. Phân Tích Điểm Yếu và Lỗ Hổng
Thông qua việc quét và kiểm thử, hệ thống thu thập các dữ liệu kỹ thuật về:
* Các cổng dịch vụ mở không an toàn.
* Thiếu sót trong cấu hình bảo mật (Security Misconfiguration).
* Khả năng bị khai thác dữ liệu từ phía máy chủ hoặc chiếm quyền điều khiển phiên làm việc (Session Hijacking).

### 2. Xác Định Mức Độ Rủi Ro (Risk Matrix)
Mức độ rủi ro của từng lỗ hổng được tính toán dựa trên ma trận kết hợp giữa:
$$\text{Mức độ rủi ro} = \text{Khả năng xảy ra (Likelihood)} \times \text{Mức độ tác động (Impact)}$$

* **Khả năng xảy ra:** Đánh giá dựa trên mức độ dễ dàng khai thác của lỗ hổng và sự phổ biến của kỹ thuật tấn công.
* **Mức độ tác động:** Đánh giá dựa trên thiệt hại đối với 3 thuộc tính an toàn thông tin cốt lõi: Tính bảo mật (Confidentiality), Tính toàn vẹn (Integrity), và Tính sẵn sàng (Availability) - Mô hình CIA.

Các kết quả rủi ro sau đó được phân loại theo các cấp độ: **Nghiêm trọng (Critical), Cao (High), Trung bình (Medium), Thấp (Low)** để doanh nghiệp có chiến lược ưu tiên xử lý thích hợp.

### 3. Đề Xuất Giải Pháp Giảm Thiểu
Báo cáo đề xuất hai nhóm giải pháp chính:
* **Giải pháp kỹ thuật:** Cấu hình lại hệ thống, cập nhật các bản vá bảo mật (Patches), triển khai tường lửa ứng dụng Web (WAF), mã hóa dữ liệu nhạy cảm và chuẩn hóa dữ liệu đầu vào (Input Validation).
* **Giải pháp quản lý:** Xây dựng chính sách an toàn thông tin, thiết lập quy trình kiểm thử định kỳ và nâng cao nhận thức bảo mật cho đội ngũ phát triển phần mềm (DevSecOps).

---

