# Bisnis.com Crawler & Scraper

Crawler dan scraper sederhana untuk mengambil artikel dari [bisnis.com](https://www.bisnis.com).  
Project ini memiliki dua mode eksekusi: **Backtrack** untuk mengambil artikel berdasarkan tanggal, dan **Standard** untuk memonitor artikel terbaru secara periodik.

---

## Fitur

1. **Backtrack Mode**  
   - Mengambil artikel dari rentang tanggal tertentu (`start_date` – `end_date`).  
   - Output: JSON berisi daftar artikel dengan field:
     - `Title` → Judul artikel  
     - `Link` → URL artikel  
     - `Content` → Isi artikel dalam bentuk teks  
     - `Time` → Tanggal terbit artikel (ISO 8601, `YYYY-MM-DD`)  

2. **Standard Mode**  
   - Monitoring artikel terbaru secara periodik.  
   - Output: JSON baru setiap kali artikel baru muncul, dengan field tambahan:
     - `ScrapedAt` → Waktu artikel di-scrape (ISO 8601)  
   - **Catatan:** Jika tidak ada artikel baru saat eksekusi, **tidak akan ada file JSON** yang dibuat.

---

## Contoh JSON

**Backtrack Mode**
```json
[
  {
    "Title": "IHSG Dibuka Menguat",
    "Link": "https://www.bisnis.com/market/20250925/194/123456/ihsg-dibuka-menguat",
    "Content": "Indeks Harga Saham Gabungan (IHSG) dibuka menguat pada perdagangan...",
    "Time": "2025-09-25"
  }
]
