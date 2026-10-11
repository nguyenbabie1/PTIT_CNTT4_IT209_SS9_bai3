\# Bài 3: Đóng gói trang Web HTML tĩnh bằng Nginx



\## 1. Nội dung



Trang web sử dụng nội dung:



```html

<h1>Hello Docker Session 09!</h1>

```



\## 2. Dockerfile



```dockerfile

FROM nginx:alpine

COPY index.html /usr/share/nginx/html/index.html

```



\## 3. Build Image



```bash

docker build -t my-html-app:v1 .

```



Image được tạo với tên:



```text

my-html-app:v1

```



\## 4. Chạy Container



```bash

docker run -d -p 8081:80 --name html-app my-html-app:v1

```



Container sử dụng cổng `8081` trên máy host và chuyển tiếp đến cổng `80` của Nginx.



\## 5. Kiểm tra



```bash

curl http://localhost:8081

```



Kết quả:



```html

<h1>Hello Docker Session 09!</h1>

```



\## 6. Kết luận



Đã build thành công Docker Image `my-html-app:v1` và chạy trang HTML tĩnh bằng Nginx trên cổng `8081`.

