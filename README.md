
Panduan ini menjelaskan cara **menjalankan Cloudflare Tunnel (cloudflared)** di **Windows + Laragon** untuk membagikan project lokal (`localhost`) ke internet tanpa konfigurasi rumit.

---

## 🧩 Prasyarat

- Windows 10 / 11 (64-bit)
- Laragon sudah terinstall
- Apache/Nginx di Laragon **RUNNING**
- Project berada di:
```

C:\laragon\www

````

---

## 📥 Download Cloudflared (Tanpa Install Ribet)

Langkah ini menggunakan **Laragon Terminal / CMD**.

### 1️⃣ Buka Laragon Terminal
- Jalankan Laragon
- Klik **Terminal**

---

### 2️⃣ Buat folder cloudflared
```bash
mkdir cloudflared
cd cloudflared
````

---

### 3️⃣ Download cloudflared.exe

```bash
curl -L -o cloudflared.exe https://github.com/cloudflare/cloudflared/releases/latest/download/cloudflared-windows-amd64.exe
```

📦 Ukuran file ± **20 MB**

---

### 4️⃣ Cek file berhasil terdownload

```bash
dir
```

Pastikan ada file:

```
cloudflared.exe
```

---

## 🔍 Cek Versi Cloudflared

```bash
cloudflared.exe --version
```

Jika muncul versi, berarti cloudflared **siap digunakan** ✅

---

## 🌐 Menjalankan Tunnel (Share Project Laragon)

### 🔹 Share seluruh localhost

```bash
cloudflared.exe tunnel --url http://localhost
```

---

### 🔹 Share project tertentu (contoh: project `buah`)

```bash
cloudflared.exe tunnel --url http://localhost/buah
```

---

## 🔗 URL Publik

Setelah dijalankan, akan muncul URL seperti:

```
https://random-name.trycloudflare.com
```

URL tersebut:

* Bisa dibuka dari mana saja 🌍
* Bisa dishare ke orang lain
* Tidak perlu login Cloudflare
* Tidak perlu setting DNS / port forwarding

---

## 🧠 Catatan Penting

* Tunnel aktif **selama terminal terbuka**
* Tutup terminal = URL nonaktif
* Cocok untuk:

  * Demo project
  * Testing API
  * Share ke client / dosen / teman

---

## ✅ Kelebihan Cloudflare Tunnel

* Gratis
* Stabil
* Tidak diblok ISP
* Lebih simpel dari ngrok
* Cocok untuk Windows + Laragon

---

## 📌 Referensi Resmi

* [https://developers.cloudflare.com/cloudflare-one/connections/connect-apps/](https://developers.cloudflare.com/cloudflare-one/connections/connect-apps/)
* [https://github.com/cloudflare/cloudflared](https://github.com/cloudflare/cloudflared)

---

✨ Selesai. Project Laragon kamu sekarang online!

