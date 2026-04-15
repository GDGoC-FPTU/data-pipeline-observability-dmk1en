# Bao cao Thi nghiem: Anh huong cua Chat luong Du lieu den AI Agent

**Student ID:** AI20K-2A202600048
**Ten:** Duong Manh Kien
**Ngay thuc hien:** 2026-04-15

---

## 1. Ket qua thi nghiem

Chay `agent_simulation.py` voi 2 bo du lieu va ghi lai ket qua:

| Scenario | Agent Response | Accuracy (1-10) | Ghi chu |
|----------|----------------|-----------------|---------|
| Clean Data (`processed_data.csv`) | "Based on my data, the best choice is Laptop at $1200." | 9 | Agent goi y dung san pham, gia chinh xac, du lieu da qua validate |
| Garbage Data (`garbage_data.csv`) | "Based on my data, the best choice is Nuclear Reactor at $999999." | 1 | Agent bi dan boi gia tri bat thuong (outlier), san pham khong hop le |

---

## 2. Phan tich & nhan xet

### Tai sao Agent tra loi sai khi dung Garbage Data?

Khi Agent nhan du lieu rac, nhieu loai loi chat luong du lieu da truc tiep lam hong ket qua dau ra. Thu nhat, cac gia tri bat thuong (outlier) nhu gia $999999 cho "Nuclear Reactor" lam lech hoan toan ket qua tinh toan trung binh va so sanh, khien Agent chon san pham hoan toan vo ly. Thu hai, ID bi trung lap khien cac ban ghi duoc dem nhieu lan, lam phat phong tong so va sai lech phan tich theo nhom. Thu ba, gia am hoac bang 0 la du lieu khong hop le ve mat nghiep vu, neu khong loc bo truoc se anh huong den moi phep tinh so sanh gia. Thu tu, category trong hoac sai kieu du lieu khien Agent khong the phan nhom san pham chinh xac, dan den ket qua tong hop sai. Cuoi cung, chuoi ky tu vo nghia trong truong ten san pham (vi du "Nuclear Reactor") cho thay du lieu rac co the gia mao bat ky thu gi, trong khi Agent van tin tuong xu ly chung nhu du lieu that. Tat ca nhung van de nay cong don voi nhau: chi can mot vai ban ghi loi la co the lam hong toan bo ket qua phan tich. Day la ly do tai sao buoc Validate trong ETL pipeline la bat buoc truoc khi dua du lieu vao bat ky mo hinh hay agent nao.

---

## 3. Ket luan

**Quality Data > Quality Prompt? (Dong y hay khong?)**

Dong y hoan toan. Thi nghiem tren minh chung ro rang: du prompt co viet ky the nao, Agent van tra loi sai khi du lieu dau vao chua rac. Voi clean data, Agent goi y dung san pham thuc te (Laptop $1200); voi garbage data, Agent lai goi y "Nuclear Reactor $999999" — mot ket qua phi thuc te va vo ich. Du lieu sach la nen tang de moi buoc phan tich phia sau dang tin cay. Mot prompt tot giup Agent suy luan tot hon, nhung chi co du lieu tot moi dam bao ket qua chinh xac.
