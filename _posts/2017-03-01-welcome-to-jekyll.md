---
title:  "Transformers, BERT, Q&A"
mathjax: true
layout: post
categories: 
      - Transformers
---
## BERT

BERT -> học cách biểu diễn ngôn ngữ sử dụng transformers -> đặc biệt encoder của transformers


## Thành phần trong BERT

### Embedding: 
* Từ được lấy và đưa về số chiều thấp. Làm sao để embed từ one-hot representation thành lower dimensional space? => cần có embedding matrix.
* One-hot representation sẽ đại diện cho từ xuất hiện trong câu, embedding matrix sẽ có số chiều là (vocab_size, embed_dim) => nhân ma trận ta được vector biểu diễn của một từ. 
*	Embedding_size của BERT là 768.
![embedding](https://github.com/NhiNguyen34/NhiNguyen34.github.io/assets/118429842/5a0f39e9-62d4-4d32-870f-11694be59511)
*	Dùng nn.Embedding layer: cách hoạt động mô tả tương tự ở trên, dung word_idx sao đó ánh xạ thành số chiều (vocab_size, embed_size)

### Positional Encoding: 
*	Cơ chế chú ý đa đầu góp phần speed- up training times => no any sense if position for each word. => positional embeddings => sinusoid

###	Attention Block:
![image](https://github.com/NhiNguyen34/NhiNguyen34.github.io/assets/118429842/4e53e03e-a2c6-4f56-8da3-98296664f389)
*	Phép nhân ma trận trả về sự tương quan => QK.T sẽ cho biết Q cần attention bao nhiêu đối với K.T (Nếu là self attention thì có thể hiểu là mỗi từ sẽ có tương quan-ảnh hưởng-chú ý như nào với nhau)
*	Softmax => probability distribution, quá trình backprop ít bị ảnh hưởng.
*	Sprt(d_k):	large_variances => kill gradients

###          Multihead-Attention:
*  Tại sao cần nhiều hơn một attention head?
*   Do kết quả của hàm softmax có thể chỉ tập trung vào một phần tử duy nhất mà đánh mất việc các phần khác cũng có ý nghĩa quan trọng => cần nhiều heads => Nếu vậy số lượng heads càng nhiều thì sẽ tìm được càng nhiều sự tương quan?
*   Solution: đồng thời nhiều heads cùng chạy => cho phép xem xét nhiều từ ngữ trước đó đồng thời khi dự đoán từ tiếp theo.
*   Lower-dimensional embedding space:
       *   	d_embed: chiều của token embedding space.
       *   	d_k: chiều của key và query (d_embed // h)
       *   	d_v: chiều của value
      *   	h: số heads
### Feedforward
### Skip connection & Layer Norm
*  Skip connection => keep gradient smooth => backprop
*   Layer Norm => mean = 0 , std = 1 => duy  trì một phân phối nhất quán => encourage convergence of parameter values + better perf 

[Source Code](https://colab.research.google.com/drive/1_OnhkDzFyhW7bkc0zbBcIy0EV3clPOMk?usp=sharing)

------
## Q&A:
1. Nếu vậy số lượng heads càng nhiều thì sẽ tìm được càng nhiều sự tương quan?


## References:
1.[Paper](https://arxiv.org/abs/1810.04805)
2.[Pytorch loss backward and optimizer](https://stackoverflow.com/questions/53975717/pytorch-connection-between-loss-backward-and-optimizer-step)
