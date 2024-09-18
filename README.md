# Jarkom-Modul-1-IT13-2024

## Nama : Muhammad Dzaky Ahnaf (5027231039)
## Nama : Muhammad Nafi Firdaus (5027231045)

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
