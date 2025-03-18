# Phase-1-Week-2

# JavaScript Week 2: File System

## 1. Pengenalan File System di Node.js

### Penjelasan
Node.js menyediakan modul bawaan bernama `fs` (File System) yang memungkinkan kita untuk bekerja dengan file di dalam sistem operasi. Modul ini memungkinkan kita untuk:
- Membaca dan menulis file
- Menghapus file
- Membuat dan menghapus direktori
- Menyunting file secara asynchronous atau synchronous

Untuk menggunakan modul `fs`, kita perlu mengimpornya terlebih dahulu dalam kode JavaScript kita:
```javascript
const fs = require("fs");
```

---

## 2. Contoh Penggunaan

### Membaca File (`fs.readFile`)
Kita bisa membaca isi file dengan `fs.readFile()`, yang bekerja secara asynchronous.

```javascript
const fs = require("fs");

fs.readFile("example.txt", "utf8", (err, data) => {
    if (err) {
        console.error("Error membaca file:", err);
        return;
    }
    console.log("Isi file:", data);
});
```

### Menulis File (`fs.writeFile`)
Untuk menulis atau membuat file baru, kita bisa menggunakan `fs.writeFile()`.

```javascript
const fs = require("fs");

fs.writeFile("output.txt", "Hello, File System!", (err) => {
    if (err) {
        console.error("Error menulis file:", err);
        return;
    }
    console.log("File berhasil dibuat!");
});
```

### Menambahkan Konten ke File (`fs.appendFile`)
Jika kita ingin menambahkan teks ke dalam file yang sudah ada tanpa menimpa isinya:

```javascript
fs.appendFile("output.txt", "\nTambahan teks baru!", (err) => {
    if (err) {
        console.error("Error menambahkan teks:", err);
        return;
    }
    console.log("Teks berhasil ditambahkan!");
});
```

### Menghapus File (`fs.unlink`)
Untuk menghapus file, kita bisa menggunakan `fs.unlink()`.

```javascript
fs.unlink("output.txt", (err) => {
    if (err) {
        console.error("Error menghapus file:", err);
        return;
    }
    console.log("File berhasil dihapus!");
});
```

### Membuat Direktori (`fs.mkdir`) dan Menghapusnya (`fs.rmdir`)

```javascript
fs.mkdir("myFolder", (err) => {
    if (err) {
        console.error("Error membuat direktori:", err);
        return;
    }
    console.log("Direktori berhasil dibuat!");
});

fs.rmdir("myFolder", (err) => {
    if (err) {
        console.error("Error menghapus direktori:", err);
        return;
    }
    console.log("Direktori berhasil dihapus!");
});
```

---

## 3. Assignment

### Tugas 1: Membaca File
1. Buat file `data.txt` dan isi dengan teks bebas.
2. Buat script `read.js` yang membaca isi file `data.txt` menggunakan `fs.readFile()`.
3. Jalankan script untuk menampilkan isi file di terminal.

### Tugas 2: Menulis dan Menghapus File
1. Buat script `write.js` yang menulis teks ke dalam file `notes.txt` menggunakan `fs.writeFile()`.
2. Tambahkan teks tambahan ke file tersebut menggunakan `fs.appendFile()`.
3. Hapus file `notes.txt` menggunakan `fs.unlink()` setelah selesai.

Selamat belajar! 🚀

