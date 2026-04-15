[![Open in Visual Studio Code](https://classroom.github.com/assets/open-in-vscode-2e0aaae1b6195c2367325f4f02e2d04e9abb55f0b24a779b69b11b9e10269abc.svg)](https://classroom.github.com/online_ide?assignment_repo_id=23573928&assignment_repo_type=AssignmentRepo)
# Day 10 Lab: Data Pipeline & Data Observability

**Student Email:** duongkien6883@gmail.com
**Student ID:** AI20K-2A202600048
**Name:** Duong Manh Kien

---

## Mo ta

Bai lab nay xay dung mot ETL pipeline tu dong de xu ly du lieu san pham tu file JSON. Pipeline thuc hien cac buoc: Extract du lieu tu `raw_data.json`, Validate de loai bo cac record khong hop le (gia <= 0 hoac category rong), Transform de tinh gia giam 10% va chuan hoa category, sau do Load ket qua ra file CSV. Ngoai ra, bai lab con thuc hien thi nghiem so sanh ket qua cua AI Agent khi chay voi du lieu sach va du lieu rac (garbage data).

---

## Cach chay (How to Run)

### Prerequisites
```bash
python -m venv venv
source venv/bin/activate   # Windows: venv\Scripts\activate
pip install pandas pytest
```

### Chay ETL Pipeline
```bash
python solution.py
```

Ket qua se duoc luu vao `processed_data.csv`.

### Chay Tests
```bash
pytest tests/
```

### Chay Agent Simulation (Stress Test)
```bash
# Chay voi du lieu sach
python agent_simulation.py

# Chay voi du lieu rac
python generate_garbage.py
python agent_simulation.py
```

---

## Cau truc thu muc

```
├── solution.py              # ETL Pipeline script
├── processed_data.csv       # Output cua pipeline (3 records sau khi validate)
├── experiment_report.md     # Bao cao thi nghiem so sanh Clean vs Garbage data
├── agent_simulation.py      # Script mo phong AI Agent
├── generate_garbage.py      # Script tao du lieu rac de thu nghiem
├── raw_data.json            # Du lieu dau vao (5 records)
└── README.md                # File nay
```

---

## Ket qua

- Tong so records dau vao: 5
- Records hop le (valid): 3 (Laptop, Chair, Monitor)
- Records bi loai bo (dropped): 2
  - Mystery Box (price = -10, gia am)
  - Phone (category = "", rong)
- Tat ca records trong output deu co `discounted_price` (giam 10%) va `processed_at` timestamp
