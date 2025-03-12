# Scene Text Recognition - Project

## Giới thiệu
Dự án **Scene Text Recognition** nhằm phát triển một hệ thống nhận diện văn bản trong ảnh, sử dụng:
- **YOLO** cho tác vụ phát hiện văn bản (Text Detection).
- **CRNN (Convolutional Recurrent Neural Networks)** cho tác vụ nhận diện chữ (Text Recognition).

Dự án được thực hiện trong khuôn khổ **AI VIET NAM - COURSE 2024**.

## Ứng dụng
Hệ thống có thể được áp dụng trong nhiều lĩnh vực như:
- Xử lý tài liệu số hóa.
- Tìm kiếm và thu thập dữ liệu từ ảnh chứa văn bản.
- Tự động hóa quy trình xử lý văn bản.

---

## Hướng dẫn cài đặt

### 1. Cài đặt môi trường
Để chạy dự án, hãy đảm bảo bạn đã cài đặt Python >= 3.8 và các thư viện cần thiết.
Bạn có thể cài đặt tất cả thư viện bằng lệnh sau:

```bash
pip install -r requirements.txt
```

### 2. Cấu trúc thư mục
```
OCR_Project/
│── data/                   # Chứa dataset gốc và preprocessed
│   ├── train/
│   ├── val/
│   ├── test/
│── models/                 # Chứa các mô hình
│   ├── yolo.pt             # Model YOLO đã train
│   ├── crnn.pt             # Model CRNN đã train
│── utils/                  # Các công cụ hỗ trợ
│   ├── dataset.py          # Load dataset, chuyển đổi định dạng YOLO
│   ├── yolo_utils.py       # Hàm train & infer YOLO
│   ├── crnn_utils.py       # Hàm train & infer CRNN
│   ├── text_pipeline.py    # Tích hợp YOLO + CRNN         
│── requirements.txt        # Danh sách thư viện cần thiết
│── README.md               # Tài liệu hướng dẫn
```

### 3. Tải dữ liệu
Bộ dữ liệu được sử dụng là **ICDAR 2003**.
Bạn có thể tải dữ liệu từ liên kết sau:
🔗 [Dataset Download](https://drive.google.com/file/d/1kUy2tuH-kKBlFCNA0a9sqD2TG4uyvBnV/view)

Sau khi tải về, hãy đặt dữ liệu vào thư mục `data/`.

---

## Huấn luyện mô hình

### Huấn luyện mô hình **Text Detection (YOLO)**:
```bash
python utils/yolo_utils.py --train --data data/train/
```

### Huấn luyện mô hình **Text Recognition (CRNN)**:
```bash
python utils/crnn_utils.py --train --data data/train/
```

---

## Sử dụng mô hình
Sau khi huấn luyện, bạn có thể chạy thử nghiệm hệ thống trên một ảnh bất kỳ:
```bash
python utils/text_pipeline.py --image_path path/to/image.jpg
```
Hệ thống sẽ phát hiện văn bản trong ảnh và hiển thị nội dung nhận diện được.

---

## Tác giả
Dự án lấy ý tưởng từ nhóm **AI VIET NAM - 2024**.
Mọi thắc mắc hoặc góp ý, vui lòng liên hệ qua email: **support@aivietnam.edu.vn**.
Rất cảm ơn nhóm AIO.
