# 📘 Tutorial Git & GitHub — Fauzi Rizky Maulana
**Peran:** Data Analyst & ML
**Branch:** `feature/data-analysis`

---

## Persiapan Awal (Lakukan Sekali Saja)

### 1. Install Git
Download di: https://git-scm.com/downloads → pilih Windows → install default.

### 2. Konfigurasi Identitas Git
Buka Git Bash, ketik:
```bash
git config --global user.name "Fauzi Rizky Maulana"
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

> ⚠️ Kamu satu branch dengan Firmansyah. Koordinasi dulu sebelum push supaya tidak konflik!

### 5. Cek Posisi Branch
```bash
git branch
```
Pastikan ada tanda `*` di `feature/data-analysis`.

---

## 🎯 Tugasmu

### Bagian A — Preprocessing Data

1. Terima `dataset_indonesia.csv` dari Firmansyah
2. Terapkan penanganan missing values:
```python
   df.interpolate(method='linear', inplace=True)
   # atau
   df.fillna(method='ffill', inplace=True)
```
3. Diskusikan dengan tim: outlier 1998 & 2020 dipertahankan atau tidak?
4. Terapkan StandardScaler — fit hanya pada training data:
```python
   from sklearn.preprocessing import StandardScaler
   scaler = StandardScaler()
   X_train_scaled = scaler.fit_transform(X_train)
   X_test_scaled = scaler.transform(X_test)
```
5. Pisahkan X (fitur) dan y (target: GDP_Growth)
6. Bagi dataset 80% training, 20% testing
7. Simpan scaler ke `models/scaler.pkl`:
```python
   import joblib
   joblib.dump(scaler, 'models/scaler.pkl')
```

### Bagian B — Modeling

1. Implementasikan 4 model:
```python
   from sklearn.linear_model import LinearRegression, Ridge
   from sklearn.tree import DecisionTreeRegressor
   from sklearn.ensemble import RandomForestRegressor
```

2. Gunakan Leave-One-Out Cross Validation (LOOCV):
```python
   from sklearn.model_selection import LeaveOneOut, cross_val_score
   loo = LeaveOneOut()
   scores = cross_val_score(model, X, y, cv=loo, scoring='r2')
```

3. Evaluasi menggunakan MAE, RMSE, R²:
```python
   from sklearn.metrics import mean_absolute_error, mean_squared_error, r2_score
```

4. Tampilkan feature importance / koefisien model

5. Pilih model terbaik (R² tertinggi, RMSE terendah)

6. Simpan model terbaik:
```python
   joblib.dump(best_model, 'models/best_model.pkl')
```

7. Buat tabel perbandingan performa semua model

### File yang Harus Kamu Buat:
| File | Keterangan |
|---|---|
| `notebooks/03_preprocessing.ipynb` | Notebook preprocessing |
| `notebooks/04_modeling.ipynb` | Notebook modeling |
| `models/scaler.pkl` | Objek scaler sudah di-fit |
| `models/best_model.pkl` | Model terbaik |
| `models/model_report.json` | Ringkasan performa model |
| `scripts/preprocessing.py` | Fungsi preprocessing |
| `scripts/model_trainer.py` | Script training model |

---

## Alur Kerja Harian

### Sebelum Mulai Kerja — Selalu Pull Dulu!
```bash
git pull origin develop
```

### Setelah Selesai Mengerjakan Sesuatu — Commit
```bash
git add .
git commit -m "✨ feat: selesai notebook preprocessing"
git push origin feature/data-analysis
```

---

## Format Pesan Commit

| Emoji | Jenis | Kapan Dipakai |
|---|---|---|
| ✨ | `feat:` | Notebook atau script baru |
| 🐛 | `fix:` | Memperbaiki error |
| 📝 | `docs:` | Update dokumentasi |
| ♻️ | `refactor:` | Merapikan kode |
| 🔧 | `config:` | Update konfigurasi model |

Contoh commit yang benar:
```
✨ feat: selesai notebook 03_preprocessing
✨ feat: selesai training 4 model ML
🐛 fix: perbaiki error LOOCV pada Ridge Regression
📝 docs: tambah ringkasan performa model di model_report.json
```

---

## Cara Buat Pull Request (Setelah Tugasmu Selesai)

1. Buka https://github.com/daifa-maulana/Machine-Learning_kelompok1
2. Klik tab **Pull requests** → **New pull request**
3. Atur:
   - **base:** `develop`
   - **compare:** `feature/data-analysis`
4. Isi judul: `✨ feat: selesai preprocessing & modeling`
5. Isi deskripsi singkat apa yang sudah dikerjakan
6. Klik **Create pull request**
7. Tunggu Daifa (PM) review dan merge

---

## ⚠️ Aturan Penting

- Koordinasi dengan Firmansyah sebelum push — kalian satu branch!
- Jangan push langsung ke `main` atau `develop`
- Selalu `git pull` sebelum mulai kerja
- Commit sering supaya progress terlacak

---

## Kalau Ada Error Umum

**Your branch is behind:**
```bash
git pull origin develop
```

**Conflict dengan Firmansyah:**
```bash
git pull origin feature/data-analysis
# Selesaikan conflict di VS Code, lalu:
git add .
git commit -m "🔧 fix: resolve merge conflict"
```

**Lupa di branch mana:**
```bash
git branch
```

---

## 👥 Koordinasi dengan Anggota Lain

- **Firmansyah (Anggota 2)** — tunggu `dataset_indonesia.csv` sebelum mulai preprocessing
- **Fajar (Anggota 7/Backend)** — serahkan `scaler.pkl`, `best_model.pkl`, dan logika preprocessing
- **Nazwa (Anggota 4/UI-UX)** — koordinasi desain visualisasi feature importance