# Laravel Framework Course

**Jehan Afwazi Ahmad**\
Freelance Developer \| Backend Engineer \| DevOps

---

# Sebelum Belajar

Sebelum mempelajari Laravel, pastikan sudah memahami:

- Basic **PHP**
- Basic **HTML & CSS**
- **MVC Design Pattern**
- **Object Oriented Programming (OOP)**

---

# Agenda Pembelajaran

1.  Intro Laravel
2.  Route
3.  View (Blade Template Engine)
4.  Dummy Model + Collections
5.  Migration
6.  Seeder + Factory + Faker
7.  Create Model Controller
8.  Relations
9.  ORM Problems (N+1)
10. Searching & Pagination
11. Authentication
12. Create Backend UI
13. CRUD + Validation
14. Authorizations

---

# Apa Itu Laravel?

> Laravel is a web application framework with expressive, elegant
> syntax.\
> We've already laid the foundation, freeing you to create without
> sweating the small things.

--- Laravel Documentation

---

# Fitur Laravel

Beberapa kelebihan Laravel:

- Dokumentasi yang baik
- Komunitas besar
- Banyak library pendukung

---

# Perbandingan Framework PHP

Referensi:\
https://www.excellentwebworld.com/best-php-frameworks

---

# Persiapan Development

Kebutuhan utama:

- **PHP** \^8.1
- **MySQL** \^5.7
- **Composer 2**
- **DBMS**
- **Terminal**
- **Code Editor**

Contoh editor:

- VSCode
- PHPStorm

---

# Fitur Code Editor

Beberapa fitur penting:

- Syntax Highlight
- Auto Complete
- Git Integration
- Debugging
- Speed Development

---

# VSCode Extensions

Disarankan menginstall:

- PHP Intelephense
- Laravel Artisan
- Laravel Snippets
- Laravel Blade Snippets
- Blade Spacer
- Laravel Goto View

---

# Hands On

Website resmi Laravel:

https://laravel.com

---

# Installation & Configuration

Langkah instalasi:

1.  Install **PHP dan MySQL** (XAMPP / WAMP / Manual)
2.  Install **Composer** https://getcomposer.org/download
3.  Install **Laravel Project**
4.  Jalankan aplikasi

```bash
php artisan serve
```

---

# Struktur Direktori Laravel

Struktur utama proyek Laravel terdiri dari:

- app/
- bootstrap/
- config/
- database/
- public/
- resources/
- routes/
- storage/
- tests/
- vendor/

---

# File .ENV

Digunakan untuk konfigurasi environment seperti:

- Database
- App key
- Mail configuration
- Cache configuration

Dokumentasi:

https://laravel.com/docs/configuration#environment-configuration

---

# Composer.json

File ini berisi:

- Dependency project
- Versi package
- Autoloading
- Script composer

---

# Routing

Contoh routing dasar:

```php
use Illuminate\Support\Facades\Route;

Route::get('/greeting', function () {
    return 'Hello World';
});
```

Routing dengan parameter:

```php
Route::get('/user/{id}', function ($id) {
    return 'User ' . $id;
});
```

---

# Routing Controller

Laravel 7:

```php
Route::get('/user', 'UserController@index');
```

Laravel 8+:

```php
use App\Http\Controllers\UserController;

Route::get('/user', [UserController::class, 'index']);
```

---

# Route Response

Response yang bisa dikembalikan:

- String
- Array
- JSON
- View

---

# View

View merupakan **User Interface** yang menampilkan data kepada pengguna.

Laravel menggunakan **Blade Template Engine** untuk mengelola tampilan.

---

# Controller

Controller digunakan untuk:

- Menangani request
- Mengelola logic aplikasi
- Menghubungkan model dengan view

Lokasi:

    app/Http/Controllers

---

# Blade Template Engine

Blade adalah template engine bawaan Laravel.

Fitur utama:

- Variable
- Looping
- Conditional
- Layout
- Component
- Partial

Format file:

    view_name.blade.php

Dokumentasi:\
https://laravel.com/docs/blade

---

# Middleware

Middleware digunakan untuk **memfilter HTTP request**.

Contoh membuat middleware:

```bash
php artisan make:middleware MiddlewareName
```

Contoh kode:

```php
public function handle($request, Closure $next)
{
    if ($request->input('token') !== 'my-secret-token') {
        return redirect('home');
    }

    return $next($request);
}
```

---

# Database Migration

Migration berfungsi seperti **version control untuk database**.

Manfaat:

- Mengelola perubahan database
- Mempermudah kolaborasi tim
- Sinkronisasi struktur database

Dokumentasi:\
https://laravel.com/docs/migrations

---

# Query Builder

Digunakan untuk menjalankan query database.

Contoh:

```php
DB::table('users')->get();
```

Dokumentasi:\
https://laravel.com/docs/queries

---

# Eloquent ORM

Eloquent adalah **ORM (Object Relational Mapper)** Laravel.

Fungsi:

- Menghubungkan tabel database dengan model
- Mengakses data sebagai object

Contoh:

```php
Post::all();
```

Dokumentasi:\
https://laravel.com/docs/eloquent

---

# Eloquent Relationship

## 1. Has Many

Contoh:

- Post memiliki banyak Comment

---

## 2. Belongs To

Contoh:

- Comment milik satu Post

---

## 3. Has One

Contoh:

- User memiliki satu Profile

---

## 4. Many to Many

Contoh:

- Product memiliki banyak Phone
- Phone memiliki banyak Product

Menggunakan **Pivot Table**.

---

# Validation

Contoh validasi request:

```php
$validated = $request->validate([
    'title' => 'required|unique:posts|max:255',
    'body' => 'required',
]);
```

---

# Form Request

Membuat class validasi:

```bash
php artisan make:request RequestName
```

---

# File Upload

Laravel menyediakan sistem upload file yang mudah.

Dapat terintegrasi dengan:

- Local filesystem
- SFTP
- AWS S3

---

# Pagination

Laravel menyediakan pagination otomatis.

Dokumentasi:\
https://laravel.com/docs/pagination

---

# Authentication

Laravel dapat menghasilkan UI authentication secara otomatis.

```bash
php artisan ui:auth
```

---

# Mailer

Membuat class mail:

```bash
php artisan make:mail MailClassName
```

Mengirim email:

```php
Mail::to($recipient)->send(new ExampleMail($param));
```

---

# Job & Queue

Digunakan untuk menjalankan proses di background.

Contoh:

- Email sending
- Image processing
- Notification

Dokumentasi:\
https://laravel.com/docs/queues

---

# Localization

Digunakan untuk membuat aplikasi **multi-language**.

Dokumentasi:\
https://laravel.com/docs/localization

---

# Laravel Best Practice

**Jehan Afwazi Ahmad**\
Freelance Developer \| Backend Engineer \| DevOps
