# VinTelligence Datathon 2026 — The Gridbreakers (Vòng 1)

**Bài toán**: Dự báo doanh thu và COGS hàng ngày, giai đoạn 01/01/2023 – 01/07/2024
 https://www.kaggle.com/competitions/datathon-2026-round-1
 
**Đội thi**: _**The Forecasters**_

**Thành viên**: _**Lâm Huy Vũ**_, Lê Hoàng Phúc, Hoàng Phương Dung, Phạm Xuân Tuấn

---

## Cấu trúc thư mục
```
DATATHON2026/
├── data/datathon-2026-round-1
│
├── notebooks/
│ ├── baseline.ipynb
│ ├── first_version.ipynb
│ ├── shap_analysis.ipynb
│ └── final_version.ipynb
│
├── src_2/
│ ├── chart
│ │ ├── image
│ │
│ ├── eda
│ │ ├── insight
│
├── Submission/
│ └── submission.csv
├── requirements.txt
└── README.md

| Notebook | Mục đích |
| :--- | :--- |
| baseline.ipynb | File baseline gốc của chương trình |
| first_version.ipynb | File nháp để tham khảo và chỉnh sửa |
| shap_analysis.ipynb | File giải thích mô hình bằng SHAP |
| final_version.ipynb | File để nộp chứa pipeline huấn luyện và sinh submission.csv |

```
---

## Phương pháp
Mô hình chính sử dụng **stacking ensemble** gồm:

- XGBoost — reg:pseudohubererror, depth 4, 2000 estimators
- LightGBM — gradient boosting trên feature bảng
- CatBoost — xử lý tốt categorical features
- Prophet — bắt trend + seasonality theo tuần/năm
Meta-learner: **HuberRegressor** để robust với outlier.

### Feature engineering
- Calendar features: year, month, day, dayofweek, month_sin, month_cos
- Sale season features: 6 đợt sale mỗi năm (tháng 1, 3, 6, 7, 8, 11), is_sale_season, sale_rank, day_to_next_sale, day_since_last_sale,
- Peak season features: 3 peak mỗi năm (tháng 4, 5, 6), is_peak_season, peak_proximity

---

## Chạy repo (Reproduce)
### Chạy trên Kaggle
1. Import notebook [`final_version.ipynb`](https://github.com/Cheetah-lhp/Datathon2026---VinTelligence/blob/main/notebooks/final_version.ipynb) trong cuộc thi trên Kaggle,
2. Sau đó chạy "Run all cells" (**Lưu ý**: chạy trên GPU để tăng tốc quá trình huấn luyện)
3. Khi chạy xong tất cả các cells. Notebook sẽ ghi file kết quả để submit:

   ```
   /kaggle/working/submission.csv
   ```
### Chạy trên local
1. Clone repo
```
git clone https://github.com/Cheetah-lhp/Datathon2026---VinTelligence.git
cd Datathon2026---VinTelligence
```
2. Tạo môi trường và cài thư viện
   
- macOS / Linux
  
```
python -m venv .venv
source .venv/bin/activate
python -m pip install --upgrade pip
python -m pip install -r requirements.txt
```

- Windows

```
python -m venv .venv
.venv\Scripts\activate
python -m pip install --upgrade pip
python -m pip install -r requirements.txt
```

3. Chọn notebook [`final_version.ipynb`](https://github.com/Cheetah-lhp/Datathon2026---VinTelligence/blob/main/notebooks/final_version.ipynb). Chọn kernel nếu cần thiết. Sau đó chạy "Run all cells"
 
4. Lấy file kết quả để submit: [`submission.csv`](https://github.com/Cheetah-lhp/Datathon2026---VinTelligence/blob/main/submission/submission.csv) 

---

## Submission
- Địn dạng giống file [`sample_submission.csv`](https://github.com/Cheetah-lhp/Datathon2026---VinTelligence/blob/main/data/sample_submission.csv)
- File [`submission.csv`](https://github.com/Cheetah-lhp/Datathon2026---VinTelligence/blob/main/submission/submission.csv) nằm trong thư mục *Submission/submission.csv*
