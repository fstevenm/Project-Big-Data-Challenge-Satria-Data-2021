# Project-Big-Data-Challenge-Satria-Data-2021


Kompetisi BDC diikuti oleh beberapa tim dalam tingkat nasional, yang mana masing-masing tim terdiri dari 3 orang.

#### Tim saya:

<p><a target="_blank" rel="noopener noreferrer"><img src="https://github.com/fstevenm/Project-Big-Data-Challenge-Satria-Data-2021/blob/main/assets/LogoUSD.png" width="128" style="max-width: 100%;"></a></p>

<table>
<thead>
</thead>
<tbody>
<tr>
<td>Ferdinandus Steven Millicent</td>
<td><a href="https://www.linkedin.com/in/fstevenm/" rel="nofollow"><img src="https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white" alt="LinkedIn" data-canonical-src="https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&amp;logo=linkedin&amp;logoColor=white" style="max-width: 100%;"></a></td>
</tr>

<tr>
<td>Ignatius Sarwo Edhi Wiyoto</td>
<td><a href="https://www.linkedin.com/in/ignatius-sarwo-edhi-wiyoto-168058197/" rel="nofollow"><img src="https://camo.githubusercontent.com/a80d00f23720d0bc9f55481cfcd77ab79e141606829cf16ec43f8cacc7741e46/68747470733a2f2f696d672e736869656c64732e696f2f62616467652f4c696e6b6564496e2d3030373742353f7374796c653d666f722d7468652d6261646765266c6f676f3d6c696e6b6564696e266c6f676f436f6c6f723d7768697465" alt="LinkedIn" data-canonical-src="https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&amp;logo=linkedin&amp;logoColor=white" style="max-width: 100%;"></a></td>

<tr>
<td>Albert Ricky Setiawan</td>
<td><a href="https://www.linkedin.com/in/albert-setiawan-440a92138/" rel="nofollow"><img src="https://camo.githubusercontent.com/a80d00f23720d0bc9f55481cfcd77ab79e141606829cf16ec43f8cacc7741e46/68747470733a2f2f696d672e736869656c64732e696f2f62616467652f4c696e6b6564496e2d3030373742353f7374796c653d666f722d7468652d6261646765266c6f676f3d6c696e6b6564696e266c6f676f436f6c6f723d7768697465" alt="LinkedIn" data-canonical-src="https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&amp;logo=linkedin&amp;logoColor=white" style="max-width: 100%;"></a></td>

</tr>
</tbody>
</table>


Tim kami berhasil menjadi finalist dalam lomba big data challenge ini. Selain itu, tim kami juga memperoleh peringkat 3 F1-Score terbaik untuk model jenis kelamin. Metodologi selengkapnya dapat diamati pada <a href="https://github.com/fstevenm/Project-Big-Data-Challenge-Satria-Data-2021/blob/main/Laporan Akhir.pdf"><code>Metodologi</code></a>


<img src="https://github.com/fstevenm/Project-Big-Data-Challenge-Satria-Data-2021/blob/main/assets/klasemen.png" width="900" style="max-width: 100%;">


## Problem


<img src="https://github.com/fstevenm/Project-Big-Data-Challenge-Satria-Data-2021/blob/main/assets/previewIMG.png" width="900" style="max-width: 100%;">
Problem kompetisi ini adalah memprediksi Jenis Kelamin dan Usia seseorang dari gambar. Pada lomba ini, tidak diperkenankan menggunakan transfer learning, penggunaan arsitektur model pada <a href="https://keras.io/api/applications/" rel="nofollow"><code>Keras Model</code></a> diperbolehkan tetapi harus di set dengan ketentuan <code>weights=None</code>.
 

## Preprocessing

Proses ini bertujuan untuk menyeragamkan data, dalam hal ini proses penyeragaman yang dilakukan adalah memotong gambar pada bagian wajah dan merotasi gambar sehingga semua pose wajah menjadi lurus. Pada data latih dan uji terdapat gambar yang memuat beberapa wajah, kami melakukan preprocessing dengan memilih wajah yang terbesar pada gambar. Data latih dikenakan preprocessing lalu disimpan ke dalam satu folder, hal ini dilakukan agar pada proses selanjutnya dapat dilakukan augmentasi gambar dengan lebih mudah dan menghindari resiko gagal crop. Sementara pada data uji proses crop hanya dilakukan ketika data ingin diprediksi, hal ini akan lebih efisien terutama jika model akan diaplikasikan nanti. Library yang kami gunakan dalam proses ini adalah <a href="https://github.com/ageitgey/face_recognition" <code>face_recognition</code></a>. Tahap:

1. Crop dan rotasi

<img src="https://github.com/fstevenm/Project-Big-Data-Challenge-Satria-Data-2021/blob/main/assets/rotate.png" width="900" style="max-width: 100%;">

2. Select

<img src="https://github.com/fstevenm/Project-Big-Data-Challenge-Satria-Data-2021/blob/main/assets/select.png" width="900" style="max-width: 100%;">


## Augmentasi

<img src="https://github.com/fstevenm/Project-Big-Data-Challenge-Satria-Data-2021/blob/main/assets/augmentasi.png" width="900" style="max-width: 100%;">

## Modelling

Artitektur model yang kami gunakan dapat dilihat pada gambar di bawah. Untuk detail mengapa kami memilih menggunakan arsitektur ini dan kelebihan dari arsitektur ini dapat pada <a href="https://github.com/isew25/BDC-Satria-Data-2021/blob/main/Report.pdf"><code>Metodologi</code></a>

1. Model Jenis Kelamin

<img src="https://github.com/fstevenm/Project-Big-Data-Challenge-Satria-Data-2021/blob/main/assets/arsitekturJK.png" width="900" style="max-width: 100%;">

2. Model Usia

<img src="https://github.com/fstevenm/Project-Big-Data-Challenge-Satria-Data-2021/blob/main/assets/arsitekturUsia.png" width="900" style="max-width: 100%;">

## Percobaan

Kami melakukan eksperimen dengan mengklaster gambar untuk memperoleh insight, tetapi eksperimen ini tidak dilanjutkan karena tidak ada insight yang dapat diambil.

<img src="https://github.com/fstevenm/Project-Big-Data-Challenge-Satria-Data-2021/blob/main/assets/eksperimen2.png" width="900" style="max-width: 100%;">

## Penerapan (Deploy)

Model yang kami buat dapat berhasil memprediksi usia dan jenis kelamin secara realtime dengan cukup baik.

<a target="_blank" rel="noopener noreferrer" href="https://github.com/fstevenm/Project-Big-Data-Challenge-Satria-Data-2021/blob/main/assets/image72.gif"><img src="https://github.com/fstevenm/Project-Big-Data-Challenge-Satria-Data-2021/blob/main/assets/image72.gif" width="600" style="max-width: 100%;"></a>


#### Don't forget to provide the source if you use this project!

---

My LinkedIn:

<a href="https://www.linkedin.com/in/fstevenm/" rel="nofollow">![LinkedIn](https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white)
