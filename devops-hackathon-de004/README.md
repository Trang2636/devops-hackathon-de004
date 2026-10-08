## 1. Thông tin sinh viên

| Họ và tên          | Mã sinh viên | Lớp       | Tài khoản Linux | GitHub                      | Cổng Nginx |
|--------------------|--|-----------|-----------------|-----------------------------|------------|
| Trần Thị Thu Trang |  | K24-CNTT2 | `Trang`         | `https://github.com/Trang2636/devops-hackathon-de004` | `8081`     |

## 2. Môi trường triển khai

- Hệ điều hành: Ubuntu 22.04/24.04
- Nginx: ``
- Git: `
- UFW: Ubuntu Firewall
- Máy chủ: `trang`
- Địa chỉ IP: `221.121.4.95`
- Cổng website: `8081`

## 3. Cấu trúc dự án

```text
devops-hackathon-de004-nguyenvana/
├── src/
│   └── index.html
├── nginx/
│   └── <TEN_TAI_KHOAN>.conf
├── screenshots/
│   ├── 01-user.png
│   ├── 02-nginx.png
│   ├── 03-ufw.png
│   ├── 04-website.png
│   ├── 05-git-log.png
│   └── 06-update.png
├── .gitignore
└── README.md
```

## 4. Cấu hình Nginx

| Tham số trong template | Giá trị đã điền                       | Giải thích |
|---|---------------------------------------|---|
| PORT | `8081`                                | Cổng riêng của website |
| SERVER_NAME | `trang`                               | Địa chỉ IP máy chủ |
| WEB_ROOT | `/var/www/devops-hackathon-de004/src` | Thư mục web root |
| INDEX_FILE | `index.html`                          | Trang chính |
| TEN_TAI_KHOAN | `trang`                               | Tài khoản Linux |
| ALLOW_DIRECTIVE | `allow all`                           | Cho phép request từ bên ngoài |

## 5. Tường lửa UFW

Các cổng được cho phép:

```text
22/tcp
8081/tcp
```

Kiểm tra:

```bash
sudo ufw status verbose
```

## 6. Các bước triển khai

```text
Tạo tài khoản Linux
→ Cài Nginx, Git, UFW, Curl
→ Tạo website
→ Push mã nguồn lên GitHub
→ Clone repository lên server
→ Đổi quyền sở hữu
→ Cấu hình Nginx
→ Kiểm tra nginx -t
→ Reload Nginx
→ Cấu hình UFW
→ Kiểm tra website
```

## 7. Kiểm tra và minh chứng

### 7.1. Tài khoản

`01-user.png` thể hiện kết quả `id` và `whoami`.

### 7.2. Nginx

`02-nginx.png` thể hiện Nginx đang `active` và `enabled`.

### 7.3. UFW

`03-ufw.png` thể hiện các cổng được phép truy cập.

### 7.4. Website

`04-website.png` thể hiện website được truy cập bằng IP và cổng riêng.

### 7.5. Git

`05-git-log.png` thể hiện lịch sử commit của repository.

### 7.6. Cập nhật website

`06-update.png` thể hiện website sau khi cập nhật nội dung.

## 8. Quy trình cập nhật website

Trên máy cá nhân:

```bash
git add .
git commit -m "update: update website content"
git push
```

Trên máy chủ:

```bash
cd /var/www/devops-hackathon-de004
git pull
```

Kiểm tra:



## 9. Xử lý sự cố

```bash
sudo nginx -t
sudo systemctl status nginx
sudo ufw status verbose
git status
git log --oneline
```


