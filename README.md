# pgCloud Provisioner - DBaaS CLI

pgCloud adalah antarmuka Command Line Interface (CLI) berbasis skrip Python murni (*Operations as a Code*) untuk mensimulasikan layanan *Database as a Service* (DBaaS) menggunakan PostgreSQL dan Docker. 

Proyek ini dibuat untuk memenuhi Tugas Mini Project Mata Kuliah Komputasi Awan. Layanan ini bertindak sebagai *Cloud Provider* yang dapat melakukan *provisioning* (pembuatan wadah database terisolasi) dan *monitoring* (perekaman kesehatan sistem seperti CPU dan RAM) secara otomatis tanpa melalui dashboard (GUI).

**Anggota Kelompok:**
1. Bagas Vieri Surya Putra  (25/575242/NPA/20020)
2. Aditya Eka Narayan  (25/575258/NPA/20026)
3. Nayla Aulia Wijaya   (25/575245/NPA/20021)
4. Nabil Hibban Hardian  (25/575252/NPA/20025)
5. Angela Echa Naresti  (25/575275/NPA/20027)

## Prasyarat (Prerequisites)
Sebelum menggunakan CLI ini, pastikan sistem operasi Linux Anda telah terinstal:
* **Python 3**
* **Docker** (Pastikan *daemon* Docker tersedia. Sistem akan mencoba menghidupkannya secara otomatis jika dalam keadaan mati).

## Cara Instalasi

Ikuti langkah-langkah berikut untuk mengimplementasikan kode dari repositori ini agar dapat dieksekusi secara global di terminal sebagai *command* `pgcloud` (tanpa perlu mengetikkan `python3 pgcloud.py`):

**1. Clone Repositori**
Unduh repositori ini ke dalam mesin lokal Anda:
```bash
git clone https://github.com/SpaghettiRegretti/miniproject-cloud-dbaas.git
cd miniproject-cloud-dbaas
```
**2. Jadikan File Sebagai Executable**
Ubah izin akses file skrip utama agar dapat dieksekusi oleh sistem:
```bash
chmod +x pgcloud
```
**3. Pindahkan ke Direktori Binary Sistem**
Pindahkan file ke direktori /usr/local/bin/ agar perintah dapat dikenali secara global dari direktori mana saja. Langkah ini membutuhkan hak akses administrator:
```bash
sudo mv pgcloud /usr/local/bin/
```

## Cara Penggunaan (Usage)
Setelah instalasi selesai, Anda dapat langsung memanggil layanan ini melalui terminal.
**Melihat Menu Bantuan:**
```bash
pgcloud -h
```
**Membuat Database Baru (Fitur Create):**
Digunakan untuk melakukan _provisioning_ container database baru.
```bash
pgcloud create --db-name <nama_bebas> --db-user <username> --db-password <password>
```
_Contoh:_
```bash
pgcloud create --db-name db-tugas-cloud --db-user admin_db --db-password rahasia123
```
**Memonitor Kesehatan Sistem Database (Fitur Monitor):**
Digunakan untuk merekam dan menampilkan penggunaan CPU dan RAM dari database secara real-time.
```bash
pgcloud monitor --db-name <nama_database>
```
_Contoh:_
```bash
pgcloud monitor --db-name db-tugas-cloud
```
