# P2_Probstat_F_5025201156
Praktikum Probabilitas dan Statistik 2022 Modul 2 (Distribusi Probabilitas)
```
Nama    : Nazhifah Elqolby
NRP     : 5025201156
Kelas   : Probstat F
```


### Soal 1 
> Seorang peneliti melakukan penelitian mengenai pengaruh aktivitas 𝐴 terhadap kadar saturasi oksigen pada manusia. Peneliti tersebut mengambil sampel sebanyak 9 responden. Pertama, sebelum melakukan aktivitas 𝐴, peneliti mencatat kadar saturasi oksigen dari 9 responden tersebut. Kemudian, 9 responden tersebut diminta melakukan aktivitas 𝐴. Setelah 15 menit, peneliti tersebut mencatat kembali kadar saturasi oksigen dari 9 responden tersebut. Berikut data dari 9 responden mengenai kadar saturasi oksigen sebelum dan sesudah melakukan aktivitas 𝐴

> ![soal 1](https://user-images.githubusercontent.com/70510279/170801862-fb8feada-e470-4bdd-90c8-2b1b050563ca.jpg)

> Berdasarkan data pada tabel diatas, diketahui kadar saturasi oksigen dari responden ke-3 ketika belum melakukan aktivitas 𝐴 sebanyak 67, dan setelah melakukan aktivitas 𝐴 sebanyak 70.

#### 1a
Carilah Standar Deviasi dari data selisih pasangan pengamatan tabel diatas

</br>

Langkah pertama penyelesaian adalah memasukkan semua data yang ada pada tabel pada sebuah variabel sebagai berikut
```
before <- c(78, 75, 67, 77, 70, 72, 28, 74, 77)
```
```
after <- c(100, 95, 70, 90, 90, 90, 89, 90, 100)
```
Setelah dimasukkan semua datanya, maka dilakukan cek data menggunakan `data.frame` yaitu
```
my_data <- data.frame(
    group = rep(c("before", "after"), each = 9),
    saturation = c(before, after)
)
```
Setelah itu dilihat hasil framenya sebagai berikut
```
print(my_data)
```
 <img width="435" alt="image" src="https://user-images.githubusercontent.com/86004023/170858094-792f1a04-8114-4add-80cf-c51cdc4fcd86.png">

    Selanjutnya mencari standar deviasinya. Standar deviasi sebelum dan sesudah aktivitas adalah
    
      ```
          # Standar Devisiasi before activity
          SD_before <- sd(before)
          SD_before
          
           # Standar Devisiasi after activity
           SD_after <-sd(after)
           SD_after
       ```        
  Maka hasilnya : 

  <img width="347" alt="image" src="https://user-images.githubusercontent.com/86004023/170858149-b2e4b403-f4a1-4515-97bd-e990edcbd699.png">

#### 1b
carilah nilai t (p-value)

</br>

Untuk mencari nilai t terutama p-value maka bisa menggunakan fungsi `t.test` yaitu sebagai berikut
```
t.test(before, after, alternative = "greater", var.equal = FALSE)
```
Maka hasilnya adalah: 
</br> <img width="616" alt="image" src="https://user-images.githubusercontent.com/86004023/170858480-4e5c7d24-b5be-4ad1-8c0f-554450bbb4ca.png">

#### 1c
tentukanlah apakah terdapat pengaruh yang signifikan secara statistika dalam hal kadar saturasi oksigen, sebelum dan sesudah melakukan aktivitas 𝐴 jika diketahui tingkat signifikansi 𝛼 = 5% serta H0 : “tidak ada pengaruh yang signifikan secara statistika dalam hal kadar saturasi oksigen , sebelum dan sesudah melakukan aktivitas 𝐴”

</br>

Langkah pertama yaitu melihat hasil komparasi dua variabel berikut
```
var.test(before, after)
```
 </br> <img width="593" alt="image" src="https://user-images.githubusercontent.com/86004023/170858996-31f369f7-66ad-4279-9b12-2562a1f0e027.png">

</br>

Selanjutnya, untuk melihat pengaruh jika tingkat signifikasi 5% dan tidak ada pengaruh yang signifikan secara statistika, maka adalah sebagai berikut
```
t.test(before, after, var.equal = TRUE)
```
</br> <img width="692" alt="image" src="https://user-images.githubusercontent.com/86004023/170859040-a1c6aaaa-0fe0-4834-8778-eedcf4530034.png">

</br>

Bisa dilihat bahwa mean dan convidence sama dengan 1b, yang berbeda adalah p-value dan df. Sehingga tidak memiliki pengaruh yang signifikan secara statistika

</br>

## Soal 2
> Diketahui bahwa mobil dikemudikan rata-rata lebih dari 20.000 kilometer per tahun. Untuk menguji klaim ini, 100 pemilik mobil yang dipilih secara acak diminta untuk mencatat jarak yang mereka tempuh. Jika sampel acak menunjukkan rata-rata 23.500 kilometer dan standar deviasi 3900 kilometer. (Kerjakan menggunakan 2 library seperti referensi pada modul).

#### 2a
Apakah Anda setuju dengan klaim tersebut?

*Setuju* karena
<br>
<img width="223" alt="2222222" src="https://user-images.githubusercontent.com/94628041/170875583-43af693a-d428-42fd-881b-79ef77453332.png">



#### 2b
Jelaskan maksud dari output yang dihasilkan!

![2c](https://user-images.githubusercontent.com/70510279/170825033-001339b6-b1c3-42ab-b928-162ead8d4fbe.jpg)

Diketahui n = 100, Rata-Rata (X̄) = 23500, dan standar deviasi(σ) = 3900
Maka null hipotesis adalah 
```
H0 : μ = 20000
```
Alternatif hipotesisnya yaitu
```
H1 : μ > 20000
```

#### 2c
Buatlah kesimpulan berdasarkan P-Value yang dihasilkan!


Untuk mencari nilai z nya yaitu 
</br>
![image-removebg-preview](https://user-images.githubusercontent.com/70510279/170823253-92e9ca27-09f7-4d40-a51c-9fd4392bb742.png)

Lalu mencari nilai p-value nya sebagai berikut
![image-removebg-preview (1)](https://user-images.githubusercontent.com/70510279/170823313-044b2776-38ff-49d4-bca6-455ef75db0a5.png)
![image-removebg-preview (2)](https://user-images.githubusercontent.com/70510279/170823338-3d86d1f2-14dc-458c-af6a-eb06f0fd8333.png)

Sehingga kesimpulan yang didapat adalah bahwa mobil dikemudikan rata-rata lebih dari 20.000 kilometer per tahun
