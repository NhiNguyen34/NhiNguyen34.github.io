---
title:  "Dependency Parsing, Q&A"
mathjax: true
layout: post
categories: 
      - Annotating Linguistic Structure
---
## 1. Syntactic Structure?

- Câu trúc câu là một phần quan trọng của ngôn ngữ vì nó cung cấp cấu trúc và tổ chức cho thông điệp được truyền đạt.
### Tại sao cần cấu trúc câu? 
- Ý tưởng giao tiếp thông thường tương đối phức tạp được cấu thành từ nhiều units nhỏ thành units lớn để diễn giải.
- Mô hình cần hiểu cấu trúc câu để có thể diễn giải đúng. (*)

### Một số vấn đề gây lầm về cấu trúc ngôn ngữ sai:
- Prepositional phrase attachment ambiguity (Nhập nhằng liên quan giới từ)
- PP attachment ambiguities multiply (Nhập nhằng liên quan nhiều cụm giới từ)
- Coordination scope ambiguity (Nhập nhằng liên quan phạm vi ngắt câu)
- Adjectival/Adverbial Modifier Ambiguity
- Verb Phrase (VP) attachment ambiguity (Nhập nhằng liên quan cụm động từ)


### HAI QUAN ĐIỂM VỀ CẤU TRÚC NGÔN NGỮ:
○ Constituency = phrase structure grammars = context-free grammars
      § Constituency: cấu trúc ngôn ngữ hiểu dựa trên thành phần tạo thành
      § CFGs: Context-free grammars - Cấu trúc ngữ pháp không dựa trên ngữ cảnh
      § Words >> phrase >> bigger phrase 
○ Dependency structure: cho thấy sự phụ thuộc của từ vào từ khác (Modified, attach to, arguments of)

## 2. Dependency Grammar and Dependency Structure

'"Dependency syntax" là một lý thuyết ngữ pháp văn phạm mà cho rằng cấu trúc cú pháp bao gồm các mối quan hệ giữa các thành phần từ vựng, thường là các mối quan hệ nhị phân không đối xứng (còn gọi là "mũi tên") được gọi là các "dependency".'
- Mỗi câu sẽ có một ROOT. Thường chúng ta sẽ thêm một note [ROOT] để toàn bộ từ đều có sự phụ thuộc.
### Dependency Parsing
- Một câu được phân tích cú pháp bằng cách mỗi từ lựa chọn từ mà nó phụ thuộc vào từ nào khác (bao gồm cả ROOT).
- Thường có một số ràng buộc:
      - Chỉ có một từ là phụ thuộc của ROOT.
      - Không muốn có chu trình như A → B, B → A.

## 3. Notes:
- Typed dependency structure: nhãn. Cụ thể: 
	- nsubj: Chủ ngữ, từ hoặc cụm từ làm chủ động trong câu.
	- obj: Đối tượng, từ hoặc cụm từ làm đối tượng của hành động trong câu.
	- root: Từ gốc của câu.
	- amod: Tính từ mô tả danh từ.
	- nmod: Cụm từ động từ hoặc danh từ phụ thuộc vào danh từ hoặc động từ khác.
	- advmod: Tính từ hoặc trạng từ mô tả động từ, tính từ, hoặc trạng từ khác.
	- acl: Mệnh đề động từ phụ thuộc vào một danh từ hoặc động từ khác.
	- cop: Động từ "to be" hoặc tương đương.
	- det: Định từ xác định hoặc không xác định.
	- punct: Dấu câu.
	- aux: Từ hỗ trợ, thường đi kèm với động từ chính.
	- case: Giới từ hoặc trạng từ quyết định cấu trúc ngữ pháp.
	- cc: Liên từ nối các thành phần của câu.
	- conj: Liên kết các thành phần câu tương đương.
	- dep: Phụ thuộc không xác định hoặc không rõ ràng.

- Ví dụ:
<img width="518" alt="image" src="https://github.com/NhiNguyen34/NhiNguyen34.github.io/assets/118429842/ea67558d-4afc-423d-b7e9-3afac0a47fae">


- Động từ:
      - Có: động từ chính, thể hiện trạng thái sở hữu.
      - In: động từ phụ, thể hiện hành động.
  
- Object:
      - Khung màu xanh dương: tân ngữ của động từ "có".
      - Dòng chữ mắm thái squid brand 700ml màu đen trên nền trắng: tân ngữ của động từ "in".
  
- Subject:
      - Bảng hiệu: chủ ngữ của câu.
  
- Thống kê:
	- Số lượng từ: 20
	- Số lượng danh từ: 8
	- Số lượng động từ: 2
	- Số lượng tính từ: 5
	- Số lượng giới từ: 1

- Phân tích chi tiết:
	- Câu này có cấu trúc chủ ngữ - vị ngữ.
	- Vị ngữ bao gồm một động từ chính ("có") và hai động từ phụ ("in", "trên").
	- Các phụ thuộc được sắp xếp theo thứ tự logic, giúp cho câu dễ hiểu.

[Source Code]
[Slide]([https://arxiv.org/abs/1810.04805](https://web.stanford.edu/class/cs224n/slides/cs224n-2021-lecture04-dep-parsing.pdf)https://web.stanford.edu/class/cs224n/slides/cs224n-2021-lecture04-dep-parsing.pdf)






