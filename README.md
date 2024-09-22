# Jarkom-Modul-1-IT13-2024

## Anggota Kelompok IT 13
| Nama Lengkap          | NRP        |
| --------------------- | ---------- |
| Muhammad Dzaky Ahnaf  | 5027231039 |
| Muhammad Nafi Firdaus | 5027231045 |

# Advance Sanity Check 
1. Langkah Pertama adalah memasukkan ncat pada terminal wsl, command sebagai berikut `ncat 10.15.42.60 44000`
2. Pertanyaan akan bermunculan pada kesempatan kali ini dimulai dengan pertanyaan Username, nama file yang dikirim lalu pesan petunjuk
![Screenshot (26)](https://github.com/user-attachments/assets/b617c2ac-1baf-4483-956a-72c1a9ec7f9b)
3. Untuk menemukan username kita hanya perlu melakukan atau mengetik `frame contains "username"` pada wireshark kita
4. Setelah kita follow maka kita dapat menemukan username
5. Setelah itu ada petunjuk dari pertanyaan mengenai file yaitu formatnya, maka kita bisa menggunakan `frame contains "."` atau `frame contains ".txt"` Jika kita sudah biasa menebak file extension
6. Setelah itu ketika kita mendapatkan nama file extension tersebut, di tempat yang sama terdapat petunjuk mengenai pesan rahasia yang berada pada ppt peraturan jarkom
7. Pesan tersebut yaitu `cGVud29yZA` yang mana dibutuhkan base64 decode untuk memecahkannya yaitu `penword`
8. Jika sudah menemukan penword, maka flag akan diberikan.

# FTP Login 
1. Langkah Pertama adalah memasukkan ncat pada terminal wsl, command sebagai berikut `ncat 10.15.42.60 49000`
2. Lalu ketika sudah masuk file, pada wireshark ketik `frame contains "200"` Karena kita mencari info login berhasil
![Screenshot (35)](https://github.com/user-attachments/assets/c40bc018-8913-4db5-a615-7161ff58265c)
3. Tampilan diatas akan menjawab kedua pertanyaan dari soal yang mana akan memberikan kita flag seperti dibawah ini 
![Screenshot (36)](https://github.com/user-attachments/assets/a9243e89-616e-4bff-a335-34589b1f6e5a)

# EZ 
1. Langkah Pertama adalah memasukkan ncat pada terminal wsl, command sebagai berikut `ncat 10.15.42.60 54000`
2. Lalu karena pada terminal ada petunjuk ini merupakan string dengan sebuah spasi, saya mencoba dengan ide `frame contains " "` untuk mencari string dengan spasi
3. Ketika sudah follow muncullah sepert ini
 ![Screenshot (37)](https://github.com/user-attachments/assets/25a4ede2-94e0-4573-8584-c3b99f8fa8bb)
4. Untuk port bisa langsung dilihat dari wireshark, bisa di double tap
5. Dan inilah hasil akhir beserta flag
![Screenshot (38)](https://github.com/user-attachments/assets/aeecbb8d-1abf-42b4-82a7-c9bd819ce97e)

# Pegawai Negeri Sebelah
1. Langkah Pertama adalah memasukkan ncat pada terminal wsl, command sebagai berikut `ncat 10.15.42.60 53000`
2. Lalu ketika membuka file wireshark saya mencoba memasukkan `frame contains "nNnM%coQuF"` sesuai soal
3. Maka satu file berisi seluruh data pegawai akan muncul dan kita bisa menggunakan fitur search didalamnya untuk mendeteksi password
4. Ini berlaku untuk soal soal berikutnya hingga kita mendapatkan flag seperti dibawah ini
   ![image](https://github.com/user-attachments/assets/42b067b7-c3dd-4b8b-8cf3-695e91fe7e4a)

# Illegal Breakthrough 
1. Langkah Pertama adalah memasukkan ncat pada terminal wsl, command sebagai berikut `ncat 10.15.42.60 46000`
2. Lalu coba follow filter destination paling atas dan itu sudah mencakup IP korban dan portnya
3. Setelah itu untuk mendapatkan endpoint yang terdapat login bisa menggunakan `frame contains "username"`
4. Lalu untuk mendapat tools bisa menggunakan `frame contains "-dev"` kita mendeteksi dari versinya dan format belakang sesuai clue soal
5. Terakhir kita bisa memasukkan `http && ip.src eq 172.21.88.207` cari yang found sehingga kita bisa mendapatkan kredensial yang digunakan untuk login sehingga kita bisa mendapatkan flag sebagai berikut
   ![image](https://github.com/user-attachments/assets/f58a9ced-3cbc-44a0-94d8-221050025d3e)

# Corporate Breach
1. Memasukkan ncat pada terminal wsl, command sebagai berikut ```nc 10.15.42.60 51000```
2. Mencari nama attacker dengan filter ```frame contains "name"```

![Screenshot (188)](https://github.com/user-attachments/assets/0b5bce88-4587-4d41-9259-543e26362a71)

Tertangkap satu nama yaitu Nakhimov.
3. Mencari email attacker dengan filter ```frame contains "email"```

![Screenshot (189)](https://github.com/user-attachments/assets/bd8e29d7-56ff-4e26-9b2e-70366b2ac220)

Tertangkap satu email anomali yaitu jarkomsupport@gmail.com beserta password nya yaitu j4rk0mg4c0rbg.

![Screenshot (201)](https://github.com/user-attachments/assets/c7e0558e-9cf8-4b40-8232-c905cfd9d7ab)

Bingo! flag ditemukan: JarkomIT{supp0rt_k0k_l3m4h_bg_P7NQjdgXKOLniE880qHL5pMvMG6ftOhBjl1G7kNX0iXCL4qTvFlBG6}

# Surprise
1. Memasukkan ncat pada terminal wsl, command sebagai berikut ```nc 10.15.42.60 48500```
2. Mencari service yang digunakan pada FTP server dengan meng-follow TCP stream lalu melihat versinya dipaling atas

![Screenshot (251)](https://github.com/user-attachments/assets/79918ed3-2c03-4946-b1be-09b605fb8625)

3. Terdapat satu file script cpp pada salah satu file FTP yaitu ```g0tcha.cpp```

![Screenshot (253)](https://github.com/user-attachments/assets/6ee09d46-48ab-40c6-b98b-55b7471d7790)

4. Isi dari ```g0tcha.cpp``` bisa dilihat dan coba jalaankan scriptnya.

![Screenshot (252)](https://github.com/user-attachments/assets/88b6c488-1cff-40b7-94bd-29ba1a67e41b)

![image](https://github.com/user-attachments/assets/738c4487-49fd-4e62-857d-fcf755a3169c)

Terdapat string teks ```g0tchu n0w l1ttl3 m0us3```

![Screenshot (256)](https://github.com/user-attachments/assets/da137914-b632-401c-97eb-4170b14e1c79)

Bingo! flag ditemukan: JarkomIT{l1ttl3_m0us3_1n_th3_h0us3_hkvm32AFY4wmmHcX5apqbP3idG0XMKTttaQWbYxuu5K4fb4OsoJvTCHU}

# Stegography
1. Memasukkan ncat pada terminal wsl, command sebagai berikut ```nc 10.15.42.60 58000```
2. Mencari jumlah file gambar dengan filtering ```frame contains "png"```. Terdapat 13 jumlah gambar PNG.

![Screenshot (257)](https://github.com/user-attachments/assets/a30a5fca-8ee0-4ae9-85d0-c69a326dd50e)

3. Menggunakan script untuk looping mengecek setiap gambar yang memiliki pesan.

![image](https://github.com/user-attachments/assets/52e789b2-ea42-449f-ba6e-f220a5871af7)

Gambar ATP, EH, KJK yang memiliki pesan terbalik

4. Gambar ATP, EH, KJK yang memiliki pesan terbalik yang jika disusun berupa kalimat ```pahlawan keamanan siber```.

![image](https://github.com/user-attachments/assets/2164221b-9cd9-4a4e-9760-3f3159d8ba4c)

Bingo! flag ditemukan: JarkomIT{S3LaM4t_p4rA_PahL4WaN_YozIVHLQ4fsDceQ6cPoLi8WV5P5ssm9EGvCbxWpACSiW6kTeqyRShhC5}

# inneRCE
1. Memasukkan ncat pada terminal wsl, command sebagai berikut ```nc 10.15.42.60 44000```
2. Pada clue terdapat kata websehll, coba lakukan filter ```frame contains "shell"```

   ![Screenshot (194)](https://github.com/user-attachments/assets/3bf43e85-7ad9-4b5b-8ad4-4af629e881f1)

# Gajah Terbang (Server Recon)
1. Memasukkan ncat pada terminal wsl, command sebagai berikut ```nc 10.15.42.60 61000```

![Screenshot (261)](https://github.com/user-attachments/assets/8480c441-60e3-486c-ac0c-d6dd576e894e)

2. Terdapat singkatan PSQL yang merupakan kepanjangan dari database ```PostgreSQL```
3. Server tersebut berjalan di port ```6969```
4. Terlihat juga bahwa mereka memakai OS ```Debian```
5. Terlihat username DBMS yaitu ```s1gm4``` dan passwordnya: ```sigmaskibidigyatrizzzz```
6. Untuk banyak users saya mencoba dari 3 karena terdapat perintah ```WHERE id=3;``` dan ditemukan ada 4 users ternyata
7. Email nya ada banyak dan saya bruteforce dan ditemukan email nya yaitu ```jojohermawan@gmail.com``` dan passwordnya yaitu ```admin1234```

![Screenshot (262)](https://github.com/user-attachments/assets/8530f426-ed69-4d50-8f77-e29cc5d3aec3)

Bingo! flag ditemukan: JarkomIT{Gy4tT_M5g_4U_UMJS6rsnT3SXBgukauo2xvPSC5k1JzgfUiqP9oGcMF4wQdaM3mw6PBiD1}
