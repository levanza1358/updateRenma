# 📱 Renma — App Update Repository

> Repositori resmi untuk distribusi pembaruan aplikasi **Renma** — aplikasi pembacaan manga online untuk Android.

---

## 📦 Tentang Repositori Ini

Repo ini digunakan untuk:
- 🔄 **Menyimpan file `update.json`** — diperiksa oleh aplikasi Renma secara otomatis untuk mendeteksi versi baru
- 📥 **Distribusi APK** — file instalasi tiap versi tersedia di tab [Releases](../../releases)
- 📋 **Changelog** — catatan perubahan tiap versi

---

## 🔗 URL Update Manifest

Aplikasi Renma mengambil informasi pembaruan dari URL berikut:

```
https://raw.githubusercontent.com/levanza1358/updateRenma/main/update.json
```

---

## 📋 Versi Terkini

| Field | Value |
|---|---|
| **Versi** | 1.0 |
| **Version Code** | 1 |
| **Tanggal Rilis** | 2026-03-31 |
| **Min Android** | 13 (API 33) |

---

## 📂 Struktur Repo

```
updateRenma/
├── update.json          ← Manifest versi (dibaca otomatis oleh app)
├── releases/
│   └── changelog/
│       └── v1.0.md      ← Catatan rilis versi 1.0
└── README.md
```

---

## 🚀 Cara Merilis Versi Baru

### 1. Update `update.json`

Edit file `update.json` dan ubah bagian `latest`:

```json
{
  "latest": {
    "version_name": "X.Y",
    "version_code": N,
    "release_date": "YYYY-MM-DD",
    "mandatory": false,
    "download_url": "https://github.com/levanza1358/updateRenma/releases/download/vX.Y/renma-vX.Y.apk",
    "changelog": [
      "✨ Fitur baru: ...",
      "🐛 Perbaikan bug: ...",
      "⚡ Peningkatan performa: ..."
    ],
    "min_android": 13,
    "size_mb": 12.5
  }
}
```

### 2. Buat GitHub Release

1. Pergi ke tab **Releases** → **Draft a new release**
2. Tag: `vX.Y` (contoh: `v1.1`)
3. Upload file APK: `renma-vX.Y.apk`
4. Paste changelog dari `update.json`
5. Publish release

### 3. Commit & Push

```bash
git add update.json
git commit -m "release: vX.Y"
git push origin main
```

Aplikasi akan otomatis mendeteksi pembaruan pada pengecekan berikutnya.

---

## 🔔 Field `update.json`

| Field | Tipe | Keterangan |
|---|---|---|
| `version_name` | string | Versi yang ditampilkan (contoh: "1.1") |
| `version_code` | int | Angka versi untuk perbandingan (harus naik) |
| `release_date` | string | Tanggal rilis format YYYY-MM-DD |
| `mandatory` | bool | `true` = paksa update, tidak bisa skip |
| `download_url` | string | URL langsung download APK |
| `changelog` | string[] | Daftar perubahan (ditampilkan di in-app dialog) |
| `min_android` | int | Minimum versi Android yang didukung |
| `size_mb` | float | Ukuran APK dalam MB |
| `announcement` | string/null | Pengumuman khusus yang ditampilkan di app |
| `maintenance` | bool | `true` = tampilkan banner maintenance di app |

---

## 📬 Kontak

Pertanyaan atau laporan masalah: **support@miraya.my.id**

---

<div align="center">
  <sub>Made with ❤️ by <strong>Miraya Apps</strong></sub>
</div>
