# Praktikum 11

Nama : Muhammad Reza Maulana

NIM : 312210303

Kelas : TI.22.A3


# Pertemuan 15


## Soal

![IMG_20230118_124606](https://user-images.githubusercontent.com/115516607/213094195-e2128d8a-475b-4490-b8c8-79baafa9e83c.jpg)

## Jawaban

## Challenge 1

Web scraping pada website https://glints.com/id/lowongan-kerja

![IMG-20230117-WA0027](https://user-images.githubusercontent.com/115516607/212916294-63e43d14-62c2-4bae-ae35-f8103c88a9a7.jpg)

### Penjelasan
!pip install pandas digunakan untuk menginstall package pandas di python. Package pandas digunakan untuk memanipulasi data dalam bentuk tabel (dataframe) dan digunakan
untuk data analysis. Fungsi dari package pandas sangat luas, seperti melakukan operasi pada data, mengimport dan mengeksport data dari berbagai format, dan lainnya.
!pip install requests digunakan untuk menginstall package requests di python. Package requests digunakan untuk melakukan HTTP request dari python.

!pip install BeautifulSoup4 digunakan untuk menginstall package BeautifulSoup4 di python. Package BeautifulSoup4 digunakan untuk parsing dan mengelola data dari HTML atau XML.

import pandas as pd digunakan untuk mengimport library pandas dan menyebutnya sebagai pd. Library pandas digunakan untuk memanipulasi data dalam bentuk tabel (dataframe) dan digunakan untuk data analysis.

from bs4 import BeautifulSoup digunakan untuk mengimport class BeautifulSoup dari package BeautifulSoup4. Class BeautifulSoup digunakan untuk mengelola dan mengolah data dari HTML atau XML.



![image](https://user-images.githubusercontent.com/93815689/212857324-be077dbf-4f0f-49e5-80de-3f49be11d47b.png)

### Penjelasan
mengambil data lowongan kerja dari situs web Glints. Dengan menggunakan library Python 'requests', kodingan mengirim permintaan GET ke URL "https://glints.com/id/lowongan-kerja" yang merupakan halaman web yang berisi informasi lowongan kerja. Kemudian, dengan menggunakan library 'BeautifulSoup', kodingan menganalisis konten halaman web yang didapat dari permintaan GET tersebut dengan menggunakan parser HTML.

Selanjutnya, kodingan mencari semua elemen HTML dengan atribut 'div' dan 'id' yang sesuai, yaitu '__next'. Kemudian, dari elemen-elemen tersebut, kodingan mengekstrak informasi pekerjaan, lokasi, dan nama perusahaan dengan mencari elemen yang memiliki atribut 'class' yang sesuai. Informasi yang diambil kemudian disimpan dalam sebuah list yang sesuai.

Setelah itu, kodingan menggunakan library pandas untuk membuat dataframe dari list yang didapat dan menyimpannya dalam variabel 'df'. Kemudian kodingan mencetak dataframe tersebut, sehingga kita dapat melihat informasi lowongan kerja yang diambil dari situs web Glints.

### OUTPUT 

![image](https://user-images.githubusercontent.com/93815689/212865172-ae5aa214-a1f6-4380-b510-ced94bbbfe97.png)

## Challenge 2

Ambil contoh web marketplace Ebay lalu salin link ke variable URL 

```
URL = "https://www.ebay.com/sch/i.html?_from=R40&_trksid=p2380057.m570.l1313&_nkw=laptop&_sacat=0"
page = req.get(URL)
soup = bs(page.content, 'html.parser')
```

Soup akan menganalisis konten nya dengan html 

---

Gunakan soup untuk mencari item produknya 

    produk = soup.find_all('li', attrs={'class': 's-item'})

buat list nya dan tambahkan list nya 

```
nama_produk = []
harga_produk = []
for item in produk:
  nama = item.find('div', attrs={'class': 's-item__title'}).text
  harga = item.find('span', attrs={'class': 's-item__price'}).text
  nama_produk.append(nama)
  harga_produk.append(harga)
```
---

buat dataframe untuk list menggunakan panda

```
df = pd.DataFrame({'Barang': nama_produk, 'Harga': harga_produk})

print(df)
```

### Output

content://com.android.chrome.FileProvider/images/screenshot/16740219581761462090968.png![image](https://user-images.githubusercontent.com/115516607/213096952-681a4e9d-0639-4cde-a0a7-48545ccd14ea.png)











