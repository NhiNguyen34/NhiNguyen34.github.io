---
title:  "ViT - Transformers for Image Recognition at Scale [1]"
mathjax: true
layout: post
categories: 
      - Transformers
---
![image](https://github.com/NhiNguyen34/NhiNguyen34.github.io/assets/118429842/998a78d6-550e-4fee-84af-ac89ea876956)

ViT (hay Vision Transformer) được huấn luyện trên lượng lớn dữ liệu (>100M), với tài nguyên tính toán thấp hơn CNN (ResNet), và được được transferred lên nhiều benchmarks dữ liệu hình ảnh, và đạt kết quả mong đợi.

## Kiến trúc Vision Transformer 
![image](https://github.com/NhiNguyen34/NhiNguyen34.github.io/assets/118429842/2abc072c-bc4c-4a55-a117-94e99344e3e8)

### 1. Embedding 
- Hình ảnh được chia thành các mảnh cố định có kích thước là (P, P) và được làm phẳng bằng cách nối các kênh màu lại với nhau.
- Mảnh này sau đó được truyền qua một lớp Feed-Forward với hàm kích hoạt tuyến tính để nhận được một chiếu mảnh tuyến tính có kích thước [D, 1].
- [class] token được thêm vào tập hợp các token hình ảnh và chịu trách nhiệm cho việc **aggregating global image information and final classification** (tổng hợp thông tin toàn bộ và phân loại cuối cùng). Nó có khả năng học được tổng hợp global trong quá trình truyền qua và học qua các lớp chú ý.
- Tại sao việc mã hóa vị trí là cần thiết? ⇒ Thêm một phần encoding positional vào các mảnh hình ảnh được để theo dõi chuỗi. Vì nếu không làm vậy sẽ bị mất thông tin hình ảnh liên tục khi chia thành patches.
### 2. Transformer Encoder 
![image](https://github.com/NhiNguyen34/NhiNguyen34.github.io/assets/118429842/8d39b83d-22c6-4685-8b6b-b828be096f38)

- Kiến trúc Transformer Encoder tương tự như đã được đề cập trong bài báo "ATTENTION IS ALL YOU NEED". Nó được tạo thành từ nhiều cấp xếp của các khối giống nhau. Mỗi khối bao gồm một lớp Multi-Head Attention tiếp theo là một lớp Feed-Forward. Có một Residual Connection quanh mỗi trong hai lớp con, tiếp sau là Layer Normalization. Tất cả các lớp con cũng như các lớp embedding trong mô hình tạo ra một đầu ra có chiều embedded là D.
- Vector Z từ bước trước (phần Embedding [1]) được truyền qua kiến trúc Transformer Encoder để nhận được vector ngữ cảnh C.
### 3. MLP Head (Đầu ra Multi Layer Perceptron)
- Khi đã có vector ngữ cảnh C của chúng ta, chúng ta chỉ quan tâm đến [ c0] cho mục đích phân loại. Token [c0] này được truyền qua một đầu MLP để cho chúng ta vector xác suất cuối cùng để giúp dự đoán.
- Đầu MLP được thực hiện với một hidden layer và tanh ở giai đoạn pretraining stage và bằng một lớp single linear ở giai đoạn fine-tuning.
### Tại sao ViT hoạt động tốt hơn CNN? 
Bởi vì Multi-Head Attention trong Vision Transformers giúp nó chỉ tập trung vào phần của hình ảnh có liên quan. Nếu chúng ta lấy trung bình của đầu ra của tất cả các đầu attention, chúng ta có thể thấy cơ chế này hoạt động. Mô hình tập trung vào các vùng hình ảnh có ý nghĩa ngữ nghĩa cho việc phân loại.
### Tổng hợp: 
Kiến trúc cuối cùng được hiển thị trong sơ đồ đầu bài. Các mảnh hình ảnh tuyến tính được thêm vào bằng một token [CLS] và truyền qua một Dense Layer để nhận được vector mã hóa cuối cùng Z cùng với các encoding positinal. Sau đó, điều này được truyền qua một kiến trúc mã hóa Transformer để nhận được vector ngữ cảnh C. Giá trị của token ngữ cảnh c0 được truyền qua một đầu MLP để nhận được dự đoán cuối cùng.
## Q&A:
1. Tại sao nói về việc các mô hình CNN(ResNet hay VGG) có tính chất local và translationally equivariant lại dẫn đến việc ViT đạt kết quả khả quan hơn?
