# MRT Link — Proposal Strengthening Pack

Dokumen ini mendampingi prototype interaktif MRT Link. Tujuannya bukan menambah sebanyak mungkin fitur, melainkan memperjelas alasan bisnis, batas novelty, cara menguji dampak, dan cerita yang perlu dilihat juri.

## 1. Rekomendasi posisi produk

**MRT Link adalah lapisan orkestrasi perjalanan door-to-door berbasis MRT yang membantu calon pengguna memilih MRT sebelum berangkat dan menjaga koneksi antarmoda selama perjalanan.**

Rekomendasi implementasi untuk proposal: posisikan MRT Link sebagai **modul/kapabilitas baru di dalam ekosistem MyMRTJ**, bukan aplikasi konsumen baru yang berdiri sendiri. Nama “MRT Link” tetap dapat dipakai sebagai nama fitur atau product layer. Posisi ini:

- memanfaatkan basis pengguna, tiket, pembayaran, dan layanan feeder yang sudah dimiliki MyMRTJ;
- mengurangi keberatan juri berupa “mengapa perlu aplikasi lain?”;
- memperjelas novelty pada keputusan dan orkestrasi perjalanan, bukan pada fitur dasar yang sudah tersedia;
- menurunkan risiko adopsi dan biaya go-to-market.

Prototype memakai identitas MRT Link tersendiri agar konsep mudah dipresentasikan, tetapi MVP yang disarankan adalah modul di MyMRTJ.

## 2. Problem statement yang lebih tajam

> MRT sudah dapat melayani bagian utama perjalanan, tetapi keputusan menggunakan MRT sering gagal sebelum pengguna tiba di stasiun. Ketidakpastian akses first mile dan risiko koneksi antarmoda membuat kendaraan pribadi terasa lebih sederhana. MRT Link mengintervensi dua titik tersebut: saat memilih moda dan saat berpindah moda.

Kekuatan problem ini adalah keterkaitannya dengan bisnis. MRT Jakarta menyatakan feeder berkontribusi sekitar **22–23% dari total ridership** dan menyebut first/last mile sebagai alasan agar masyarakat terus menggunakan transportasi umum serta perlahan meninggalkan kendaraan pribadi. Itu memberi dasar resmi bahwa feeder bukan fitur pelengkap semata, melainkan salah satu pengungkit ridership.[^1]

## 3. Why now dan benchmark MyMRTJ

Listing resmi MyMRTJ saat ini sudah menyebut pembelian dan langganan tiket, pengecekan jadwal, informasi fasilitas, loyalty, serta informasi layanan feeder berupa ride-hailing, bus, taksi, dan shuttle.[^2] MRT Jakarta juga menjelaskan fitur tiket QR, jadwal, peta stasiun, Marti Point, promo feeder, dan layanan gaya hidup.[^3]

Konsekuensinya, proposal sebaiknya **tidak mengklaim** bahwa integrasi informasi feeder, tiket, promo, atau pembayaran saja merupakan novelty. Batas pembeda harus tegas:

| Kapabilitas | Sudah ada/beririsan dengan MyMRTJ | Nilai baru MRT Link |
|---|---:|---|
| Jadwal dan tiket MRT | Ya | Dipakai sebagai komponen journey |
| Informasi/promo feeder | Ya | Feeder dipilih dalam rencana door-to-door |
| Loyalty dan journey history | Beririsan | Bukan novelty utama |
| Perbandingan kendaraan pribadi vs MRT | Belum dinyatakan pada sumber resmi yang ditinjau | **MRT Conversion** |
| Pemantauan risiko koneksi lintas moda | Belum dinyatakan pada sumber resmi yang ditinjau | **Connection Assist** |
| Replanning ketika feeder terlambat | Belum dinyatakan pada sumber resmi yang ditinjau | **Connection Assist** |

Catatan koreksi naskah awal: listing Google Play yang diperiksa mencantumkan pembaruan **15 Agustus 2026**, bukan 24 Agustus 2026.[^2] Lebih aman menulis “berdasarkan listing resmi MyMRTJ yang diakses September 2026” agar proposal tidak bergantung pada tanggal pembaruan aplikasi.

