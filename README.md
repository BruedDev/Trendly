# Trendly Project

Dự án Trendly bao gồm cả backend và frontend được quản lý thông qua Git submodules.

## 📋 Yêu cầu hệ thống
- Git phiên bản 2.13 trở lên
- Node.js và npm (cho frontend và backend)

## 🚀 Hướng dẫn clone project

### Cách 1: Clone với submodules (Khuyến nghị)
```bash
git clone --recurse-submodules https://github.com/BruedDev/Trendly.git
cd Trendly
```

### Cách 2: Clone rồi init submodules sau
```bash
git clone https://github.com/BruedDev/Trendly.git
cd Trendly
git submodule init
git submodule update
```

### Cách 3: Sử dụng lệnh rút gọn
```bash
git clone https://github.com/BruedDev/Trendly.git
cd Trendly
git submodule update --init --recursive
```

## 📁 Cấu trúc project sau khi clone
```
Trendly/
├── back-end/     # Backend code (submodule)
├── front-end/    # Frontend code (submodule)
├── .gitmodules   # Cấu hình submodules
└── README.md     # File hướng dẫn này
```

## 🔄 Cập nhật code

### Cập nhật code từ repository chính
```bash
git pull origin main
```

### Cập nhật submodules lên phiên bản mới nhất
```bash
git submodule update --remote
```

### Cập nhật tất cả (repo chính + submodules)
```bash
git pull origin main
git submodule update --recursive --remote
```

## 🛠️ Làm việc với submodules

### Kiểm tra trạng thái submodules
```bash
git submodule status
```

### Vào thư mục submodule để làm việc
```bash
# Làm việc với backend
cd back-end
git checkout main
# Thực hiện các thay đổi...

# Làm việc với frontend
cd ../front-end
git checkout main
# Thực hiện các thay đổi...
```

### Commit thay đổi trong submodule
```bash
# Trong thư mục submodule
cd back-end
git add .
git commit -m "Update backend"
git push origin main

# Quay lại thư mục chính và commit reference mới
cd ..
git add back-end
git commit -m "Update backend submodule reference"
git push origin main
```

## ⚠️ Lưu ý quan trọng

1. **Không được commit trực tiếp trong thư mục submodule** mà không push lên remote repository trước
2. Khi pull code mới, luôn chạy `git submodule update` để đảm bảo submodules được cập nhật đúng version
3. Nếu submodule bị "detached HEAD", hãy checkout về branch chính:
   ```bash
   cd back-end
   git checkout main
   ```

## 🔧 Khắc phục sự cố

### Submodule bị lỗi hoặc không đồng bộ
```bash
git submodule deinit --all
git submodule update --init --recursive
```

### Reset submodule về trạng thái ban đầu
```bash
git submodule foreach --recursive git reset --hard
git submodule update --init --recursive
```

## 🌐 Repository Links
- **Main Repository**: https://github.com/BruedDev/Trendly.git
- **Backend Repository**: https://github.com/BruedDev/Trendly-backend.git
- **Frontend Repository**: https://github.com/BruedDev/Trendly-frontend.git

## 📞 Hỗ trợ
