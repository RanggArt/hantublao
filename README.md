# Rekap Kebakaran Jakarta Utara

## Struktur File

```
rekap-kebakaran/
├── index.html   ← Halaman utama (HTML saja, tidak perlu diedit)
├── style.css    ← Semua tampilan & warna
├── data.js      ← SEMUA DATA KEJADIAN (edit ini untuk update!)
├── app.js       ← Logika chart, tabel, filter, PDF (jarang diedit)
└── README.md    ← Panduan ini
```

## Cara Update Data Bulanan

Buka `data.js`, cari bagian yang ingin diupdate:

### 1. Tambah data warga terdampak (di `allData`)
```js
"allData": {
  "2026": {
    wargaTotal: 10,           // ← update total
    wargaData: {
      "Juni": { "Penjaringan": 1, ... }  // ← tambah bulan baru
    }
  }
}
```

### 2. Update ringkasan per kecamatan (`kecData`)
```js
"Penjaringan": { frek: 12, kerugian: "Rp 1,2M", sektor: "Pemukiman" },
```

### 3. Tambah kejadian detail (`masterFireData`)
```js
"Nama Kelurahan": {
  "Juni": [
    {
      hari:"Senin", tgl:"2/6/2026", jenis:"Rumah Tinggal",
      alamat:"Jl. Contoh No.1", rt:"3", rw:"5",
      penyebab:"Korsleting", luas:"50", kk:"2", jiwa:"6",
      luka:"-", meninggal:"-", kerugian:"Rp50jt",
      petugas:"1", warga:"-", jmlUnit:"4"
    }
  ]
}
```

## Cara Membuka

Karena menggunakan beberapa file terpisah, **tidak bisa dibuka langsung** dengan double-click.

Gunakan salah satu cara berikut:
- **VS Code** → Install ekstensi *Live Server* → klik kanan `index.html` → *Open with Live Server*
- **Python** → Buka terminal di folder ini → jalankan: `python -m http.server 8000` → buka `http://localhost:8000`
