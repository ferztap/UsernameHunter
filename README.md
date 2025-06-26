# UsernameHunter

[![Python](https://img.shields.io/badge/python-3.8%2B-blue?logo=python)](https://www.python.org/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Contributors](https://img.shields.io/github/contributors/FerzDevZ/UsernameHunter)](https://github.com/FerzDevZ/UsernameHunter/graphs/contributors)
[![Issues](https://img.shields.io/github/issues/FerzDevZ/UsernameHunter)](https://github.com/FerzDevZ/UsernameHunter/issues)
[![Stars](https://img.shields.io/github/stars/FerzDevZ/UsernameHunter?style=social)](https://github.com/FerzDevZ/UsernameHunter)

> **UsernameHunter** — Advanced & Modern Username Checker for 200+ Social Media & Viral Sites (Global & Indonesia) 🚀

Cek ketersediaan username di ratusan platform sosial media global, Indonesia, dan situs viral secara paralel, cepat, dan modern. Mendukung fitur pencarian multi-username, plugin, proxy, filter hasil, progress bar, output warna, statistik, chart, logging, wizard interaktif, dan ekspor hasil ke berbagai format.

---

## ✨ Fitur Utama
- **Cek username** di ratusan platform (global, Indonesia, viral)
- **Multi-username & multi-platform search**
- **Pencarian paralel** (ThreadPoolExecutor)
- **Validasi username otomatis & per platform**
- **Proxy otomatis & retry**
- **Plugin system** (folder plugins/ & custom JSON)
- **Export hasil:** JSON, CSV, TXT
- **Filter hasil:** hanya ditemukan/tidak ditemukan/gagal
- **Progress bar multi-level** (rich)
- **Output warna** (rich, emoji)
- **Mode silent & logfile**
- **Riwayat pencarian** (`--history`)
- **Statistik hasil** (`--stats`)
- **Visualisasi chart** (`--chart`)
- **Mode wizard interaktif** (`--wizard`)
- **Logging detail** (`--loglevel`)
- **Dokumentasi CLI bilingual, FAQ, tips** (`--faq`, `--tips`)

---

## 📦 Struktur Modular

```
app/
├── uh.py                # Main CLI & entrypoint
├── platforms.py         # Daftar platform utama
├── proxy/
│   └── proxy.py         # Manajemen proxy
├── validation/
│   └── validation.py    # Validasi username
├── plugins_mod/
│   └── plugins.py       # Loader plugin
├── exporter/
│   └── exporter.py      # Export hasil (JSON, CSV, TXT)
├── search/
│   └── search.py        # Core search, filter, statistik, riwayat
├── plugins/
│   └── contoh.py        # Contoh plugin platform
├── config.json          # Config default (auto-create)
├── history.jsonl        # Riwayat pencarian
├── hasil_chart.png      # Output chart jika headless
```

---

## 👤 Author & Kontributor

- **Owner:** [@FerzDevZ](https://github.com/FerzDevZ)
- **Project Team:** [ferztap](https://github.com/ferztap)
- **Contributors:**
  - [@callysta-cloud](https://github.com/callysta-cloud)
  - [@ChristianAngelo1](https://github.com/ChristianAngelo1)
  - [@EnnVyy7](https://github.com/EnnVyy7)
  - [@HoseajsJ](https://github.com/HoseajsJ)
  - [@JusdyParla](https://github.com/JusdyParla)
  - [@KieranYui](https://github.com/KieranYui)
  - [@rianmmuahamad](https://github.com/rianmmuahamad)
  - [@Feng-Liuz](https://github.com/Feng-Liuz)
  - [@frrllxs](https://github.com/frrllxs)

---

## 🚀 Cara Instalasi

1. **Clone repository:**
   ```bash
   git clone https://github.com/FerzDevZ/UsernameHunter.git
   cd UsernameHunter/app
   ```
2. **Install semua dependencies utama dan opsional:**
   ```bash
   # Install semua dependensi utama dan opsional sekaligus
   pip install -r requirements.txt
   # Untuk fitur chart: pip install matplotlib
   # Untuk config YAML: pip install pyyaml
   # Untuk output warna: pip install rich
   # Untuk progress bar: pip install tqdm
   # Untuk export Excel: pip install pandas openpyxl
   # Untuk plugin/ekstensi: pip install requests colorama
   ```
   > **Tips:**
   > - Jika ingin semua fitur lanjutan aktif, install juga: `pip install matplotlib pyyaml rich tqdm pandas openpyxl requests colorama`
   > - Untuk environment terisolasi, gunakan [venv](https://docs.python.org/3/library/venv.html):
   >   ```bash
   >   python3 -m venv venv
   >   source venv/bin/activate
   >   pip install -r requirements.txt
   >   ```
   > - Jika ada error dependency, update pip: `python3 -m pip install --upgrade pip`

---

## ⚡️ Penggunaan Simpel

Cek satu username:
```bash
python3 uh.py johndoe
```
Cek banyak username:
```bash
python3 uh.py johndoe janedoe --only-found
```
Cek dari file:
```bash
python3 uh.py --username-file daftar.txt --output hasil.json
```
Lihat semua platform:
```bash
python3 uh.py --list-platforms
```
Export hasil ke CSV:
```bash
python3 uh.py johndoe --output hasil.csv
```
Tampilkan chart ringkasan:
```bash
python3 uh.py --chart
```

---

## 🧩 Modular Tools & Advanced Usage

### 1. **Proxy**
- Atur file proxy: `--proxy-file proxy.txt`
- Otomatis rotate proxy setiap request

### 2. **Validation**
- Validasi username otomatis & per platform
- Bisa custom rule di `validation/validation.py`

### 3. **Plugins**
- Tambah platform baru via folder `plugins/` atau file JSON custom
- Contoh plugin: `app/plugins/contoh.py`

### 4. **Exporter**
- Export hasil ke JSON, CSV, TXT
- (Coming soon: Excel, Google Sheets, Database)

### 5. **Search**
- Pencarian paralel, filter hasil, statistik, riwayat
- Progress bar multi-level (tqdm & rich)

### 6. **Config**
- Otomatis generate `config.json` jika belum ada
- Bisa pakai YAML/JSON: `--config config.yaml`

### 7. **Logging & Silent Mode**
- Logging detail: `--logfile hasil.log --loglevel debug`
- Mode silent: `--silent`

### 8. **Wizard & Chart**
- Wizard interaktif: `--wizard` (coming soon)
- Visualisasi chart: `--chart` (pie chart, auto-save PNG jika headless)

---

## 📝 Contoh Perintah Lain

- Tampilkan riwayat pencarian:
  ```bash
  python3 uh.py --history
  ```
- Tampilkan statistik hasil:
  ```bash
  python3 uh.py --stats
  ```
- Tampilkan FAQ & tips:
  ```bash
  python3 uh.py --faq
  python3 uh.py --tips
  ```

---

## ❓ FAQ

- **Bagaimana export ke Excel?**
  - Gunakan `--output hasil.xlsx` (fitur segera hadir, sementara gunakan .csv)
- **Bagaimana menambah platform baru?**
  - Tambahkan di custom JSON atau folder plugins.
- **Bagaimana agar hasil hanya ke file, tidak ke layar?**
  - Gunakan `--silent --logfile hasil.log`
- **Bagaimana monitoring otomatis?**
  - Jalankan dengan cron/scheduler dan gunakan `--logfile`.

---

## 🛠️ Roadmap & Fitur Mendatang
- Export ke Excel (.xlsx), Google Sheets, Database
- Notifikasi Telegram/Discord/email/WhatsApp
- Monitoring username otomatis (scheduler/cron)
- Integrasi headless browser (Selenium/Playwright)
- GUI (web/desktop: Streamlit, Tkinter, Electron)
- Export otomatis ke Google Drive/Dropbox
- Saran username (username generator)
- Plugin eksternal (pip installable)
- Auto-update daftar platform dari repo/URL
- Visualisasi chart lain (bar, dsb)
- Unit test & CI/CD, installer (pip/docker/exe)

---

## 🤝 Kontribusi

Pull request, issue, dan saran sangat terbuka! Lihat [CONTRIBUTING.md](CONTRIBUTING.md) untuk panduan kontribusi.

---

## 📄 Lisensi

MIT License © [FerzDevZ](https://github.com/FerzDevZ) & [ferztap](https://github.com/ferztap)
