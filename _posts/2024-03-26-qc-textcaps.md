---
title:  "Question-controlled Text-aware Image Captioning, Q&A"
mathjax: true
layout: post
categories: 
      - Transformers
---


## Automatic Dataset Construction

![image](https://github.com/NhiNguyen34/NhiNguyen34.github.io/assets/118429842/4adf8634-e6e6-4abb-94eb-b657e15bed1b)

### Overview về dataset

- Đầu vào và đầu ra của bài toán TextCaps thông thường sẽ là `<I, Y>`.
- Với nghiên cứu về của tác giả, đầu vào bài toán trở thành `<I, C_ini, Q, Y>`. Cụ thể trong đó C_ini và Q được thêm vào, vai trò của từng thành phần trở thành:
  - I: Image
  - C_ini: Caption no scene-text
  - Q: Question
  - Y: Caption scene-text
   
### Initial Caption Generation: 
- major visual object (w/o scene-text)
- initial captions show mention scene-text.
- Cách khởi tạo C~_init:
  - Phát hiện văn bản cảnh trong Y
    - Xác định từ trong Y là từ văn bản cảnh (tạm gọi là từ_Y1)
    - Chạy OCR trên ảnh và so sánh kết quả OCR với từ_Y1
  - Loại bỏ văn bản cảnh:
    - sử dụng bộ phân tích cú pháp phụ thuộc (syntactic dependency parser) Spacy2 để xây dựng cây phụ thuộc (dependency tree) và cắt tỉa các nhánh chứa văn bản cảnh (scene text). 

- Tổng quan qui trình: Extract C~_ini (I, Y) → (train) model - AoANet → C_ini

### Question Generation 

- T5 → tạo câu hỏi-câu trả lời từ Y
- Filter: Do một số cặp câu hỏi - trả lời không liên quan đến văn bản cảnh, nên chúng ta lọc ra các cặp này bằng cách kiểm tra xem câu trả lời có thể được tìm thấy trong kết quả nhận dạng ký tự quang học (OCR) không.
- Bên cạnh đó, các câu hỏi về một văn bản cảnh có thể chứa các câu trả lời dạng văn bản cảnh từ các câu hỏi khác hoặc mô tả đối tượng bổ sung không có trong chú thích ban đầu, điều này làm rò rỉ thông tin groundtruth cho mô hình và cần tránh.

## Proposed Method (GQAM)
![image](https://github.com/NhiNguyen34/NhiNguyen34.github.io/assets/118429842/66c52741-6779-435b-b10c-3425ff9455f1)

- (Tích hợp thông tin địa lí vào quá trình encode ảnh) → kết hợp region-level (obj f + ocr f) = spatial relationship.
- Q-guided encoder → relevant visual f
- Multimodal decoder → personalized text-aware caption.
- Tóm gọn lại:
      - Bộ mã hóa hình ảnh theo hình học (Geometry-informed Visual Encoder) kết hợp các đặc trưng vùng đối tượng và đặc trưng vùng văn bản cảnh với thông tin hình học tương đối. (region obj features và scene text region features)
      - Bộ mã hóa theo câu hỏi (Question-guided Encoder) lựa chọn động các đặc trưng hình ảnh liên quan để mã hóa các câu hỏi. (select relevants visual features to encode questions)
      - Bộ giải mã đa phương thức (Multimodal Decoder) nhận đầu vào là các đặc trưng hình ảnh, câu hỏi và chú thích ban đầu để tuần tự tạo ra chú thích có nhận biết văn bản cho câu hỏi. (visual - question - initial captions features → caption)

### Geometry-informed Visual Encoder
![image](https://github.com/NhiNguyen34/NhiNguyen34.github.io/assets/118429842/87aa583a-e03f-44ab-8f1a-bb852233046b)

### Question-guided Encoder
![image](https://github.com/NhiNguyen34/NhiNguyen34.github.io/assets/118429842/a33f4327-892c-4910-b84c-17f4c1fdf853)
![image](https://github.com/NhiNguyen34/NhiNguyen34.github.io/assets/118429842/47e0626a-7d94-4e69-88d1-d220fb38997a)

### Multimodal Decoder
![image](https://github.com/NhiNguyen34/NhiNguyen34.github.io/assets/118429842/72e89b81-6a97-46d6-8d55-87982b0f1ee1)


[Source Code](https://github.com/HAWLYQ/Qc-TextCap)
[Paper](https://arxiv.org/pdf/2108.02059.pdf)

------
## Q&A:
1. Sử dụng bộ phân tích cú pháp phụ thuộc (syntactic dependency parser) Spacy2 để xây dựng cây phụ thuộc (dependency tree) và cắt tỉa các nhánh chứa văn bản cảnh (scene text). -> Liệu bước filter này có thể sử dụng được trên dữ liệu tiếng Việt không?
