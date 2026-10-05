# Reflection — Lab 19

**Path:** Lite (Python 3.14, WSL)

## Kết quả và lựa chọn tìm kiếm

Trên 50 golden queries, Hybrid đạt Precision@10 trung bình **78,6%**, hơn BM25 (**77,8%**) và vector (**73,2%**). Hybrid đạt **100%** ở nhóm `mixed` nhờ kết hợp tín hiệu từ khóa và ngữ nghĩa; ở `exact`, BM25 và Hybrid cùng đạt **96,7%**. Ở `paraphrase`, BM25 đạt **33,3%**, Hybrid **32,0%**, vector **24,0%**. Vector không thắng ở đây, có thể vì `bge-small-en-v1.5` chủ yếu được huấn luyện bằng tiếng Anh. Cần kiểm chứng embedding trên ngôn ngữ và dữ liệu thực tế.

Chọn BM25 khi truy vấn cần khớp mã/tên chính xác và ưu tiên tốc độ, đơn giản. Chọn vector thuần khi truy vấn thiên về ngữ nghĩa và embedding đã được kiểm chứng cho dữ liệu đó.

## Điều ngạc nhiên nhất

Vector yếu với paraphrase tiếng Việt là điều bất ngờ nhất; embedding phù hợp quan trọng không kém thuật toán.
