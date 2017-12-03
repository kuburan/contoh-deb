contoh cara membuat termux package (.deb) file yg menggunakan python
sebagai bahasa pemrograman nya. tapi bukan hanya untuk python saja,
metode atau cara ini dapat juga digunakan untuk membangun package 
dengan bahasa yg lain seperti :
ruby, perl, dan lainnya.


BAGAIMANA CARA MEMBANGUN NYA ?

ini sangat mudah, hanya dengan beberapa langkah saja sudah selesai.

$ git clone https://github.com/kuburan/contoh-deb.git            
$ cd contoh-deb                             
$ chmod 775 ./contoh_1.0_all/DEBIAN ./contoh_1.0_all/DEBIAN/*                     
$ dpkg-deb --build contoh_1.0_all

( atau dengan data compressed berekstensi xz )

$ dpkg-deb -v -Z xz -b contoh_1.0_all

selesai !! 

untuk menginstall nya sangat mudah, sekali ENTER langsung selesai.

$ apt-get install -y ./contoh_1.0_all.deb            
$ contoh                      
$ apt show contoh

untuk uninstall ketik perintah berikut :

$ apt-get remove contoh                       
atau bisa juga                             
$ apt-get purge contoh
         

NOTE :

1. pastikan internet koneksi lu aktif bro. karena pada proses instalasi akan langsung mendownload six python module.

2. di setiap folder nya, saya selalu membuat file baca-saya-gan.txt
jadi untuk penjelasan lebih lanjut anda bisa membaca file tersebutpada setiap foldernya. 
tutorial ini mudah untuk dipahami asalkan anda mau membaca file pada setiap folder nya.



PENJELASAN UNUTK CONTROL FILE :

1. Packages: adalah nama dari tools yg ingin lu building.

2. Version: adalah versi dari tool tersebut.

3. Architecture: adalah target arsitektur dari tools tersebut,
   macam"2, ada: aarch64, arm, i686, x86_64, all
   nah,, dari contoh diatas berarti saya membangun tool ini
   untuk semua arsitektur (independent architecture).

4. Homepages: adalah website resminya bro, atau rumahnya !! hehe

5. Maintainer: bisa lu isi dengan nama lu, atau apa saja lah, terserah

6. Depends: ini adalah dependensi dari tools yg akan lu building.
   nah, ini penting bro. jangan sampai salah tulis.
   bisa"2 ntar error: unmet dependencies.
   kalau tools tersebut tidak mempunyai dependensi, jadi ga usah ditulis bro.

7. Installed-Size: adalah ukuran, berapa besar package tersebut setelah di install,
   dari contoh diatas saya ambil simple saja sekitar 100 KB.



Terima kasih, semoga bermanfaat.
