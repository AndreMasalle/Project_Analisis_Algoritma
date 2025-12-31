# Horizontal Image Flip

## Deskripsi Tugas
Tugas besar ini bertujuan untuk membandingkan efisiensi dua algoritma (Iteratif vs Rekursif) dalam Horizontal Image Flipping. Mahasiswa diharapkan memahami pentingnya algoritma yang efisien melalui praktik langsung dan visualisasi hasil analisis.

## Judul
**Analisis Performa Pendekatan Rekursif vs Iteratif pada Horizontal Image Flipping**

## Anggota Kelompok
<table>
  <tr>
    <th> NIM </th>
    <th> Nama </th>
    <th> Bagian yang dikerjakan </th>    
  </tr>
  <tr>
    <td> 103012580012 </td>
    <td> Krisnia Syahwadani </td>
    <td> Iteratif </td>
  </tr>
  <tr>
    <td> 103012580016 </td>
    <td> IGN Brindawan Tri Guna Yoga </td>
    <td> Rekursif </td>
  </tr>
  <tr>
    <td> 103012580019 </td>
    <td> Andre Fransiscus Masalle </td>
    <td> Ide dan Analisis </td>
  </tr>
</table>

## Algoritma yang Digunakan
- **Iteratif:** Iterasi per piksel (nested loop pada setiap baris dan channel)

- **Rekursif:** Rekursi dengan pendekatan divide-and-conquer sederhana

## Eksperimen
Eksperimen dilakukan menggunakan beberapa citra dengan ukuran berbeda.
Runtime diukur dan divisualisasikan dalam grafik runtime vs ukuran data (jumlah piksel).


## Analisis Komplesitas Iteratif


Pada inner loop iteratif dapat dihitung komplesitasnya sebagai berikut:

$$
T_{inner}(H,W) = \sum_{i=1}^{H} \sum_{j=1}^{W/2} 1 = \frac{H \cdot W}{2}
$$

Dikarenakan horizontal maka yang swap adalah kiri dan kanan sehingga yang dibagi 2 adalah width nya, kemudian hal yang sama dilakukan pada 3 channel RGB, sehingga didapatkan kompleksitas seperti berikut:


$$
T_{iteratif}(H,W) = \sum_{i=1}^{3} \sum_{j=1}^{H} \sum_{k=1}^{W/2} 1 = \frac{3 \cdot H \cdot W}{2} = \frac{3}{2}n
$$

Maka:

$$
 T_{iteratif}(H,W) \in O(HW)
$$

atau dengan $n=HW$

$$
 T_{iteratif}(n) \in O(n)
$$

## Analisis Komplesitas Rekursif

Pertama-tama untuk rekursif terdalam yang menukar baris Didapati $T(n)$ sebagai berikut:

$$
T_{baris}(W) =
\begin{cases}
0 & \text{jika } kiri ≥ kanan \\
1 + T(W-2) & \text{lainnya}
\end{cases}
$$

- $W = \text{jumlah kolom}$

Maka untuk solusi rekursif terdalam adalah:

$$ T_{baris}(W) = \frac{W}{2} $$

Kemudian untuk rekursif tengah untuk flip channel didapatkan $T(n)$:

$$
T_{channel}(H,W) =
\begin{cases}
0 &  H=0 \\
T_{baris}(W) + T(H-1, W) & H>0
\end{cases}
$$

- $H = \text{jumlah baris}$
- $W = \text{jumlah kolom}$

Maka untuk solusi rekursif bagian tengah ini adalah:

$$
T_{channel}(H,W) = \frac{H \cdot W}{2}
$$

Lalu yang terakhir, rekursif pada 3 channel didapati T(n) sebagai berikut:

$$
T_{rgb}(H,W) =
\begin{cases}
0 &  c=0 \\
T_{channel}(H,W) + T_{rgb}(H, W, c-1) & c>0
\end{cases}
$$

- $H = \text{jumlah baris}$
- $W = \text{jumlah kolom}$
- $c = \text{3 channel (R,G,B)}$


Maka untuk solusi rekursif bagian akhir ini adalah:

$$
T_{rekursif}(H,W) = \frac{3 \cdot H \cdot W}{2} = \frac{3}{2}HW
$$

Sehingga

$$
T_{rekursif}(H,W) \in O(HW)
$$

Jika $n = HW$, maka:

$$
T_{rekursif}(n) \in O(n)
$$



## Grafik Perbandingan Running Time

<img width="841" height="393" alt="image" src="https://github.com/user-attachments/assets/41b831a8-e835-408f-95ff-b624b934f812" />

## Kesimpulan
Meskipun algoritma iteratif dan rekursif memiliki kompleksitas waktu yang sama
(O(H·W)), perbedaan runtime nyata muncul akibat overhead Python ataupun manajemen memori ataupun hal yang lainnya.


  
