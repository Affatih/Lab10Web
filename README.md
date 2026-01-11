# Laporan Praktikum 10: Pemrograman Web orientasi Objek (PHP OOP)

## 1. Judul Proyek
**Sistem Manajemen Stok Warung Madura**

## 2. Deskripsi
Aplikasi ini merupakan sistem manajemen inventaris sederhana yang dibangun menggunakan bahasa pemrograman PHP dengan menerapkan paradigma **Object Oriented Programming (OOP)**. Fokus utama praktikum ini adalah enkapsulasi logika koneksi database dan manipulasi data ke dalam sebuah Class.

## 3. Penerapan Konsep OOP
Dalam proyek ini, konsep OOP diterapkan pada bagian inti sistem:

* **Definisi Class & Object:** Seluruh interaksi database dikelola oleh class `Database`.
* **Property & Method:**
    * `$host`, `$user`, `$pass`, `$db`: Digunakan sebagai property untuk menyimpan kredensial database.
    * `__construct()`: Magic method yang otomatis menjalankan koneksi database saat objek dibuat.
    * `query()`: Method utama untuk menjalankan perintah SQL (SELECT, INSERT, UPDATE, DELETE).
* **Modularitas (Class Library):** File `Database.php` dipisahkan di dalam folder `class/` agar dapat digunakan berulang kali di berbagai modul (reusability).

## 4. Struktur Folder (OOP Standard)
```text
warung_madura/
├── class/
│   └── Database.php      <-- Class Library Utama
├── config.php            <-- File Konfigurasi Database
├── index.php             <-- Main Controller / Router
└── module/
    └── barang/           <-- Implementasi Fitur
```

## 5. Cuplikan Kode OOP (Koneksi Database)
```
// Contoh Instansiasi Objek di index.php
include_once 'class/Database.php';
$db = new Database($config); // Membuat Object dari Class Database

// Contoh Penggunaan Method Query
$result = $db->query("SELECT * FROM data_barang");
```
