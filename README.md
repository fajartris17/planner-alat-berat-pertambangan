# Planner Alat Berat Pertambangan

Template kerja untuk **Equipment Planner / Maintenance Planner** di tambang terbuka (*open pit*), khususnya site batubara Kalimantan.

Repositori: https://github.com/fajartris17/planner-alat-berat-pertambangan

## File dalam paket

| File | Fungsi |
| --- | --- |
| `Planner_Alat_Berat_Pertambangan.xlsx` | Workbook 8 sheet: asumsi, fleet, produktivitas, match factor, kebutuhan unit, PM berbasis SMH, dashboard KPI |
| `Panduan_Planner_Alat_Berat_Pertambangan.docx` | Panduan kerja: peran planner, rumus, arti KPI (PA, UA, MA, MF), checklist harian-bulanan |
| `PANDUAN.md` | Versi Markdown dari panduan kerja |

## Cara pakai workbook

1. Isi identitas site di sheet `01_COVER` (sel kuning = input).
2. Sesuaikan jam kerja, PA, UA, swell, fill factor, dan target RKAB di `02_ASUMSI`.
3. Update daftar unit, status, dan SMH aktual di `03_FLEET`.
4. Masukkan cycle time hasil *time study* ke `04_PRODUKTIVITAS`.
5. Baca *Match Factor* dan gap unit di `05` dan `06`.
6. Kunci jadwal service di `07_PM_PLANNER` (interval 250 / 500 / 1.000 / 2.000 SMH).
7. Cetak `08_DASHBOARD` untuk morning meeting.

Jangan mengetik di sel rumus.

## KPI yang dipakai

- **PA** (*Physical Availability*) — ketersediaan fisik unit
- **MA** (*Mechanical Availability*) — ketersediaan mekanis
- **UA** (*Use of Availability*) — pemanfaatan waktu available
- **MF** (*Match Factor*) — kesesuaian jumlah hauler vs loader (target 0,90–1,10)
- **SMH** (*Service Meter Hours*) — dasar jadwal Preventive Maintenance

## Catatan

Angka default bersifat tipikal site batubara terbuka Kalimantan, **bukan** hasil time study site Anda. Keputusan final jumlah alat, setting fleet, dan jadwal PM wajib merujuk data aktual, Kepmen ESDM 1827 K/30/MEM/2018, RKAB, SMKP, manual OEM, dan persetujuan Kepala Teknik Tambang.

## Pemilik

Akun GitHub: [fajartris17](https://github.com/fajartris17)

Revisi template: Rev. 00 — September 2026
