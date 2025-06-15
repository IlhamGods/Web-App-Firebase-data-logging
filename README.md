# Firebase-data-logging-web-app-for-ESP32S3
Firebase data logging web app dalam bentuk gauges, grafik, dan tabel.

# Overview pembahasan
Sebenarnya projek ini untuk my TA, yaitu data-data yang terbaca oleh board ESP32-S3, akan ditampilkan berupa gauges, grafik, dan tabel pada web. Bagian ini akan membahas web firebasenya. Secara spesifik membahas web interface dengan gauges, grafik, dan tabel. Disini juga akan dibuat tombol untuk menghapus semua data dari database dan kustomisasi UI. Dan lagi, web ini akan diproteksi dengan autentukasi email dan semua data dibatasi hanya untuk pengguna yang menggunakan aturan basis data.

Penting juga untuk melakukan logging data ke firebase.  Tutorial untuk logging data ke firebase bisa dilihat pada:

# Penting diperhatikan
 1. Firebase yang meng-hosting-kan web ini melalui CDN global dengan menggunakan Firebase Hosting dan terdapat sertifikat SSL. Kamu bisa mengakses web ini darimana aja asal punya nama domain yang dibuat
 2. Saat pertama kali mengakses web, kamu perlu melakukan autentikasi menggunakan alamat email yang terdaftar. Referensi cara autentikasi dapat dilihat pada : https://randomnerdtutorials.com/esp32-esp8266-firebase-bme280-rtdb/#Set-Authentication-Methods
 3. Setelah melakukan autentikasi, kamu dapat mengakses halaman web yang menunjukkan pembacaan data sensor.
 4. Terdapat tombol untuk menampilkan atau menyembunyikan semua pembacaa yang tersimpan pada database. Tidak hanya itu saja, tetapi ada juga untuk tombol untuk menghapus data
 5. Semua data dibatasi dengan aturan database

# Software yang dibutuhkan 
1. Visual Studio Code : https://code.visualstudio.com/
2. Node.JS LTS version : https://randomnerdtutorials.com/esp32-firebase-web-app/#install-nodejs
3. Firebase tools pada VSC : https://randomnerdtutorials.com/esp32-firebase-web-app/#install-firebase-tools

# Tambahkan App ke Firebase projek
 1. Pergi ke Google Firebase : https://firebase.google.com/?hl=id
 2. Tambahkan app pada logo "+ Add app" yang terletak ada pojok kanan atas
    ![image](https://github.com/user-attachments/assets/840f9abd-0bf5-4c27-ae8b-649b5ad54810)
3. Pilih ikon web app
4. Tambahkan nama projek. Selanjutnya klik tombol centang pada opsi "Also set up firebase hosting for this app". Click register app
   ![image](https://github.com/user-attachments/assets/b03bbd9a-212f-45b7-966a-9fd4815a7ac1)
5. Salin firebaseConfig pada :
6. Klik next dan continue to console

# Set-up firebase web app pada VSC
1. Buka VSC, klik File > open folder > cari tempat folder yang kamu buat
2. Pergi ke terminal > new terminal. 
3. Selanjutnya, untuk firebase login kamu bisa memasukkan kode ini pada terminal:
   ``firebase login``
4. Di terminal, akan ada pesan untuk meminta persetujuan pengumpulan informasi penggunaan CLI dan pelaporan kesalahan. Bagian ini terserah anda, bisa disetujui atau tidak. Jika disetujui masukkan ``Y`` , namun untuk menolak masukkan ``N`` , selanjutnya tekan enter
   ![image](https://github.com/user-attachments/assets/1d268c0a-b6ba-47b9-9f0e-e66dcf869a93)
5. Selanjutnya, akan ada pop-up window pada browser untuk memilih akun yang akan masuk pada akun firebase
6. Klik "Allow" firebase CLI untuk akses ke akun Google anda
7. Setelah itu, firebase CLI login selesai. Seperti ini:
   ![Firebase-CLI-Login-Successful](https://github.com/user-attachments/assets/9964d61c-be64-4347-8e4f-2609a0ac30a3)
8. Setelah itu, inisialisasi web app firebase project. Jalankan perintah untuk memulai direktori proyek Firebase di folder saat ini. Dengan kode perintah : ``firebase init``
9. Setelah itu, akan muncul seperti gambar ini. Masukkan ``Y`` dan enter
   ![image](https://github.com/user-attachments/assets/6aeaaf63-4591-4915-bca8-e162a8dc1d18)
10. Selanjutnya, gunakan tombol panah atas dan bawah serta spasi pada keyboard. Terdapat opsi:
      I.   Realtime Database: Configure security rules file for Realtime Database and (optionally) provision default instance.
      II.  Hosting: Configure files for Firebase Hosting and (optionally) set up GitHub Action deploys
    Pilih opsi tersebut dan tekan enter
    ![image](https://github.com/user-attachments/assets/956b0416-4384-411c-a086-6a7a0e46dcb2)
11. Pilih "Use an existing project", dan tekan enter
    ![image](https://github.com/user-attachments/assets/41a75247-4c86-425c-83ba-2d2d0b334e03)
12. Selanjutnya, pilih firebase project pada direktori ini. Sebagai contoh, nama projectnya adalah ``ESP-Project`` dan tekan enter
    ![image](https://github.com/user-attachments/assets/5b14f6c8-1f55-49e5-b84b-031ff06de992)
13. Ikuti opsi ini:
    
    ![image](https://github.com/user-attachments/assets/c8047502-5cc5-4f8f-9b73-479a6e863780)
15. Tekan enter pada pertanyaan yang menyatakan default security rules database file "What file should be used for Realtime Database Security Rules?"
16. Firebase project sudah terinisialisasi, selanjutnya pergi ke VSC dan buat file penting dibawah project folder
    ![image](https://github.com/user-attachments/assets/ff3676f1-79d7-43a3-8938-ccd4ea85fa07)
17. Untuk mengecek jika semuanya sudah sesuai, masukkan kode perintah pada VSC terminal : ``firebase deploy``
    ![image](https://github.com/user-attachments/assets/f8b62c8d-e47c-4bdc-be59-5af2b80aaa94)
    Jika sudah semuanya sudah sesuai, terdapat pesan "Deploy complete"
18. Salin URL hosting dan pastekan pada web browser.
    ![Firebase-Hosting-Setup-Complete](https://github.com/user-attachments/assets/f05d372b-4683-4855-a51d-b5b1eddcc233)
    











  
