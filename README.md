# Bài 1: Quản lý người dùng giới hạn và Truyền tải dữ liệu qua SFTP trên Windows


### 1. Đăng nhập với tài khoản root
```bash
ssh root@<IP>
```

### 2. Khởi tạo tài khoản người dùng:
```bash
sudo adduser sftp-user
```

### 3. Tạo thư mục log giả lập và gán quyền đọc:
```bash
sudo mkdir -p /var/log/app-backup/

sudo touch /var/log/app-backup/backup-check.log

sudo bash -c 'echo "Backup status: SUCCESS at $(date)" > /var/log/app-backup/backup-check.log'

sudo chown -R root:sftp-user /var/log/app-backup

sudo chmod 750 /var/log/app-backup

sudo chmod 640 /var/log/app-backup/backup-check.log
```

### 4. Sử dụng phần mềm SFTP Client (đề xuất: Bitvise SSH Client )
- Mở phần mềm Bitvise SSH Client trên Windows:
```angular2html
1. Mở phần mềm Bitvise SSH Client trên Windows
2. Điền sftp-user vào ô Username.
3. Chọn Method là Password và nhập mật khẩu của sftp-user.
4. Log in
5. Sau khi login thành công
-  chọn New SFTP Window
-  đi đến thư mục /var/log/app-backup/ (bên Remote Files)
    kéo file backup-check.log sang Local File trên máy 
```
