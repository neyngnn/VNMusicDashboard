# 🎵 VNMusicDashboard - Phân Tích & Trực Quan Hóa Dữ Liệu Spotify Việt Nam  

## 📌 Giới Thiệu  
Dự án **VNMusicDashboard** là một hệ thống phân tích và trực quan hóa dữ liệu âm nhạc Việt Nam trên nền tảng Spotify. Dữ liệu được thu thập từ Spotify, làm sạch và xử lý để tạo ra các biểu đồ và bảng điều khiển (**dashboard**) giúp theo dõi xu hướng âm nhạc tại Việt Nam theo từng năm.  

## 🎯 Mục Tiêu  
- **Phân tích xu hướng âm nhạc Việt Nam** qua dữ liệu từ Spotify.  
- **Xác định mức độ phổ biến** của các nghệ sĩ, thể loại nhạc, và bài hát.  
- **Trực quan hóa dữ liệu** bằng các biểu đồ và dashboard tương tác.  
- **Cung cấp insight** để hỗ trợ nhà sản xuất, nhạc sĩ và người yêu nhạc nắm bắt xu hướng.  

---

## 📊 Bộ Dữ Liệu  
### 📝 Nguồn dữ liệu  
- Dữ liệu được lấy từ nền tảng **Spotify** thông qua API.  
- Chỉ bao gồm các bài hát tiếng Việt để đảm bảo tập trung vào thị trường Việt Nam.  

### 📌 Các bước xử lý dữ liệu  
1. **Lọc trùng lặp** (Dựa trên `track_uri`).  
2. **Loại bỏ bài hát nước ngoài** (Dựa trên `track_name` và `artist_name`).  
3. **Xóa bài hát quá ngắn** (Dựa trên `duration_ms`).  
4. **Lọc bài hát không lời** (Dựa trên `instrumentalness`).  
5. **Chuẩn hóa thể loại nhạc** (Gộp các thể loại tương đồng, sử dụng One-Hot Encoding).  

Sau khi xử lý, tập dữ liệu còn **2,456 dòng** với **26 cột**, gồm:  
- `track_uri`, `track_name`, `artist_name`, `artist_pop`, `artist_genres`, `album`, `track_pop`, `danceability`, `energy`, `key`, `loudness`, `mode`, `speechiness`, `acousticness`, `instrumentalness`, `liveness`, `valence`, `tempo`, `duration_ms`, `year`, `genre1`, `genre2`, `genre3`, …  

---

## 📊 Dashboard Trực Quan  
Dashboard được xây dựng bằng **Power BI**, gồm nhiều loại biểu đồ:  
✔ **Biểu đồ đường**: Xu hướng thay đổi theo thời gian (sự phổ biến của bài hát theo tháng).  
✔ **Biểu đồ cột**: Số lượng album phát hành theo quý, độ phổ biến của nghệ sĩ.  
✔ **Biểu đồ doughnut**: Phân phối thể loại nhạc chính.  
✔ **Biểu đồ radar**: Phân tích đặc điểm âm nhạc của một bài hát.  
✔ **Biểu đồ cây**: Sắp xếp album theo độ phổ biến.  
✔ **Gauge chart**: Chỉ số đo lường bài hát/nghệ sĩ.  

### 📌 Tính Năng Chính  
✅ **Tương tác linh hoạt**: Nhấp vào biểu đồ để xem chi tiết từng nghệ sĩ, thể loại, hoặc bài hát.  
✅ **Bộ lọc mạnh mẽ**: Chọn năm, nghệ sĩ, thể loại để phân tích theo góc nhìn mong muốn.  
✅ **Điều hướng đơn giản**: Giao diện thân thiện, dễ sử dụng với thanh điều hướng.  

---

## 🚀 Công Nghệ Sử Dụng  
- **Power BI**: Trực quan hóa dữ liệu và tạo dashboard.  
- **Python (Jupyter Notebook)**: Thu thập và tiền xử lý dữ liệu.  
- **Spotify API**: Lấy dữ liệu bài hát, nghệ sĩ từ Spotify.  

---

## 📂 Cấu Trúc Dự Án  
```
📂VNMusicDashboard
├──📂source
│   ├──📜 crawl_data.ipynb 
│   └──📜 data_preprocessing.ipynb
│──📜dashboard.pbix               
│──📜report.docx                 
│──📜slide.pdf 
└──📜README.md
```
