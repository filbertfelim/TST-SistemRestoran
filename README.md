# YummyBite
Merupakan sistem manajemen restoran dapat digunakan untuk mengelola daftar menu yang disediakan oleh restoran. Pengelola restoran dapat menambahkan menu baru, mengubah informasi dari menu yang sudah ada, dan menghapus menu. Data menu yang tercatat pada sistem manajemen restoran mencakup nama makanan, kalori, harga, dan waktu pemrosesan makanan. Sistem dapat melakukan perhitungan kalori dari setiap restoran berdasarkan data kalori makanan yang dimiliki oleh masing-masing restoran, dan mengkategorikan hasil perhitungan kalori tersebut, yang merupakan core domain dari sistem ini. Perhitungan kalori dan kategorisasi kalori tersebut digunakan oleh [domain sistem pemesanan delivery](https://github.com/filbertfelim/TST-CodeIgniter) untuk menyediakan filter restoran berdasarkan tingkat kalori. Selain itu, sistem manajemen restoran dapat menampilkan daftar pesanan beserta rinciannya untuk masing-masing restoran dengan menggunakan data pemesanan dari [domain sistem pemesanan delivery](https://github.com/filbertfelim/TST-CodeIgniter). Pengelola restoran juga dapat melihat total pendapatan yang diperoleh restoran berdasarkan data pemesanan tersebut.

## Fitur
1. Sistem dapat melakukan autentikasi pengguna  
2. Sistem dapat menampilkan daftar menu yang tersedia pada restoran
3. Sistem menyediakan pengelolaan daftar menu restoran
4. Sistem dapat menampilkan riwayat pemesanan yang dimiliki restoran
5. Sistem dapat menghitung dan menampilkan total pendapatan restoran

## Teknologi
**Bahasa pemograman** : PHP
***Framework*** : CodeIgniter 4 
***Database*** : MySQL

## API Endpoint
#### 1. /restoranAPI
Mengembalikan data seluruh restoran

HTTP *method* : **GET**

*Request body example*
```jsonc
{
   “username”: string, 
   “password” : string
}
```
*Response body example*
```jsonc
{
   “id”: int,
   “namaRestoran”: string, 
   “lokasiX”: int,
   “lokasiY”: int,
   “image” : string,
   “totalKalori”: int
   “totalHarga”: int
} [] | null
```

#### 2. /restoranbyid/(:restoranID)
Mengembalikan data restoran berdasarkan ID restoran yang diminta

HTTP *method* : **GET**

*Request body example*
```jsonc
{
   “username”: string, 
   “password” : string
}
```
*Response body example*
```jsonc
{
   “id”: int,
   “namaRestoran”: string, 
   “lokasiX”: int,
   “lokasiY”: int,
   “image”: string,
   “totalKalori”: int
} | null
```
#### 3. /makananAPI/(:restoranID)
Mengembalikan data makanan berdasarkan ID restoran yang diminta

HTTP *method* : **GET**

*Request body example*
```jsonc
{
   “username”: string, 
   “password” : string
}
```
*Response body example*
```jsonc
{
   “id”: int,
   “namaMakanan”: string, 
   “harga”: int,
   “kalori”: int,
   “waktuProses”: string,
   “restoranId”: int
} [] | null
```

## Antarmuka Pengguna
### Sign In Page
![](https://lh7-us.googleusercontent.com/T0DwPSV2K2gsQUGAW8IZVz47mOt_mSn2zszE-FoJujIGCEiULEmYKZ_IMF-diOOhNuY_vAS09DhJSggsX17XwyNPTHKkm8qCaZz4k82ndMJCZCNLhFd7Zdn9OJV3TsRkUg1nOC9eQ2iKRt2nHbUTAIo)
### Menu List Page
![](https://lh7-us.googleusercontent.com/vxSkk1kiB5Auz5lOe7_jUNcis1R_PGqwIvraEzqcACXmNlAA1IeMosCwa0nOqGBHITDuSBNXA7XhQeINujqlf6Sg5I8nKxpZEbadTZd5x83T2uDmrw-g4FARVzVa3UGM_tEcW6SYMdJS4-fgXT6s-Oo)
### Add New Menu Page
![](https://lh7-us.googleusercontent.com/k5ZHzCUR558ZBN1u6GyWyAepRz7Ofkic36VOBh4lUPb5qeteIkM5YGeScy1d72t5Kba9iPz5C0RKnOCmeFCEr4Tk6u5q5B1C6WC-FFBeJz9zg-0OtToAYetwhAaZknuI3MkqtAdp4PukkyWkgLoaKCU)
### Edit Menu Page
![](https://lh7-us.googleusercontent.com/dA0bDC90BetJPa6gjXsdc-HGqRIVJQzIK7OD7JO5cxeEqJdZiQLNlQ-RNXODQV16YH-4BtXwzmDJfXQc1Pj2J4iKebFwysTSCcrZy3GfeRgmReC4psNJLsgSmnmW1FJrIdYHeIFxEKkQxhcI6MOU1go)
### Delete Confirmation Modal
![](https://lh7-us.googleusercontent.com/Kix_6YFVdU7WyJOhtdomukBF5pOgMjoHQmj1YCeafaBShtIkDSMeb9gWLIEomWjTQuSBGslKgJ5Q7HpwEXywbQJm_D1Bg34nRydO4C9Z8-boXkLKCQmDJq0zX7iVkCcNHCG85lyBoUmAT6Opq1mX2do)
### Transaction History Page
![](https://lh7-us.googleusercontent.com/jz_-QQ4Hb_v_yWDrzJe7udw1O1r9PNQJsK_SDYO_sl-j693jMMA2ks1Qw0ZszCwuxezzLFIgxqJNIRl0qXHQ8xyiJd3XPu2QoAGsK3UvQTbm0Zao5pGPAD5mOrOQYp7vJiWQxJoXL3LR-cPsEFUEtvM)
### Order Details Modal
![](https://lh7-us.googleusercontent.com/HH8J6JelP9d-t0b7BMO8nJMUg0UQC2S_dvx0wlpy49MExErGcXuKGTJgRVNZiL98tAxTTfKuGTPs-xTJpZcwgV_NM1VoKIReVUkfUU3YgRQSs9DeR5yMtHenw0rsVRvRLPizvfc6Ns8aYCum6P2c8NY)	

## Database
Berikut skema ***database*** yang digunakan dalam sistem :
![](https://lh7-us.googleusercontent.com/wu7l2xndArTV65lMrxRV02LpdatOS0yr2T31CG7L7I9y2lli37oe6YZdx24kUMRZRZA1GjzIBjzqI4O8hgz9XZ_yXiW63324loj40Zg3Pj2ZxrXJhTib8ZkRqMYzsXeX5VHZ154CCd8plls6TQ2h8Nk)
