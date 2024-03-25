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
[Source Code](https://colab.research.google.com/drive/1_OnhkDzFyhW7bkc0zbBcIy0EV3clPOMk?usp=sharing)
[Paper](https://arxiv.org/abs/1810.04805)

------
## Q&A:
1. Sử dụng bộ phân tích cú pháp phụ thuộc (syntactic dependency parser) Spacy2 để xây dựng cây phụ thuộc (dependency tree) và cắt tỉa các nhánh chứa văn bản cảnh (scene text). -> Liệu bước filter này có thể sử dụng được trên dữ liệu tiếng Việt không?
