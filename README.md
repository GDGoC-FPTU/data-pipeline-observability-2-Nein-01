[![Open in Visual Studio Code](https://classroom.github.com/assets/open-in-vscode-2e0aaae1b6195c2367325f4f02e2d04e9abb55f0b24a779b69b11b9e10269abc.svg)](https://classroom.github.com/online_ide?assignment_repo_id=24112941&assignment_repo_type=AssignmentRepo)
# Day 10 Lab: Data Pipeline & Data Observability

**Student Email:** 26ai.quangnv3@vinuni.edu.vn
**Name:** Nguyễn Văn Quang

---

## Mo ta
Trong bài lab này tôi đã:
    - Extract dữ liệu từ file JSON.
    - Kiểm tra & loại bỏ dữ liệu không hợp lệ.
    - Chuẩn hóa dữ liệu.
    - Load dữ liệu ra file CSV.

---

## Cach chay (How to Run)

### Prerequisites
```bash
pip install pandas
```

### Chay ETL Pipeline
```bash
python solution.py
```

### Chay Agent Simulation (Stress Test)
```bash
# Mo ta cach ban chay thi nghiem Clean vs Garbage data
# Tao garbage data
python generate_garbage.py
# Chay Agent Simulation
python agent_simulation.py
```

## Cau truc thu muc

```
├── solution.py              # ETL Pipeline script
├── processed_data.csv       # Output cua pipeline
├── experiment_report.md     # Bao cao thi nghiem
└── README.md                # File nay
```

---

## Ket qua

Kết quả chạy các file lab có những kết quả:
Bộ dữ liệu từ raw_data.json có:
    - Valid: 3 items.
    - Dropped: 2 items [{'id': 3, 'reason': 'Price not appropriate'}, {'id': 4, 'reason': 'Category is empty'}]
Từ đó tạo ra `garbage_data.csv` có 'Poisoned' records.
Rồi Agent Simulation sử dụng file data garbage ấy để xử lý data và cho ra kết quả: 
```bash
    Testing with CLEAN data:
    Agent: Based on my data, the best choice is Laptop at $1200.

    Testing with GARBAGE data:
    Agent: Based on my data, the best choice is Nuclear Reactor at $999999.
```