## 4. Value proposition

### Untuk calon pengguna MRT

“Saya dapat membandingkan perjalanan secara utuh, memilih MRT dengan percaya diri, dan tidak perlu menyusun ulang rute sendiri ketika koneksi berubah.”

### Untuk MRT Jakarta

“MRT Link menambahkan conversion funnel sebelum pembelian tiket dan reliability layer selama perjalanan, sehingga dapat diuji kontribusinya terhadap pengguna baru, trip completion, dan repeat usage.”

### Untuk mitra feeder

“Mitra memperoleh permintaan perjalanan yang terkait langsung dengan keberangkatan/kedatangan MRT, dengan standar data dan operasional yang lebih jelas.”

## 5. Alur pengguna yang dipakai dalam prototype

```text
INPUT DOOR-TO-DOOR
Rumah → Kantor
        ↓
MRT CONVERSION
Motor pribadi vs Feeder + MRT
        ↓
INTEGRATED JOURNEY
Feeder → Transfer → MRT → Last mile
        ↓
CONNECTION ASSIST
Deteksi risiko → Alternatif → ETA baru
        ↓
JOURNEY RECORD
Perjalanan selesai → Insight → Repeat usage
```

Setiap layar punya satu tugas:

1. **Home:** mengubah mental model dari station-to-station menjadi door-to-door.
2. **Compare:** membangun alasan untuk beralih dari kendaraan pribadi.
3. **Journey detail:** membuat perjalanan lintas moda terasa sederhana dan dapat dipesan.
4. **Live journey:** membuktikan novelty Connection Assist melalui skenario feeder terlambat.
5. **Journey Record:** memperlihatkan hasil dan membuka peluang retensi serta evaluasi layanan.

## 6. Business impact chain

```text
Eligible private-vehicle journeys
        ×
MRT recommendation acceptance rate
        ×
Booking completion rate
        ×
Completed MRT legs
        =
Potential incremental MRT trips
        ×
Average realized MRT fare
        =
Potential incremental farebox revenue
```

Rumus ini lebih aman daripada langsung menjanjikan persentase pertumbuhan revenue. Proposal dapat menyajikan tiga skenario—conservative, base, optimistic—setelah jumlah eligible journeys dan conversion rate diuji melalui pilot.

## 7. KPI yang disarankan

### North-star metric

**Jumlah completed MRT legs dari pengguna yang sebelumnya berniat memakai kendaraan pribadi.**

Metric ini langsung menghubungkan MRT Conversion dengan farebox dan menghindari vanity metric seperti jumlah unduhan.

### Leading indicators

| Tahap | KPI | Makna |
|---|---|---|
| Discovery | Comparison start rate | Apakah pengguna memahami entry point door-to-door? |
| Conversion | MRT recommendation acceptance rate | Apakah perbandingan berhasil mengubah pilihan? |
| Booking | Integrated journey completion rate | Apakah rencana cukup jelas untuk dipesan? |
| During trip | Connection Assist acceptance rate | Apakah rekomendasi replanning dipercaya? |
| Reliability | Successful connection rate | Berapa banyak koneksi yang tetap berhasil? |
| Outcome | Completed MRT legs | Trip MRT yang benar-benar terjadi |
| Retention | Repeat MRT journey within 30 days | Apakah pengguna baru membentuk kebiasaan? |
| Business | Incremental realized farebox | Pendapatan dari trip terverifikasi, bukan sekadar niat |

### Guardrail metrics

- keluhan atau refund karena mismatch jadwal/harga;
- missed connection setelah rekomendasi diterima;
- cancellation rate mitra feeder;
- waktu tunggu tambahan;
- opt-out dan keluhan terkait data lokasi;
- bias rekomendasi: MRT tidak boleh direkomendasikan ketika journey memang tidak layak.

## 8. Desain pilot yang realistis

