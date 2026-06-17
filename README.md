<div align="center">

# 🚀 My First App

**Dự án nền tảng Laravel — bước đầu làm quen với PHP framework**

![Laravel](https://img.shields.io/badge/Laravel-9-FF2D20?style=flat-square&logo=laravel&logoColor=white)
![PHP](https://img.shields.io/badge/PHP-%5E8.0.2-777BB4?style=flat-square&logo=php&logoColor=white)
![License](https://img.shields.io/badge/license-MIT-green?style=flat-square)

</div>

---

## 📝 Giới thiệu

`my_first_app` là dự án khởi tạo bằng [Laravel 9](https://laravel.com/), được dựng lên để làm quen với cấu trúc, quy ước (convention) và vòng đời request của một framework PHP hiện đại — routing, middleware, Eloquent ORM, migration, và tích hợp frontend qua Vite.

Ở trạng thái hiện tại, project giữ nguyên bộ khung mặc định mà Laravel cung cấp khi tạo project mới: trang chào (`welcome.blade.php`), model `User`, các migration cơ bản (`users`, `password_resets`, `personal_access_tokens`, `failed_jobs`) và một endpoint API mẫu được bảo vệ bởi Sanctum. Đây là điểm khởi đầu phù hợp để tiếp tục xây dựng các tính năng thực tế (CRUD, authentication, API resource...).

## 🔧 Công nghệ sử dụng

| Công nghệ | Vai trò |
|---|---|
| [Laravel 9](https://laravel.com/) | PHP framework chính (routing, ORM, migration, validation...) |
| PHP ^8.0.2 | Ngôn ngữ backend |
| [Laravel Sanctum](https://laravel.com/docs/9.x/sanctum) | Xác thực API bằng token (đã cấu hình sẵn, route `/api/user`) |
| [Vite](https://vitejs.dev/) + `laravel-vite-plugin` | Build & bundle asset frontend (JS/CSS) |
| Axios, Lodash | Thư viện JS hỗ trợ phía client |
| PHPUnit | Test framework (đã có sẵn cấu hình `phpunit.xml` và thư mục `tests/`) |

## 🚀 Cài đặt & chạy dự án

### Yêu cầu

- PHP ≥ 8.0.2 (kèm các extension cần thiết của Laravel)
- [Composer](https://getcomposer.org/)
- Node.js & npm (để build asset frontend qua Vite)
- Một hệ quản trị CSDL (MySQL/SQLite...) — có thể dùng SQLite để chạy nhanh không cần cài server CSDL

### Các bước

```bash
# 1. Clone dự án
git clone https://github.com/vohuynhdatpy/my_first_app.git
cd my_first_app

# 2. Cài đặt dependencies PHP
composer install

# 3. Tạo file môi trường và sinh application key
cp .env.example .env
php artisan key:generate

# 4. Cấu hình kết nối database trong file .env, sau đó chạy migration
php artisan migrate

# 5. Cài đặt dependencies frontend
npm install

# 6. Build asset (hoặc chạy ở chế độ watch khi phát triển)
npm run dev
```

Mở một terminal khác để chạy server Laravel:

```bash
php artisan serve
```

Truy cập [http://localhost:8000](http://localhost:8000) để xem trang chào mặc định của Laravel.

### Chạy test

```bash
php artisan test
# hoặc
./vendor/bin/phpunit
```

## 📂 Cấu trúc thư mục chính

```
my_first_app/
├── app/
│   ├── Http/Controllers/   # Controller xử lý request (hiện chỉ có Controller cơ sở)
│   ├── Models/             # Eloquent model (User.php)
│   └── Providers/          # Service provider của Laravel
├── database/
│   ├── migrations/         # Định nghĩa schema: users, password_resets, personal_access_tokens...
│   ├── factories/          # Factory sinh dữ liệu giả cho testing/seeding
│   └── seeders/            # Seeder khởi tạo dữ liệu mẫu
├── resources/
│   ├── views/welcome.blade.php  # View chào mừng mặc định
│   ├── js/                 # Entry point JS (app.js, bootstrap.js)
│   └── css/                # Stylesheet
├── routes/
│   ├── web.php              # Route giao diện web (hiện chỉ có route "/")
│   └── api.php              # Route API (endpoint /api/user dùng Sanctum)
├── tests/                  # Unit & Feature test (PHPUnit)
├── composer.json
├── package.json
└── vite.config.js
```

## 📚 Hướng phát triển tiếp theo

Vì đây là dự án nền tảng, một số hướng mở rộng tự nhiên là:

- [ ] Xây dựng Controller, Model và Migration cho nghiệp vụ cụ thể (ví dụ: quản lý bài viết, sản phẩm, đơn hàng...).
- [ ] Hoàn thiện hệ thống đăng ký/đăng nhập (Laravel Breeze, Jetstream hoặc tự xây bằng Sanctum).
- [ ] Viết thêm Feature test cho các route/API mới.
- [ ] Thiết kế lại frontend (Blade, hoặc tích hợp Vue/React qua Vite) thay cho trang `welcome.blade.php` mặc định.
- [ ] Cấu hình môi trường deploy (Docker, Laravel Sail, hoặc các nền tảng như Render/Railway).

## 👤 Tác giả

**Võ Huỳnh Đạt**

🔗 [github.com/vohuynhdatpy](https://github.com/vohuynhdatpy)

---

<div align="center">

Dự án học tập — phản hồi và góp ý luôn được hoan nghênh!

</div>
