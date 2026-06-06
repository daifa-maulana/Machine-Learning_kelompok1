# 📘 Tutorial Git & GitHub — Mochamad Firmansyah
**Peran:** Data Analyst & ML
**Branch:** `feature/data-analysis`

---

## Persiapan Awal (Lakukan Sekali Saja)

### 1. Install Git
Download di: https://git-scm.com/downloads → pilih Windows → install default.

### 2. Konfigurasi Identitas Git
Buka Git Bash, ketik:
```bash
git config --global user.name "Mochamad Firmansyah"
git config --global user.email "email_kamu@gmail.com"
```

### 3. Clone Repo
```bash
git clone https://github.com/daifa-maulana/Machine-Learning_kelompok1.git
cd Machine-Learning_kelompok1
```

### 4. Pindah ke Branch Kamu
```bash
git checkout -b feature/data-analysis origin/develop
```

### 5. Cek Posisi Branch
```bash
git branch
```
Pastikan ada tanda `*` di `feature/data-analysis`.

---

## 🎯 Tugasmu

### Yang Harus Kamu Kerjakan:
1. Unduh semua 8 indikator dari World Bank untuk Indonesia (1991–2024)
   - Buka: https://data.worldbank.org
   - Filter: Country = Indonesia
   - Download format CSV per indikator
   - Simpan di folder `data/raw/`

2. Gabungkan semua CSV menjadi satu file `dataset_indonesia.csv`
   - Kolom: `Year, GDP_Growth, Inflation, Unemployment, Population_Growth, Exports, Imports, FDI, Exchange_Rate`
   - Simpan di `data/processed/`

3. Data Validation — cek di notebook:
   - Tipe data setiap kolom
   - Rentang nilai wajar
   - Duplikasi baris
   - Konsistensi tahun

4. Data Quality Checking:
   - Hitung persentase missing value per kolom
   - Identifikasi outlier ekstrem (boxplot sederhana)
   - Catat temuan di `docs/data_quality_report.md`

5. Buat `docs/data_dictionary.md`:
   - Nama variabel, satuan, kode indikator World Bank
   - Rentang tahun, jumlah missing

6. Hitung korelasi awal:
```python
   df.corr()
```
   Simpan hasilnya sebagai referensi untuk Fauzi (EDA & ML)

### File yang Harus Kamu Buat:
| File | Keterangan |
|---|---|
| `data/raw/*.csv` | Data mentah per indikator |
| `data/processed/dataset_indonesia.csv` | Dataset final |
| `docs/data_dictionary.md` | Kamus data |
| `docs/data_quality_report.md` | Laporan kualitas data |
| `notebooks/01_data_collection.ipynb` | Notebook pengumpulan data |

---

## Alur Kerja Harian

### Sebelum Mulai Kerja — Selalu Pull Dulu!
```bash
git pull origin develop
```

### Setelah Selesai Mengerjakan Sesuatu — Commit
```bash
git add .
git commit -m "🗃️ data: tambah file dataset_indonesia.csv"
git push origin feature/data-analysis
```

---

## Format Pesan Commit

| Emoji | Jenis | Kapan Dipakai |
|---|---|---|
| 🗃️ | `data:` | Menambah atau update dataset |
| 📝 | `docs:` | Update dokumentasi / data dictionary |
| ✨ | `feat:` | Menambahkan fitur / notebook baru |
| 🐛 | `fix:` | Memperbaiki error |
| ♻️ | `refactor:` | Merapikan kode |

Contoh commit yang benar:
```
🗃️ data: tambah raw CSV inflasi dari World Bank
📝 docs: tambah data_dictionary.md
✨ feat: selesai notebook 01_data_collection
🐛 fix: perbaiki error merge dataset tahun 1998
```

---

## Cara Buat Pull Request (Setelah Tugasmu Selesai)

1. Buka https://github.com/daifa-maulana/Machine-Learning_kelompok1
2. Klik tab **Pull requests** → **New pull request**
3. Atur:
   - **base:** `develop`
   - **compare:** `feature/data-analysis`
4. Isi judul: `✨ feat: selesai data collection & validasi`
5. Isi deskripsi singkat apa yang sudah dikerjakan
6. Klik **Create pull request**
7. Tunggu Daifa (PM) review dan merge

---

## ⚠️ Aturan Penting

- Jangan push langsung ke `main` atau `develop`
- Selalu `git pull` sebelum mulai kerja
- Commit sering — jangan tunggu selesai semua baru commit
- Gunakan akun GitHub pribadi supaya kontribusi terlacak dosen

---

## Kalau Ada Error Umum

**Your branch is behind:**
```bash
git pull origin develop
```

**Please commit your changes before merging:**
```bash
git add .
git commit -m "📝 docs: simpan progress sementara"
git pull origin develop
```

**Lupa di branch mana:**
```bash
git branch
```

---

## 👥 Koordinasi dengan Anggota Lain

- **Fauzi (Anggota 3)** — serahkan `dataset_indonesia.csv` dan hasil korelasi awal setelah selesai
- **Daifa/PM (Anggota 1)** — kirimkan `data_quality_report.md` untuk dokumentasi