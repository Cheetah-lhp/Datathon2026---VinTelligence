# VinTelligence Datathon 2026 — The Gridbreakers

**Bài toán**: Dự báo doanh thu và COGS hàng ngày, giai đoạn 01/01/2023 – 01/07/2024
 https://www.kaggle.com/competitions/datathon-2026-round-1
 
**Đội thi**: _**The Forecasters**_

**Thành viên**: _**Lâm Huy Vũ**_, Lê Hoàng Phúc, Hoàng Phương Dung, Phạm Xuân Tuấn

## Cấu trúc thư mục
```
DATATHON2026/
├── data/datathon-2026-round-1 (các file data gốc của cuộc thi)
├── notebooks/
│ ├── datathon26-mcqs.ipynb # Giải các câu MCQ phân tích dữ liệu (thêm sau)
│ ├── baseline.ipynb # Baseline đơn giản (seasonal average + trend)
│ ├── first_version.ipynb # File nháp để tham khảo và chỉnh sửa (no shap, trend + ML)
│ ├── shap_analysis.ipynb # Shap analysis cho các base models (thêm sau)
│ └── final_version.ipynb # Pipeline chính: stacking XGB + LGB + CatBoost + Prophet
├── Submission/
│ └── submission.csv
└── README.md
```
## Phương pháp
abc xyz(thêm sau)

## Sử dụng (Reproduce)
1. Tạo và import notebook trong cuộc thi trên Kaggle,
2. Sau đó chạy "Run all cells" (**Lưu ý**: chạy trên GPU để tăng tốc quá trình huấn luyện)
3. Khi chạy xong tất cả các cells. Notebook sẽ ghi file"

   ```
   /kaggle/working/submission.csv
   ```

| Notebook | Mục đích |
| :--- | :--- |
| baseline.ipynb | File baseline gốc của chương trình |
| first_version.ipynb | File nháp để tham khảo và chỉnh sửa |
| shap_analysis.ipynb | File giải thích mô hình bằng SHAP |
| final_version.ipynb | File để nộp chứa pipeline huấn luyện và sinh submission.csv |

## Submission
- File submission nằm trong thư mục *Submission/submission.csv*
- Link kaggle + score leaderboard(thêm sau)
