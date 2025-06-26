# UsernameHunter

[![Python](https://img.shields.io/badge/python-3.8%2B-blue?logo=python)](https://www.python.org/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Contributors](https://img.shields.io/github/contributors/FerzDevZ/UsernameHunter)](https://github.com/FerzDevZ/UsernameHunter/graphs/contributors)
[![Issues](https://img.shields.io/github/issues/FerzDevZ/UsernameHunter)](https://github.com/FerzDevZ/UsernameHunter/issues)
[![Stars](https://img.shields.io/github/stars/FerzDevZ/UsernameHunter?style=social)](https://github.com/FerzDevZ/UsernameHunter)
[![PyPI version](https://img.shields.io/pypi/v/usernamehunter?color=blue)](https://pypi.org/project/usernamehunter/) <!-- Remove if not on PyPI -->
[![Build Status](https://img.shields.io/github/actions/workflow/status/FerzDevZ/UsernameHunter/python-app.yml?branch=main)](https://github.com/FerzDevZ/UsernameHunter/actions) <!-- Remove if not using CI -->

> **UsernameHunter** — Advanced & Modern Username Checker for 200+ Social Media & Viral Sites (Global & Indonesia) 🚀

---

## 📝 Deskripsi

UsernameHunter adalah tools open-source untuk melakukan pengecekan ketersediaan username di ratusan platform sosial media, marketplace, dan situs viral secara paralel, cepat, dan modern. Mendukung pencarian multi-username, plugin, proxy, filter hasil, progress bar, output warna, statistik, chart, logging, wizard interaktif, dan ekspor hasil ke berbagai format.

- **Multi-platform:** Cek username di ratusan situs (global, Indonesia, viral, niche)
- **Paralel & Efisien:** ThreadPoolExecutor, progress bar multi-level
- **Ekstensi Mudah:** Plugin, custom JSON, modularisasi penuh
- **Visual & Logging:** Output warna, chart, logging detail, riwayat, statistik
- **Automation Ready:** CLI, config YAML/JSON, mode silent, cron/scheduler friendly

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
- **Auto-create config** (YAML/JSON)
- **Export chart otomatis ke PNG** (headless)
- **Extensible & automation ready**

---

## 🏗️ Arsitektur Modular

```
app/
├── uh.py                # Main CLI & entrypoint
├── platforms.py         # Daftar platform utama
├── proxy/
│   └── proxy.py         # Manajemen proxy (rotasi, validasi)
├── validation/
│   └── validation.py    # Validasi username (global & per platform)
├── plugins_mod/
│   └── plugins.py       # Loader plugin (folder & custom JSON)
├── exporter/
│   └── exporter.py      # Export hasil (JSON, CSV, TXT, stub Excel)
├── search/
│   └── search.py        # Core search, filter, statistik, riwayat, output warna
├── plugins/
│   └── contoh.py        # Contoh plugin platform
├── config.json          # Config default (auto-create)
├── history.jsonl        # Riwayat pencarian
├── hasil_chart.png      # Output chart jika headless
```

**Penjelasan Modular:**
- **proxy/**: Manajemen proxy, auto-rotate, validasi proxy pool
- **validation/**: Validasi username (regex, per platform, custom rule)
- **plugins_mod/**: Loader plugin platform (folder & custom JSON)
- **exporter/**: Export hasil ke berbagai format (JSON, CSV, TXT, stub Excel)
- **search/**: Core pencarian, filter, statistik, riwayat, output warna
- **plugins/**: Contoh plugin platform custom

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
   pip install -r requirements.txt
   # Untuk fitur chart: pip install matplotlib
   # Untuk config YAML: pip install pyyaml
   # Untuk output warna: pip install rich
   # Untuk progress bar: pip install tqdm
   # Untuk export Excel: pip install pandas openpyxl
   # Untuk plugin/ekstensi: pip install requests colorama
   ```
   > **Tips:**
   > - Untuk semua fitur lanjutan: `pip install matplotlib pyyaml rich tqdm pandas openpyxl requests colorama`
   > - Untuk environment terisolasi: `python3 -m venv venv && source venv/bin/activate && pip install -r requirements.txt`
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

## 🖥️ Contoh Output CLI

```bash
$ python3 uh.py johndoe --only-found
[Instagram] Terdaftar
  URL: https://instagram.com/johndoe
  Username ditemukan di Instagram
[Twitter] Tidak Terdaftar
  URL: https://twitter.com/johndoe
  Username tidak ditemukan di Twitter
...dst
```

---

## 🧩 Modular Tools & Advanced Usage

### 1. **Proxy**
- Atur file proxy: `--proxy-file proxy.txt`
- Otomatis rotate proxy setiap request
- Support proxy pool dari API (coming soon)

### 2. **Validation**
- Validasi username otomatis & per platform
- Custom rule di `validation/validation.py`

### 3. **Plugins**
- Tambah platform baru via folder `plugins/` atau file JSON custom
- Contoh plugin: `app/plugins/contoh.py`
- Plugin eksternal (pip installable, roadmap)

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

## 🤖 Integrasi Automation & Cron

- Jalankan otomatis via cron/scheduler:
  ```bash
  0 * * * * cd /path/to/UsernameHunter/app && python3 uh.py --username-file daftar.txt --output hasil.json --silent --logfile cron.log
  ```
- Integrasi dengan notifikasi (Telegram/Discord/email): roadmap
- Export otomatis ke Google Drive/Dropbox: roadmap

---

## 🛡️ Security & Privacy
- Tidak menyimpan password/user credential
- Semua request hanya GET ke public profile
- Tidak mengirim data ke server eksternal (kecuali plugin custom)
- History & log hanya lokal

---

## 🛠️ Troubleshooting
- **matplotlib error:**
  - Install: `pip install matplotlib`
  - Jika warning headless, chart otomatis disimpan ke PNG
- **pyyaml error:**
  - Install: `pip install pyyaml`
- **rich/tqdm error:**
  - Install: `pip install rich tqdm`
- **Permission error:**
  - Jalankan dengan akses yang benar, atau gunakan virtualenv
- **Proxy error:**
  - Pastikan proxy valid dan tidak diblokir
- **Export Excel error:**
  - Install: `pip install pandas openpyxl`

---

## 📚 Dokumentasi & Referensi
- [Wiki & FAQ](https://github.com/FerzDevZ/UsernameHunter/wiki)
- [Contoh Plugin](app/plugins/contoh.py)
- [CONTRIBUTING.md](CONTRIBUTING.md)
- [CHANGELOG.md](CHANGELOG.md)

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
- **Bagaimana menambah plugin eksternal?**
  - Roadmap: plugin pip installable, cek [Wiki](https://github.com/FerzDevZ/UsernameHunter/wiki)
- **Bagaimana troubleshooting error dependency?**
  - Lihat bagian troubleshooting di atas

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
- Dokumentasi API & REST (roadmap)

---

## 🤝 Kontribusi

Pull request, issue, dan saran sangat terbuka! Lihat [CONTRIBUTING.md](CONTRIBUTING.md) untuk panduan kontribusi.

---

## 📄 Lisensi

MIT License © [FerzDevZ](https://github.com/FerzDevZ) & [ferztap](https://github.com/ferztap)
