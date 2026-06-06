# 🇮🇩 Prediksi GDP Growth Indonesia

Proyek Machine Learning untuk memprediksi laju pertumbuhan ekonomi (GDP Growth) 
Indonesia berdasarkan tujuh indikator ekonomi makro menggunakan data World Bank 
(1991–2024).

---

## 👥 Anggota Kelompok

| No | Nama | Peran |
|---|---|---|
| 1 | Daifa Maulana | Project Manager |
| 2 | Mochamad Firmansyah | Data Analyst & ML |
| 3 | Fauzi Rizky Maulana | Data Analyst & ML |
| 4 | Nazwa Nur Hapidah | UI/UX Designer |
| 5 | Dini Sriastuti | Frontend Developer |
| 6 | Muhammad Raufan Umarulloh | Frontend Developer |
| 7 | Fajar Muhammad Ramdhani | Backend & Deployment |

---

## 🛠️ Teknologi yang Digunakan

* **Bahasa Pemrograman:** Python
* **Machine Learning:** Scikit-Learn, Pandas, NumPy
* **Frontend/Deployment:** Streamlit
* **Visualisasi:** Matplotlib, Seaborn, Plotly

---

## ✨ Fitur Utama

1. **Eksplorasi Data (EDA):** Menampilkan visualisasi tren ekonomi makro Indonesia.
2. **Prediksi GDP:** Pengguna dapat memasukkan indikator ekonomi untuk melihat proyeksi GDP Growth.
3. **Evaluasi Model:** Menampilkan metrik performa model Machine Learning yang digunakan.

---

## 📊 Variabel yang Digunakan

| Variabel | Keterangan |
|---|---|
| GDP Growth | Target — Pertumbuhan ekonomi (% per tahun) |
| Inflation | Tingkat inflasi tahunan (%) |
| Unemployment | Tingkat pengangguran (%) |
| Population Growth | Pertumbuhan populasi (%) |
| Exports | Nilai ekspor (% dari GDP) |
| Imports | Nilai impor (% dari GDP) |
| FDI | Foreign Direct Investment (% dari GDP) |
| Exchange Rate | Nilai tukar Rupiah terhadap USD |

---

## ⚙️ Cara Install

```bash
git clone [https://github.com/daifa-maulana/Machine-Learning_kelompok1.git]
cd Machine-Learning_kelompok1
pip install -r requirements.txt

```

---

## ▶️ Cara Menjalankan Website

```bash
streamlit run app.py

```

---

## 🗂️ Struktur Folder

```text
Machine-Learning_kelompok1/
├── data/
│   ├── raw/          ← Data mentah per indikator dari World Bank
│   └── processed/    ← dataset_indonesia.csv (final)
├── notebooks/        ← Notebook eksplorasi & modeling
├── models/           ← best_model.pkl, scaler.pkl
├── scripts/          ← preprocessing.py, visualization.py
├── pages/            ← Halaman-halaman Streamlit
├── assets/           ← CSS, gambar
├── docs/             ← Dokumentasi, laporan, meeting notes
│   └── tutorial/     ← Panduan Git & GitHub per anggota tim
├── presentation/     ← Slide presentasi
├── app.py            ← Entry point Streamlit
└── requirements.txt

```

---

## 📖 Panduan Kontribusi Tim

Untuk panduan alur kerja Git dan GitHub masing-masing anggota tim, silakan cek tautan berikut:

* [Tutorial Git - Daifa (PM)](https://www.google.com/search?q=docs/tutorial/01_daifa_pm.md)
* [Tutorial Git - Firmansyah (Data Analyst)](https://www.google.com/search?q=docs/tutorial/02_firmansyah_data.md)
* [Tutorial Git - Fauzi (Machine Learning)](https://www.google.com/search?q=docs/tutorial/03_fauzi_ml.md)
* [Tutorial Git - Nazwa (UI/UX)](https://www.google.com/search?q=docs/tutorial/04_nazwa_uiux.md)
* [Tutorial Git - Dini (Frontend)](https://www.google.com/search?q=docs/tutorial/05_dini_frontend.md)
* [Tutorial Git - Raufan (Frontend)](https://www.google.com/search?q=docs/tutorial/06_raufan_frontend.md)
* [Tutorial Git - Fajar (Backend)](https://www.google.com/search?q=docs/tutorial/07_fajar_backend.md)

---

## 🌐 Link Website

> Akan diupdate setelah deployment selesai

---

## 📄 Lisensi

Proyek ini dibuat untuk keperluan Mata Kuliah Machine Learning.

```

```