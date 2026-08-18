# Reflection

Anti-pattern mà dữ liệu dễ gặp nhất là **quá nhiều file nhỏ**. Dữ liệu quan sát LLM và trajectory của agent được ghi liên tục theo từng request hoặc micro-batch; mỗi lần ghi tạo một file Parquet sẽ làm số object tăng nhanh hơn dung lượng thực tế. Trong NB2, 200 file khiến truy vấn mất 223,5 ms; sau compaction và clustering còn 55 file, truy vấn chỉ mất 33,9 ms, nhanh hơn 6,6 lần. NB6 tiếp tục giảm 200 file xuống 11 file và cho thấy chi phí GET phụ thuộc trực tiếp vào số file.

Rủi ro này làm tăng thời gian lập kế hoạch, metadata, chi phí object-store và khiến độ trễ thiếu ổn định. Nhóm em sẽ đặt kích thước file mục tiêu, compact định kỳ, cluster theo khóa truy vấn phổ biến và theo dõi số file trên mỗi partition. Compaction phải đi cùng checkpoint, VACUUM và quét orphan có age guard; nếu bỏ qua lifecycle, chi phí lưu trữ vẫn tăng và khả năng time travel có thể mất ngoài dự kiến.