### Fase 0 — Validasi problem (2–3 minggu)

- wawancara pengguna kendaraan pribadi yang origin/destination-nya berada dalam catchment MRT;
- uji prototype kepada 8–12 responden;
- ukur apakah pengguna memahami perbandingan dan percaya kepada Connection Assist;
- petakan alasan penolakan: waktu, biaya, transfer, keamanan, atau ketidakpastian.

### Fase 1 — Concierge MVP (4–6 minggu)

- pilih satu koridor dengan feeder dan volume komuter yang memadai;
- gunakan jadwal MRT resmi dan satu tipe mitra feeder;
- replanning dapat dibantu operator di belakang layar sebelum seluruh sistem otomatis;
- batasi pada jam komuter dan skenario first-mile terlebih dahulu.

### Fase 2 — Limited integration (8–12 minggu)

- integrasi ETA/status feeder dan jadwal MRT;
- aktifkan notifikasi risiko koneksi dan alternatif;
- ukur completed MRT legs, successful connection rate, dan repeat usage;
- bandingkan dengan kelompok pengguna yang hanya menerima informasi rute biasa.

Pemilihan koridor Cinere → Lebak Bulus → Dukuh Atas pada prototype adalah **skenario ilustratif**, bukan rekomendasi lokasi final. Lokasi pilot harus dipilih dari data catchment, asal feeder, pola tap-in/tap-out, dan kesiapan partner.

## 9. Kebutuhan data dan sistem

```text
Input pengguna
  ├─ origin, destination, departure preference
  └─ consent lokasi selama active journey
            ↓
Journey Orchestrator
  ├─ MRT schedule/service status
  ├─ feeder availability, pickup ETA, trip status
  ├─ routing, travel time, fare estimate
  └─ connection-risk and replanning rules
            ↓
Output
  ├─ comparison
  ├─ integrated itinerary
  ├─ alert + alternative
  └─ journey record
```

MVP tidak perlu mengklaim kecerdasan buatan kompleks. Aturan sederhana sudah cukup, misalnya:

> Bila `estimated station arrival + minimum transfer buffer > scheduled MRT departure`, tandai koneksi berisiko dan tawarkan jadwal layak berikutnya.

Proposal akan lebih kredibel bila menjelaskan bahwa akurasi ETA, data status mitra, aturan buffer, dan model settlement adalah kebutuhan feasibility—bukan sesuatu yang diasumsikan sudah tersedia.

## 10. Privacy by design

MRT Jakarta telah menyatakan komitmen menjaga privasi data dari MyMRTJ dan account-based ticketing.[^4] Untuk konsisten dengan prinsip tersebut:

- lokasi presisi hanya aktif selama journey dan dengan consent yang jelas;
- minimalkan penyimpanan raw location history;
- pisahkan data identitas dari data journey untuk analitik;
- gunakan data agregat untuk evaluasi koridor;
- sediakan kontrol hapus riwayat dan opt-out personalisasi;
- jelaskan tujuan penggunaan data sebelum permission diminta.

## 11. Risiko utama dan mitigasi

| Risiko | Mengapa penting | Mitigasi awal |
|---|---|---|
| Terlihat menduplikasi MyMRTJ | Dapat menggugurkan novelty | Jadikan MRT Link modul di MyMRTJ; fokuskan dua novelty |
| ETA feeder tidak akurat | Rekomendasi koneksi dapat menyesatkan | Data-quality SLA, confidence band, safe transfer buffer |
| Booking/payment terlalu kompleks | Integrasi komersial membutuhkan waktu | Mulai dari deep link/reservation, lalu unified payment |
| Perbandingan dianggap bias | Kepercayaan pengguna turun | Tampilkan asumsi, sumber estimasi, dan kondisi ketika kendaraan pribadi lebih rasional |
| Klaim emisi lemah | Mudah dipertanyakan juri | Pakai metodologi dan emission factor resmi; labeli angka prototype sebagai simulasi |
| Farebox impact belum terbukti | Revenue hanya potensi | Ukur completed MRT legs dan realized fare selama pilot |
| Ketergantungan mitra | Risiko operasional dan data | Pilot dengan partner terbatas dan API/operational agreement yang jelas |

