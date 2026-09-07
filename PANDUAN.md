# Panduan Planner Alat Berat Pertambangan

Dokumen kerja untuk Equipment Planner / Maintenance Planner di tambang terbuka (open pit).

## 1. Peran

Planner Alat Berat merancang kapan, berapa unit, dan dalam kondisi apa armada dipakai agar target RKAB tercapai, downtime terkendali, dan biaya R&M tidak jebol.

Tiga fungsi yang diikat:

- Mine Planning — kebutuhan fleet sesuai sequence pit dan stripping ratio
- Plant / Maintenance — jadwal Preventive Maintenance berbasis SMH
- Production — Plan vs Actual, Match Factor, antrian loading point

### Tugas inti

1. Hitung kebutuhan alat gali-muat dan angkut
2. Hitung Match Factor (target mendekati 1,0)
3. Susun PM schedule 250 / 500 / 1.000 / 2.000 SMH
4. Forecast spare part kritis
5. Pantau KPI: PA, UA, MA, MTBF, MTTR, fuel burn
6. Koordinasi production vs workshop
7. Review cycle time (time study)
8. Laporan Plan vs Actual mingguan

## 2. KPI

| Kode | Nama | Arti lapangan | Rumus |
| --- | --- | --- | --- |
| PA | Physical Availability | Unit tidak rusak / tidak PM panjang | (W + S) / T |
| MA | Mechanical Availability | Rusak vs kerja | W / (W + R) |
| UA | Use of Availability | Waktu available yang dipakai produksi | W / (W + S) |
| EU | Effective Utilization | Porsi waktu total yang produktif | W / T |
| SMH | Service Meter Hours | Jam meter mesin | Hour meter unit |
| MTBF | Mean Time Between Failures | Jam operasi antar kerusakan | SMH operasi / jumlah BD |
| MTTR | Mean Time To Repair | Jam perbaikan per breakdown | Jam perbaikan / jumlah BD |

W = working hours, R = repair hours, S = standby hours, T = W + R + S.

Target tipikal site batubara Kalimantan: PA 85–90%, UA 80–85%, MA ≥ 90% untuk fleet baru.

## 3. Match Factor

- MF < 1 = undertruck (excavator menunggu truk)
- MF > 1 = overtruck (truk antri di loading point)

N truk ideal ≈ Cycle Time truk ÷ waktu muat per truk

Target MF sehat: 0,90 – 1,10.

## 4. Rumus produktivitas

### Excavator (BCM/jam)

Qexc = (q × Ff / Sf × 3600 / Tdetik) × PA × UA

- q = bucket heaped (m3)
- Ff = fill factor (OB lunak 0,85–0,95)
- Sf = swell factor (claystone Kalsel 1,25–1,40)
- Tdetik = cycle time gali-muat (24–32 detik)

Jangan samakan BCM (volume in-situ) dengan LCM (volume gembur di bak truk).

### Dump truck

CTtruk (menit) = t_load + (2 × jarak_km / v_rata) × 60 + t_dump + t_spot

Kecepatan realistis haul road basah: loaded 16–20 km/jam, empty 22–28 km/jam.

### Jumlah unit

N = Target BCM bulanan ÷ (produktivitas 1 unit × jam efektif per bulan)

Selalu ROUNDUP. Sisakan cadangan 10–15% untuk hujan, pit crowding, dan PM.

## 5. Preventive Maintenance (SMH)

| Interval | Nama | Isi utama |
| --- | --- | --- |
| 250 SMH | PM-A | Filter oli + fuel primer, grease, inspect hose |
| 500 SMH | PM-B | PM-A + oli engine, undercarriage |
| 1.000 SMH | PM-C | PM-B + oli hidraulik / OAS, final drive |
| 2.000 SMH | PM-D | PM-C + oli transmisi / torque converter |
| 6.000–12.000 | Overhaul | Engine, pump hidraulik, final drive rebuild |

Sheet `07_PM_PLANNER` menandai URGENT jika sisa SMH ≤ 50 jam.

## 6. Cara pakai workbook

Sel kuning + angka biru = INPUT. Jangan timpa sel rumus.

1. `01_COVER` — identitas site
2. `02_ASUMSI` — jam kerja, PA, UA, swell, target RKAB, jarak angkut
3. `03_FLEET` — daftar unit, status, SMH, lokasi front
4. `04_PRODUKTIVITAS` — cycle time time study
5. `05_MATCH_FACTOR` — undertruck / overtruck
6. `06_KEBUTUHAN` — gap unit vs operasi
7. `07_PM_PLANNER` — unit URGENT service
8. `08_DASHBOARD` — ringkasan meeting pagi

## 7. Checklist

### Harian

- Update SMH dari FMS / timesheet
- Cek unit URGENT (sisa ≤ 50 SMH)
- Pantau antrian loading point
- Catat breakdown baru

### Mingguan

- Rekap Plan vs Actual OB dan batubara
- Hitung PA, UA, MA aktual
- Review fuel burn
- Koordinasi roster mekanik vs slot PM

### Bulanan

- Time study cycle time ulang
- Update swell dan fill factor jika material berubah
- Forecast spare part 30–60 hari (termasuk ban OTR)
- Rekomendasi sewa / pindah front / rebuild

## 8. Acuan

- Kepmen ESDM 1827 K/30/MEM/2018 Lampiran II (perencanaan tambang dan kebutuhan peralatan)
- SMKP Minerba
- Manual OEM Komatsu / CAT / Hitachi / Sany
- Kontrak jasa pertambangan (target PA dan denda breakdown)
- RKAB tahunan

Template ini indikatif. Perhitungan desain pit dan geoteknik wajib dikerjakan engineer berwenang dan disetujui Kepala Teknik Tambang.

Revisi 00 — September 2026
