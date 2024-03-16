---
title:  "Pooling Operations"
mathjax: true
layout: post
categories: media
---

## Generalized Mean Pooling
<img width="247" alt="image" src="https://github.com/NhiNguyen34/NhiNguyen34.github.io/assets/118429842/548316ea-dd19-40d4-96a1-f07db14ddfab">

* Generalized Mean Pooling (GeM) tính trung bình tổng quát của mỗi kênh trong một tensor. GeM là một sự tổng quát hóa của phép lọc trung bình thường được sử dụng trong các mạng phân loại và của lớp max-pooling không gian.
## Global Average Pooling
* Global Average Pooling là một phép gom nhóm được thiết kế để thay thế các lớp kết nối đầy đủ trong CNN cổ điển. Ý tưởng là tạo ra một bản đồ đặc trưng cho mỗi danh mục tương ứng của nhiệm vụ phân loại trong lớp mlpconv cuối cùng. Thay vì thêm các lớp kết nối đầy đủ lên trên các bản đồ đặc trưng, chúng ta lấy trung bình của mỗi bản đồ đặc trưng, và vectơ kết quả được đưa trực tiếp vào lớp softmax.