## 12. Susunan proposal/pitch deck 10 slide

1. **Opening:** “Perjalanan MRT tidak dimulai di stasiun.”
2. **Problem:** friction first/last mile dan ketidakpastian koneksi.
3. **Evidence:** kontribusi feeder 22–23% terhadap ridership.
4. **Existing ecosystem:** apa yang sudah dilakukan MyMRTJ dan gap yang tersisa.
5. **Solution:** MRT Link sebagai modul orchestration layer.
6. **Novelty 1:** MRT Conversion, tampilkan layar compare.
7. **Novelty 2:** Connection Assist, tampilkan skenario keterlambatan.
8. **Business model/impact:** conversion funnel → completed MRT legs → farebox.
9. **Pilot & feasibility:** koridor terbatas, KPI, data, partner, privacy.
10. **Closing:** dari kendaraan pribadi menuju perjalanan MRT yang tersambung.

## 13. Script demo 75 detik

> “Raka biasanya naik motor dari Cinere ke kantornya di Dukuh Atas. Ia tidak menolak MRT; yang terasa rumit adalah perjalanan menuju dan setelah stasiun. Di MRT Link, Raka cukup memasukkan Rumah ke Kantor. MRT Conversion membandingkan perjalanan motor dengan feeder plus MRT secara transparan. Raka memilih MRT Journey dan memperoleh satu itinerary lintas moda. Di jalan, feeder terlambat tiga menit. Connection Assist mendeteksi bahwa MRT 07:27 berisiko terlewat, menyarankan MRT 07:35, dan memperbarui ETA tanpa biaya tambahan. Journey tetap tersambung dan trip MRT benar-benar selesai. Inilah fungsi MRT Link: bukan menggandakan MyMRTJ, tetapi menambahkan conversion layer sebelum perjalanan dan reliability layer selama perjalanan—dua titik yang dapat diuji kontribusinya terhadap ridership dan farebox.”

## 14. Hal yang jangan diklaim sebelum tervalidasi

- persentase kenaikan ridership atau revenue tertentu;
- integrasi API real-time dengan seluruh feeder;
- unified booking/payment untuk semua partner;
- angka penghematan emisi tanpa metodologi;
- komisi mitra sebagai sumber revenue utama;
- bahwa pengguna kendaraan pribadi pasti berpindah hanya karena lebih murah;
- bahwa seluruh perjalanan multimoda dapat dijamin tanpa SLA partner.

## 15. Langkah desain berikutnya

1. Uji prototype kepada 5 pengguna untuk menemukan kebingungan terbesar.
2. Buat usability test script dan form scoring.
3. Revisi copy, urutan informasi, dan indikator kepercayaan.
4. Tambahkan versi presentation-ready berupa 5 screenshot layar utama.
5. Susun deck 10 slide dengan evidence, prototype, impact model, dan pilot plan.

---

[^1]: [MRT Jakarta — Tengah Tahun 2024, 18,4 Juta Orang Gunakan MRT Jakarta](https://www.jakartamrt.co.id/id/info-terkini/tengah-tahun-2024-184-juta-orang-gunakan-mrt-jakarta)
[^2]: [Google Play — MyMRTJ, listing resmi PT MRT Jakarta](https://play.google.com/store/apps/details?id=com.mrt.jakarta)
[^3]: [MRT Jakarta — Fitur Baru Aplikasi MyMRTJ Dukung Gaya Hidup Urban](https://jakartamrt.co.id/id/siaran-pers/fitur-baru-aplikasi-mymrtj-dukung-gaya-hidup-urban)
[^4]: [MRT Jakarta Sustainability Report 2024 — Perlindungan Privasi Pelanggan](https://www.jakartamrt.co.id/sites/default/files/2025-07/MRT%20Jakarta%20-%20SR%202024%20-%20250602.pdf)
