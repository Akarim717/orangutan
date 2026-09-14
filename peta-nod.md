# Jejak Orang Utan — Peta Nod

Struktur: berasaskan keadaan (state-based). Pemboleh ubah tersembunyi: **kepercayaan**, **bukti**, **bahaya**. 27 nod (22 nod cerita + 5 pengakhiran), termasuk 3 nod prolog latar belakang di awal.

| ID | Ringkasan | Perubahan keadaan | Pilihan | Destinasi |
|----|-----------|--------------------|---------|-----------|
| p1 | PROLOG — siapa Samad, di mana Kampung Sungai Rasa, kedudukan berhampiran Hutan Simpan Ulu Segama | — | (paksa) | p2 |
| p2 | PROLOG — hubungan Samad dengan Pak Milan (arwah datuk) dan Pak Rashid, latar ekonomi kampung bergantung pada Perkasa Timber | — | (paksa) | p3 |
| p3 | PROLOG — rentak harian/malam kampung, suasana sebelum bunyi lori ganjil kedengaran | — | (paksa) | n1 |
| n1 | Malam ganjil, lori balak lalu lewat malam | — | Ikut jejak lori / Jumpa Pak Rashid dulu | n2 / n3 |
| n2 | Mengekori lori ke kem, gelap dan tegang | bahaya +1 | (paksa) | n4 |
| n3 | Pak Rashid mula syak Encik Razif | kepercayaan +1 | Siasat bersama / Sendiri dulu | n5 / n6 |
| n4 | Sampai kem, pagar tinggi, raungan haiwan | — | Menyelinap dekat / Berundur, catat | n7 / n5 |
| n5 | BOTTLENECK — kumpul maklumat, rancang | bukti +1 | Cari Farid / Balik, fikir esok | n8 / n9 |
| n6 | Sendirian, Encik Damsuki beri amaran | bahaya +1, kepercayaan −1 | (paksa) | n9 |
| n7 | Nampak kandang anak orang utan, dengar "penghantaran esok", lari | bukti +1, bahaya +1 | (paksa) | n9 |
| n8 | Jumpa Farid, sepupu di kem | Percaya sepenuhnya: kepercayaan +1, bahaya +1. Kongsi separuh: tiada | Percaya sepenuhnya / Kongsi separuh | n10 / n10 |
| n9 | Putuskan langkah esok | — | Cari Tok Ketua (perlu kepercayaan ≥1) / Cari Pak Rashid, bincang bukti / Nekad sendiri | n11 / n12 / n13 |
| n10 | Farid janji bantu | — | (paksa) | n9 |
| n11 | Tok Ketua teragak-agak sebab kenal keluarga Razif | Minta hubungi terus: kepercayaan +1. Rasa lambat, sendiri: kepercayaan −1, bahaya +1 | Minta hubungi pegawai terus / Rasa lambat, pergi sendiri | n14 / n13 |
| n12 | Pak Rashid: perlu bukti visual kukuh | — | Bukti cukup, hantar sekarang (perlu bukti ≥2) / Kembali untuk video jelas | n15 / n16 |
| n13 | Nekad sendiri ke kem, risiko tinggi | — | Ambil gambar kandang / Cuba lepaskan orang utan sendirian | n17 / n18 |
| n14 | Hubungi PERHILITAN daerah, masa cemas | bahaya +1 | (paksa) | n19 |
| n15 | Bukti diserahkan awal, tindakan pantas | — | (paksa) | n19 |
| n16 | Kembali bersama Pak Rashid, rakam video jelas | bukti +2, bahaya +1 | (paksa) | n19 |
| n17 | Ambil gambar kandang, hampir ketahuan | bukti +1, bahaya +2 | (paksa) | n19 |
| n18 | Cuba lepaskan orang utan sendirian, ditangkap basah | — | (paksa) | n24 (ENDING E5, terus) |
| n19 | KLIMAKS — trak mula bergerak ke simpang jalan | — (auto-laluan ikut keadaan) | — | n20 / n21 / n22 / n23 / n24 |
| n20 | ENDING — Menang Penuh | — | — | — |
| n21 | ENDING — Menang Pahit | — | — | — |
| n22 | ENDING — Separuh Berjaya | — | — | — |
| n23 | ENDING — Dikhianati | — | — | — |
| n24 | ENDING — Gagal / Ditangkap | — | — | — |

## Logik laluan di n19 (klimaks)

Disemak mengikut turutan ini, guna keadaan yang terkumpul sepanjang cerita:

1. bahaya ≥ 4 → n24 (Gagal)
2. bukti ≥ 3 **dan** kepercayaan ≥ 2 **dan** bahaya ≤ 2 → n20 (Menang Penuh)
3. bukti ≥ 3 **dan** bahaya ≥ 3 → n21 (Menang Pahit)
4. bukti < 2 **dan** bahaya ≥ 3 → n23 (Dikhianati)
5. selebihnya → n22 (Separuh Berjaya), laluan lalai

## Pengesahan graf

Disahkan secara programatik: tiada pautan mati, semua 27 nod boleh dicapai dari permulaan (p1), kesemua 5 pengakhiran boleh dicapai (laluan sebenar disimulasikan bagi setiap satu), tiada gelung terperangkap (graf tidak mempunyai kitaran).

## Versi buku bergambar

Setiap satu daripada 27 nod kini ada dua medan tambahan dalam objek `story`:

- `img` — URL terus ke ilustrasi yang dijana melalui OpenArt (model gpt-image-2, gaya sinematik separa-realistik).
- `tag` — label pendek babak dalam Bahasa Melayu, dipaparkan di atas teks (nod pengakhiran guna label pengakhiran sedia ada sebagai ganti).

**Nota penting untuk penyelenggaraan:** gambar-gambar ini TIDAK dibenamkan sebagai data offline dalam fail HTML. Ia dimuatkan terus dari pelayan `cdn.openart.ai` setiap kali fail dibuka, jadi fail ini kini perlukan sambungan internet untuk memaparkan ilustrasi (teks dan mekanik cerita tetap berfungsi offline). Jika mahu benar-benar swasembada tanpa CDN, langkah seterusnya ialah muat turun ke-27 imej itu secara berasingan dan benamkan sebagai `data:` URI di dalam fail.
