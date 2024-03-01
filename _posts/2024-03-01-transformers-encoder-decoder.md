---
title:  "Transformers - Encoder & Decoder"
mathjax: true
layout: post
categories: 
      - Transformers
---

<img width="216" alt="image" src="https://github.com/NhiNguyen34/NhiNguyen34.github.io/assets/118429842/16d73a7e-dcec-404b-b936-1ade2be9d971">


## Cơ chế Attention
<img width="271" alt="image" src="https://github.com/NhiNguyen34/NhiNguyen34.github.io/assets/118429842/cc60cd07-f8e5-4237-b5d8-b8fb95bded22">

* Mục tiêu: Khả năng biết được những từ nào nên chú ý đến được học trong quá trình huấn luyện thông qua lan truyền ngược.
* Mạng RNN, LSTM hay GRU cũng có khả năng xem xét các đầu vào trước đó. Nhưng sức mạnh của cơ chế Attention là nó không gặp vấn đề về bộ nhớ ngắn hạn.
* Hiểu đơn giản, encoder sẽ maps câu đầu vào thành một biểu diễn trừu tượng. Decoder sẽ lấy biểu diễn đó và generates ra từng output khi đưa output trước vào (autoregressive).
  
## Input Embeddings & Positional Encoding

* Embedding có thể được coi như một bảng tra cứu để lấy một biểu diễn vector đã học của mỗi từ.  Từ đó ánh xạ qua câu input đầu vào.

* Bước tiếp theo là thêm thông tin vị trí vào các nhúng từ. Điều này được thực hiện bằng cách sử dụng mã hóa vị trí. Các tác giả đã đề xuất một thủ thuật thông minh bằng cách sử dụng các hàm sin và cosine. Hàm sin và cos được chọn cùng nhau vì chúng có các tính chất tuyến tính mà mô hình có thể dễ dàng học để chú ý đến.
<img width="270" alt="image" src="https://github.com/NhiNguyen34/NhiNguyen34.github.io/assets/118429842/7526bd2d-40fc-48b2-bd70-aca0aedba24b">


## Encoder
### Introduction
* Bao gồm 2 sub-module (multi-headed attention, followed by a fully connected network, residual connection, layer normalization). Có tất cả N-layers (trong paper nhóm tác giả đề cập là 6.)
<img width="225" alt="image" src="https://github.com/NhiNguyen34/NhiNguyen34.github.io/assets/118429842/d7d9dd40-9d0f-45e9-84fb-1a3f38200983">

### Architecture

#### Multi-head Attention
* Multi-head Attention trong encoder áp dụng một cơ chế chú ý cụ thể được gọi là Self-attention, cho phép các mô hình liên kết mỗi từ trong đầu vào với các từ khác.
<img width="175" alt="image" src="https://github.com/NhiNguyen34/NhiNguyen34.github.io/assets/118429842/49c5b785-52c5-4f23-a0f3-068074d3b2f1">

#### Add & Norm Layer & Residual Layer & Point-wise feed forward network
* Multi-headed attention output vector được thêm vào nhúng từ đầu vào vị trí ban đầu. Điều này được gọi là residual connection. Đầu ra của residual connection đi qua một  layer normalization. (Có một số gợi ý có thể sầi Group Normalization)
* The normalized residual output được chiếu qua một pointwise feed-forward network. The pointwise feed-forward network bao gồm một vài lớp tuyến tính với một hàm kích hoạt ReLU. Đầu ra của đó sau đó được thêm vào đầu vào của pointwise feed-forward network và tiếp tục được chuẩn hóa.

## Decoder
### Introduction
* These sub-layers behave similarly to the layers in the encoder but each multi-headed attention layer has a different job ⇒ Cơ bản giống với Decoder nhưng khác chỗ nhiệm vụ của multihead-attention.
* Decoder: autoregressive
### Architecture
#### Decoder input embeddings & Positonal Encoding 
#### Multi-head Attention (1)
#### Multi Attention (2) & Point-wise Feed Forward Layer
#### Linear Classifier and Final Softmax for Output Probabilities
* Encoder cũng có thể được xếp chồng với N lớp, mỗi lớp nhận đầu vào từ decoder và các lớp encoder trước đó. Bằng cách xếp chồng các lớp, mô hình có thể học được cách trích xuất và tập trung vào các kết hợp khác nhau của sự chú ý từ các đầu chú ý của nó, có thể tăng cường hiệu suất dự đoán.
<img width="260" alt="image" src="https://github.com/NhiNguyen34/NhiNguyen34.github.io/assets/118429842/50c282b6-c6ef-4b19-a1c4-51471a2fddeb">
#### Training & Inference
* Training: Truyền câu grouth-truth vào decoder. Tính loss giữa output và grout-truth
* Inference: Truyền output trước đó vào decoder để dự đoán từ tiếp theo.
* 
## Q&A:
1. Tại sao chiến lược optimization là tăng ở 4000 epoch đầu, và giảm dần về sau?


