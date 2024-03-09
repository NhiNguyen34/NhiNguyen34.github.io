---
title:  "ViT - Transformers for Image Recognition at Scale [1]"
mathjax: true
layout: post
categories: 
      - Transformers
---

ViT (hay Vision Transformer) được huấn luyện trên lượng lớn dữ liệu (>100M), với tài nguyên tính toán thấp hơn CNN (ResNet), và được được transferred lên nhiều benchmarks dữ liệu hình ảnh, và đạt kết quả mong đợi.

## Kiến trúc Vision Transformer 

### 1. Embedding 
- Hình ảnh được chia thành các mảnh cố định có kích thước là (P, P) và được làm phẳng bằng cách nối các kênh màu lại với nhau.
- Mảnh này sau đó được truyền qua một lớp Feed-Forward với hàm kích hoạt tuyến tính để nhận được một chiếu mảnh tuyến tính có kích thước [D, 1].
- [class] token được thêm vào tập hợp các token hình ảnh và chịu trách nhiệm cho việc **aggregating global image information and final classification** (tổng hợp thông tin toàn bộ và phân loại cuối cùng). Nó có khả năng học được tổng hợp global trong quá trình truyền qua và học qua các lớp chú ý.
- Tại sao việc mã hóa vị trí là cần thiết? ⇒ Thêm một phần encoding positional vào các mảnh hình ảnh được để theo dõi chuỗi. Vì nếu không làm vậy sẽ bị mất thông tin hình ảnh liên tục khi chia thành patches.
### 2. Transformer Encoder 
### 3. MLP Head (Đầu ra Multi Layer Perceptron)
## Q&A:
1. Tại sao chiến lược optimization là tăng ở 4000 epoch đầu, và giảm dần về sau?
