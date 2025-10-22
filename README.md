# lol

*Created with love by willicc & Qwen*

# Twitter Auto Task Bot

Bot otomatis untuk mendaftarkan akun Twitter dan menyelesaikan tugas-tugas pada platform Lolana.fun.

## 📋 Deskripsi

Bot ini secara otomatis:
- Generate username Twitter yang unik
- Mendaftarkan akun dengan wallet address
- Menyelesaikan semua task yang tersedia
- Mencapai 50 points per akun
- Menyimpan hasil ke file teks

## 🚀 Fitur

- ✅ Generate 1000+ username unik secara acak
- ✅ Auto register dengan referral @fvrtgr
- ✅ Auto complete 5 tasks
- ✅ Delay acak antara request
- ✅ Error handling yang robust
- ✅ Simpan hasil ke file
- ✅ Deteksi duplikasi otomatis

## 📁 Struktur Project

```
twitter-auto-bot/
├── auto_submit.py      # Script utama
├── address.txt         # File input wallet addresses
├── hasil.txt           # File output hasil
└── README.md          # Dokumentasi ini
```

## ⚙️ Instalasi

1. **Clone repository**
```bash
git clone https://github.com/willicc/lol.git
cd lol
```

2. **Install dependencies**
```bash
pip install requests
```

3. **Siapkan file address.txt**
Buat file `address.txt` dan isi dengan wallet addresses (satu per baris):

```
4tjd8Fb61A9u3HmWei6DshTY4QirLGvT11vnET5qoRkN
8xYc9DvRkLm2aPnQwE7sTgHjKlZbNmVcXz
3qWe8RtYuIoPaSdFgHjKlZxCnVmBpLqWe
```

## 🎯 Penggunaan

Jalankan script dengan perintah:

```bash
python auto_submit.py
```

### Output yang Diharapkan

```
=== Auto Submit Twitter & Wallet ===
Referral: @fvrtgr
Total prefixes: 100
Total suffixes: 100
Found 0 existing wallets in hasil.txt

Ditemukan 5 wallet untuk diproses
Wallet yang akan diproses: 5

============================================================
Memproses [1/5]
Wallet: 4tjd8Fb61A9u3HmWei6DshTY4QirLGvT11vnET5qoRkN
============================================================
Generated username: @quantum_warrior42
Menunggu 7.6 detik sebelum memulai...
1. Mendaftarkan user...
    Payload: {"username": "@quantum_warrior42", "wallet": "4tjd8Fb61A9u3HmWei6DshTY4QirLGvT11vnET5qoRkN", "points": 0, "completed_tasks": "[]", "referral": "@fvrtgr"}
    Response Status: 201
✅ Berhasil mendaftarkan user!
...
```

## 📊 Tasks yang Diselesaikan

Bot akan menyelesaikan 5 tasks secara berurutan:

1. **Twitter Follow** - 10 points
2. **Follow Owner** - 20 points  
3. **Telegram Join** - 30 points
4. **Tweet Share** - 45 points
5. **Daily Claim** - 50 points

## ⚡ Konfigurasi

### Delay Settings
- **Antar user**: 5-10 detik
- **Setelah registrasi**: 3-6 detik  
- **Antar task**: 2-4 detik
- **Retry delay**: 3-6 detik

### Username Generation
- **Format**: `@prefix_suffix` atau `@prefix_suffix123`
- **Panjang maks**: 15 karakter
- **Kombinasi**: 100 prefix × 100 suffix × 1000 angka

## 🛠 Troubleshooting

### Error Umum dan Solusi

**Error 400: Bad Request**
```bash
Response Text: {"code":"PGRST204","details":null,"hint":null,"message":"Could not find the 'lolana_balance' column"}
```
✅ **Solusi**: Script sudah diperbaiki, hapus field yang tidak diperlukan

**Error 409: Conflict**
```bash
Response Text: Username/wallet sudah terdaftar
```
✅ **Solusi**: Bot akan auto generate username baru

**Error Connection**
```bash
Request error: Connection timeout
```
✅ **Solusi**: Cek koneksi internet dan API endpoint

## 📝 File Output

Hasil berhasil disimpan di `hasil.txt` dengan format:
```
@quantum_warrior42|4tjd8Fb61A9u3HmWei6DshTY4QirLGvT11vnET5qoRkN
@cosmic_explorer123|8xYc9DvRkLm2aPnQwE7sTgHjKlZbNmVcXz
@digital_mage99|3qWe8RtYuIoPaSdFgHjKlZxCnVmBpLqWe
```

## ⚠️ Disclaimer

- Script ini untuk tujuan edukasi dan testing saja
- Gunakan dengan bertanggung jawab
- Patuhi Terms of Service platform yang dituju
- Developer tidak bertanggung jawab atas penyalahgunaan

## 🔧 Pengembangan

### Menambah Prefix/Suffix
Edit lists `PREFIXES` dan `SUFFIXES` dalam script untuk variasi username lebih banyak.

### Mengubah Delay
Modify values dalam fungsi `time.sleep()` dan `random.uniform()`.

### Custom Referral
Ubah variable `REFERRAL` di bagian konfigurasi.

## 📄 License

MIT License - bebas digunakan untuk tujuan personal dan edukasi.

## 🤝 Contributing

1. Fork repository
2. Buat feature branch
3. Commit changes
4. Push ke branch
5. Buat Pull Request

---

**Note**: Pastikan untuk mengikuti semua ketentuan dan regulasi yang berlaku saat menggunakan script ini.
