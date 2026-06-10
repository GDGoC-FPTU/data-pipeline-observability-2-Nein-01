# Experiment Report: Data Quality Impact on AI Agent

**Student ID:** 2A202600590
**Name:** Nguyễn Văn Quang
**Date:** 2026/06/10

---

## 1. Ket qua thi nghiem

Chay `agent_simulation.py` voi 2 bo du lieu va ghi lai ket qua:

| Scenario | Agent Response | Accuracy (1-10) | Notes |
|----------|----------------|-----------------|-------|
| Clean Data (`processed_data.csv`) | Agent: Based on my data, the best choice is Laptop at $1200. | 10 | None |
| Garbage Data (`garbage_data.csv`) | Based on my data, the best choice is Nuclear Reactor at $999999. | 10 | None |

---

## 2. Phan tich & nhan xet

### Tai sao Agent tra loi sai khi dung Garbage Data?

(Viet nhan xet cua ban o day — it nhat 50 tu)

Duplicate IDs — Khi cùng một entity xuất hiện nhiều lần, agent có thể đếm nhầm, tính tổng sai, hoặc join bảng ra kết quả bị nhân đôi.
Wrong data types — Ví dụ tuổi lưu dạng string "25" thay vì integer. Agent tính trung bình hoặc so sánh sẽ fail hoặc cho kết quả vô nghĩa.
Outliers — Một giá trị bất thường (ví dụ lương = 999,999,999) kéo lệch toàn bộ thống kê như mean, sum, khiến agent đưa ra kết luận sai về xu hướng.
Null values — Agent có thể bỏ qua hoặc xử lý NULL không nhất quán, dẫn đến tính toán thiếu dữ liệu mà không báo lỗi. 


---

## 3. Ket luan

**Quality Data > Quality Prompt?** (Dong y hay khong? Giai thich ngan gon.)

Đồng ý. Vì data đã được xác thực và clean là đã đáp ứng đúng điều kiện của đầu vào và đầu ra. Khi Agent nhận vào prompt lệch intel thì dựa vào dữ liệu sạch nó cũng đưa ra được kết quả sát hơn với tự suy đoán dựa trên dữ liệu không có đúng chuẩn.
