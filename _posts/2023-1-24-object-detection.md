---
layout: post
title: 4 - Object Detection
categories : General
author: Nguyen Quoc Khanh
---

<br>

Về bản chất, các nhiệm vụ thị giác máy tính là làm cho máy tính hiểu được hình ảnh kỹ thuật số cũng như dữ liệu trực quan từ thế giới thực. Điều này có thể liên quan đến việc trích xuất, xử lý và phân tích thông tin từ các đầu vào đó để đưa ra quyết định.

Sự phát triển của thị giác máy chứng kiến ​​sự chính thức hóa quy mô lớn của các bài toán khó thành các phát biểu bài toán phổ biến có thể giải được.

Việc phân chia các chủ đề thành các nhóm được hình thành tốt với danh pháp phù hợp đã giúp các nhà nghiên cứu trên toàn cầu xác định các vấn đề và giải quyết chúng một cách hiệu quả.

Các tác vụ thị giác máy tính phổ biến nhất mà chúng ta thường thấy trong thuật ngữ AI bao gồm:

* **Phân loại hình ảnh (image classification)**: liên quan đến việc gán nhãn cho hình ảnh.
* **Định vị vật thể (object localization)**: liên quan đến việc vẽ một hộp giới hạn (bounding box) xung quanh một hoặc nhiều đối tượng trong hình ảnh nhằm khoanh vùng đối tượng.
* **Phát hiện đối tượng (object detection)**: Là nhiệm vụ khó khăn hơn và là sự kết hợp của cả hai nhiệm vụ trên: Vẽ một bounding box xung quanh từng đối tượng quan tâm trong ảnh và gán cho chúng một nhãn. Kết hợp cùng nhau, tất cả các vấn đề này được gọi là object recognition hoặc object detection.
Bài viết này sẽ giới thiệu một cách khái quát các vấn đề của object detection và các mô hình deep learning state-of-art được thiết kế để giải quyết nó.

# 1 - Object Detection là gì?

Nhận dạng đối tượng là một thuật ngữ chung để mô tả một tập hợp các nhiệm vụ thị giác máy tính có liên quan liên quan đến việc xác định các đối tượng trong ảnh kỹ thuật số.

Phân loại hình ảnh liên quan đến việc dự đoán lớp của một đối tượng trong một hình ảnh. Định vị vật thể đề cập đến việc xác định vị trí của một hoặc nhiều đối tượng trong một hình ảnh và vẽ bounding box xung quanh chúng. Phát hiện đối tượng kết hợp hai nhiệm vụ trên và thực hiện cho một hoặc nhiều đối tượng trong hình ảnh. Chúng ta có thể phân biệt giữa ba nhiệm vụ thị giác máy tính cơ bản trên thông qua input và output của chúng như sau:

- **Image classification**: Dự đoán nhãn của một đối tượng trong một hình ảnh.
    - Input: Một hình ảnh với một đối tượng, chẳng hạn như một bức ảnh.
    - Output: Nhãn lớp (ví dụ: một hoặc nhiều số nguyên được ánh xạ tới nhãn lớp).
- **Object location**: Xác định vị trí hiện diện của các đối tượng trong ảnh và cho biết vị trí của chúng bằng bounding box.
    - Input: Một hình ảnh có một hoặc nhiều đối tượng, chẳng hạn như một bức ảnh.
    - Output: Một hoặc nhiều bounding box được xác định bởi tọa độ tâm, chiều rộng và chiều cao.
- **Object detection**: Xác định vị trí hiện diện của các đối tượng trong bounding box và nhãn của các đối tượng nằm trong một hình ảnh.
    - Input: Một hình ảnh có một hoặc nhiều đối tượng, chẳng hạn như một bức ảnh.
    - Output: Một hoặc nhiều bounding box và nhãn cho mỗi bounding box.
  
Một số định nghĩa khác cũng rất quan trọng trong computer vision là **phân đoạn đối tượng (object segmentation)**, trong đó các đối tượng được nhận dạng bằng cách làm nổi bật các pixel cụ thể của đối tượng thay vì bounding box. Và **image captioning** kết hợp giữa các kiến trúc mạng CNN và LSTM để đưa ra các lý giải về hành động hoặc nội dung của một bức ảnh.

Hình dưới mô tả các nhiệm vụ thị giác máy tính cơ bản, trong đó object segmentation được chia thành 2 loại là:
-   **Semantic segmentation**: phân đoạn đối tượng theo lớp, chẳng hạn như phân đoạn đối tượng thành các lớp như: người, xe, cây, núi, v.v.
-   **Instance segmentation**: phân đoạn đối tượng theo thể hiện, chẳng hạn như phân đoạn đối tượng thành các thể hiện như: người 1, người 2, xe 1, xe 2, v.v.

{% include image.html url="\images\less4\Computer-vision-tasks-Adapted-from.png" description="" %}
