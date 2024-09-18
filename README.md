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
