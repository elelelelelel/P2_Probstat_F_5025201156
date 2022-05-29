# P2_Probstat_F_5025201156
Praktikum Probabilitas dan Statistik 2022 Modul 2 (Distribusi Probabilitas)
```
Nama    : Nazhifah Elqolby
NRP     : 5025201156
Kelas   : Probstat F
```
Seorang peneliti melakukan penelitian mengenai pengaruh aktivitas 𝐴 terhadap kadar saturasi oksigen pada manusia. Peneliti tersebut mengambil sampel sebanyak 9 responden. Pertama, sebelum melakukan aktivitas 𝐴, peneliti mencatat kadar saturasi oksigen dari 9 responden tersebut. Kemudian, 9 responden tersebut diminta melakukan aktivitas 𝐴. Setelah 15 menit, peneliti tersebut mencatat kembali kadar saturasi oksigen dari 9 responden tersebut. Berikut data dari 9 responden mengenai kadar saturasi oksigen sebelum dan sesudah melakukan aktivitas 𝐴

![soal 1](https://user-images.githubusercontent.com/70510279/170801862-fb8feada-e470-4bdd-90c8-2b1b050563ca.jpg)

Berdasarkan data pada tabel diatas, diketahui kadar saturasi oksigen dari responden ke-3 ketika belum melakukan aktivitas 𝐴 sebanyak 67, dan setelah melakukan aktivitas 𝐴 sebanyak 70.

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
    group = rep(c("sebelum", "sesudah"), each = 9),
    saturation = c(before, after)
)
```
Setelah itu dilihat hasil framenya sebagai berikut
```
print(my_data)
```
![1a-1](https://user-images.githubusercontent.com/70510279/170801700-5a72cc8a-a5e8-4331-9466-534b5adba1b0.jpg)

Selanjutnya mencari standar deviasinya. Standar deviasi sebelum aktivitas adalah
```
SD_before <- sd(before)
SD_before
```
Maka hasilnya : 
</br>
![1a-2](https://user-images.githubusercontent.com/70510279/170802086-33f51947-7316-4eb1-a173-8b27355b2c21.jpg)
</br>

Standar deviasi setelah aktivitas adalah
```
SD_after <-sd(after)
SD_after
```
Maka hasilnya : 
</br>
![1a-3](https://user-images.githubusercontent.com/70510279/170802089-d7e550cd-e308-41a0-9881-dee36fcec0f8.jpg)

#### 1b
carilah nilai t (p-value)

</br>

Untuk mencari nilai t terutama p-value maka bisa menggunakan fungsi `t.test` yaitu sebagai berikut
```
t.test(before, after, alternative = "greater", var.equal = FALSE)
```
Maka hasilnya adalah: 
</br>

![1b](https://user-images.githubusercontent.com/70510279/170802497-1c8e11ec-b849-46df-970c-ae7a53990355.jpg)

#### 1c
tentukanlah apakah terdapat pengaruh yang signifikan secara statistika dalam hal kadar saturasi oksigen, sebelum dan sesudah melakukan aktivitas 𝐴 jika diketahui tingkat signifikansi 𝛼 = 5% serta H0 : “tidak ada pengaruh yang signifikan secara statistika dalam hal kadar saturasi oksigen , sebelum dan sesudah melakukan aktivitas 𝐴”

</br>

Langkah pertama yaitu melihat hasil komparasi dua variabel berikut
```
var.test(before, after)
```
![1c-1](https://user-images.githubusercontent.com/70510279/170803286-8d17ff49-ab43-4c8d-b68f-8252e50de12c.jpg)

</br>

Selanjutnya, untuk melihat pengaruh jika tingkat signifikasi 5% dan tidak ada pengaruh yang signifikan secara statistika, maka adalah sebagai berikut
```
t.test(before, after, var.equal = TRUE)
```
![1c-2](https://user-images.githubusercontent.com/70510279/170803288-c8b36ba6-954b-49b3-83e1-51e6236efe74.jpg)

</br>

Bisa dilihat bahwa mean dan convidence sama dengan 1b, yang berbeda adalah p-value dan df. Sehingga tidak memiliki pengaruh yang signifikan secara statistika
