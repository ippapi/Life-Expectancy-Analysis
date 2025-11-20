<!-- Banner -->
<p align="center">
  <a href="https://www.uit.edu.vn/" title="Trường Đại học Công nghệ Thông tin" style="border: none;">
    <img src="https://i.imgur.com/WmMnSRt.png" alt="Trường Đại học Công nghệ Thông tin | University of Information Technology">
  </a>
</p>

# Life Expectancy Analysis – Nhóm 20

## Giới Thiệu Tổng Quan

Đây là đồ án cuối kỳ môn **Phân Tích Dữ Liệu – IE224** của sinh viên trường Đại học Công nghệ Thông tin – ĐHQG.  
Đề tài tập trung phân tích các yếu tố ảnh hưởng đến **chỉ số tuổi thọ trung bình (Life Expectancy)** của 179 quốc gia giai đoạn 2000–2015.  
Nhóm sử dụng **Pandas, Plotly, Matplotlib, Scikit-learn** để xử lý dữ liệu, trực quan hóa và xây dựng mô hình học máy.

Dữ liệu được tham khảo từ bộ **Life Expectancy (WHO) Fixed – Kaggle** và được nhóm xử lý, phân tích, trực quan hóa, chọn đặc trưng và xây dựng mô hình dự đoán.

## Thành Viên Nhóm

| STT | Tên              | MSSV     | Vai Trò        |
| --- | ---------------- | -------- | -------------- |
| 1   | Phạm Trung Nguyên| 22520983 | Thành viên     |
| 2   | Bùi Thanh Phong  | 22521082 | Thành viên     |
| 3   | Vũ Thanh Phong   | 22521095 | Thành viên     |
| 4   | Trương Hồng Phúc | 22521144 | Thành viên     |

## Công Nghệ Sử Dụng

- **Ngôn ngữ**: Python  
- **Thư viện xử lý dữ liệu**: Pandas  
- **Thư viện trực quan hóa**: Matplotlib, Plotly  
- **Thư viện mô hình**: Scikit-learn  
- **Các kỹ thuật sử dụng**:  
  - ANOVA  
  - Pearson Correlation  
  - Regression Plot  
  - Linear Regression, Ridge Regression  
  - Grid Search + Cross-validation  
  - Partial Residual Plot đa biến (tự xây dựng)

## Nội Dung Chính

### Phân Tích Dữ Liệu (EDA)
- Kiểm tra dữ liệu sạch, kiểu dữ liệu  
- Phân tích tương quan giữa các biến  
- ANOVA cho biến phân loại  
- Trực quan hoá:
  - Biểu đồ tương quan (heatmap)
  - Regression plot
  - Boxplot (theo khu vực, trạng thái phát triển)
  - Life Expectancy theo các năm

### Lựa Chọn Đặc Trưng
Nhóm chọn được **11 đặc trưng quan trọng nhất** dựa trên:
- Tương quan
- ANOVA
- Regression Plot
- Phát hiện đa cộng tuyến

### Mô Hình Hóa
Huấn luyện 2 mô hình:
- Linear Regression  
- Ridge Regression (giải quyết Multicollinearity + giảm overfitting)

Tối ưu **alpha** bằng Grid Search 5-fold.

### Đánh Giá
- Sử dụng MSE và R²-score  
- So sánh mô hình khi:
  - Dùng toàn bộ 20 đặc trưng  
  - Dùng 11 đặc trưng đã chọn  
  - Dùng từng đặc trưng đơn lẻ (Adult_mortality, GDP_per_capita)

### Kết Quả Nổi Bật

| Trường hợp | Số đặc trưng | MSE | R² | Ghi chú |
|-----------|--------------|-----|-----|---------|
| Full features | 20 | ~0.209 | 0.9976 | Độ chính xác gần tuyệt đối |
| Selected features | 11 | ~0.259 | 0.9971 | Gần tương đương nhưng ít đặc trưng hơn |
| Only Adult_mortality | 1 | 9.20 | 0.898 | Ảnh hưởng rất mạnh |
| Only GDP_per_capita | 1 | 60.18 | 0.334 | Ảnh hưởng trung bình |

### 🔬 Partial Residual Plot (tự xây dựng)
- Giúp kiểm tra quan hệ tuyến tính khi có nhiều biến  
- Dễ phát hiện outliers  
- Minh chứng được mức độ ảnh hưởng của từng đặc trưng
