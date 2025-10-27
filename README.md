# Social Network Influence Mapper

## Deskripsi Tugas
Tugas besar ini bertujuan untuk membandingkan efisiensi dua algoritma dalam menganalisis jaringan sosial. Mahasiswa diharapkan memahami pentingnya algoritma yang efisien melalui praktik langsung dan visualisasi hasil analisis.

## Judul
**Analisis Kompleksitas Algoritma Graph Analysis: Perbandingan PageRank Iteratif dan Community Detection Recursive untuk Pemetaan Pengaruh dalam Jejaring Sosial**

## Anggota Kelompok
- Krisnia Syawahdani
- IGN Brindawan Tri Guna Yoga
- Andre Masalle

## Studi Kasus
Analisis pengaruh pengguna dan komunitas dalam jejaring sosial, seperti Facebook, Twitter, atau email, untuk memahami pola interaksi dan hubungan pengaruh di antara anggota jaringan.

## Dataset
- **Sumber:** [Stanford SNAP Twitter Networks](https://snap.stanford.edu/data/twitter_combined.txt.gz)  
- **Deskripsi:** Dataset ini merupakan gabungan 973 ego-networks Twitter, membentuk graph directed dengan node mewakili akun pengguna dan edge mewakili hubungan "follow".  
- **Ukuran:** 81.306 nodes, 1.768.149 edges.  
- **Catatan:** Dataset hanya berisi Node ID dan edges; tidak ada nama atau fitur pribadi pengguna. Dataset cocok untuk analisis struktur graph, PageRank, dan deteksi komunitas.

## Algoritma yang Digunakan
- **Iteratif:** PageRank Algorithm  
  Mengukur tingkat pengaruh tiap node dalam jaringan melalui pendekatan iteratif.

- **Rekursif:** Louvain Community Detection  
  Mengidentifikasi komunitas dalam jaringan menggunakan metode rekursif berbasis modularitas.

## Aplikasi Sederhana
Visualisasi interaktif struktur jaringan yang menampilkan node, edge, pengaruh tiap pengguna, dan komunitas yang terbentuk.  
*(Contoh: visualisasi network graph dengan node berwarna sesuai komunitas, ukuran node berdasarkan PageRank)*

## Analisis Efisiensi
- Mengukur running time kedua algoritma dengan berbagai ukuran masukan (misal: 1, 10, 20, ..., 10000 node).  
- Membandingkan kelas kompleksitas waktu (asymptotic complexity) dari algoritma iteratif dan rekursif.  
- Menyajikan grafik perbandingan efisiensi.

## Grafik Perbandingan Running Time
*(Grafik akan ditambahkan sini setelah pengujian)*
  