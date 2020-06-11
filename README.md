# Webworm

This is merupakan Webworm yang di tulis dalam bahasa PHP, dan merupakan PoC-Worm yang artinya ini merupakan sample dari beberapa Teknik di bidang PHP VXing(Virusing) yang relatif baru, penyebarannya tidak dianjurkan!!

Webworm menyebar melalui beberapa webvulns, menginstal sendiri di server, menginfeksi dan men-backdoor file dan merusak server.

!!! Saya tidak bertanggung jawab atas segala kerusakan atau hal-hal tidak menyenangkan yang muncul. Kode ini atau apapun yang terkait !!!

# Usage

Agar worm berfungsi (Anda tidak berpikir saya akan memberikan versi yang berfungsi penuh sekarang, bukan? wkwk :v) Anda harus menghapus file, dan menggabungkan semua file ke satu (Tidak perlu menggunakan file-file sebagai inlcude, anda hanya perlu men Dump semua code yg ada pada file-file ke satu file inti) maka Anda siap untuk bermain!  (not literally of course XD)

# Worm Operations

  1) Inisialisasi worm, kirim Signature (file was just called by other worm that exploited this server)
  2) Perbarui worm (jika versi yang diunduh lebih baru)
  3) Merusak current server 
  4) Mulai rutinitas eksploitasi
  5) Mulai rutinitas infeksi file
  
  Eksploitasi beroperasi sebagai berikut:
  1) loop melalui semua dorks exploit dan query google
  2) loop melalui maksimal hasil google $ MAIN ['searchlimit'] (mulai dari posisi acak) dan mencoba untuk mengeksploitasi semuanya
  3) permintaan file worm di server jauh, jika merespons dengan Signature worm, kita tahu itu terinfeksi
  
  # Catatan:
  
Saya tidak akan memeriksa forehand jika server sudah terinfeksi, meskipun ini mungkin membuat worm menyebar lebih cepat (dan mencegah risiko DDoS besar dari internet secara umum (adding a bit of code that'd do a check would be easy, but i can't be bothered), itu akan memungkinkan orang untuk membuat server mereka mengirim keluar tanggapan yang salah dengan demikian menjaga worm dari server mereka.

Infeksi file akan beroperasi sebagai berikut:

   1) Crawling drive untuk file php.
   2) Jika nama file cocok dengan regex backdoor, kami backdoorin dan lanjutkan ke langkah 1.
   3) File memiliki kemungkinan 2/5 terinfeksi.
   4) File ini memiliki 1/5 peluang untuk dikaburkan(Obfuscate) daripada terinfeksi (lihat 5 untuk alasannya).
   5) Jika terinfeksi (dan tidak terinfeksi sebelumnya), file tersebut memiliki 1/5 peluang untuk ditambahkan dan 1/5 terinfeksi EPO
     teknik. Jika ditambahkan, file tersebut akan dikaburkan dan diacak juga, sehingga akan sulit
     untuk menganalisis file yang terinfeksi. Itu tidak akan menjadi pilihan yang baik untuk menghapus semua file yang sudah dikaburkan      sejak saat itu beberapa file yang tidak terinfeksi dikaburkan juga.
   6) File yang di-backdoor tidak akan pernah teracak, sehingga menyembunyikan prescence mereka dan karena fakta
     bahwa tidak semua file terinfeksi, akan sulit untuk menemukan backdoor.
     
# Customizing 

  I) Customizing apa pun tidak masalah, selama Anda membiarkan credit notice intact
  II) Sangat mudah untuk menambahkan modul eksploitasi baru ke mesin eksploitasi, pastikan eksploitasi mengikuti aturan berikut
   (unless you wanna get into real difficult stuff and actually make an automated "hacker" XD )
       1) Eksploitasi harus mengunggah file bmbox.php ke server target
       2) file yang diunggah harus dapat diakses dengan permintaan GET (untuk mengaktifkan worm di server itu)
  III) global $ MAIN ['changevars'] tidak boleh berisi vars umum seperti $ i, jangan sampai Anda ingin mengacaukan semuanya
  IV) Global $ MAIN ['signature'] harus cukup unik untuk tidak ada dalam file yang tidak terinfeksi
  V) Pastikan Anda menyertakan $ MAIN ['vx_version'] = <versionnumber> dengan setiap rilis baru (untuk pembaruan) dan <versionnumber> harus selalu berupa bilangan bulat dan lebih tinggi daripada rilis terakhir

# Ide / Todo:

*Menggunakan RSA untuk mengenkripsi file yang dicadangkan

*Cross-infection (PHP->VBS/JS/BAT) || (PHP->CPP (source code infection)

*lebih banyak eksploitasi

*lebih cepat / lebih kecil
 
 # Author || Created By Ardean Bima Saputra
 
 Please make my ass high for subsribing my YouTube Channel : https://www.youtube.com/channel/UC1Hu0kEfFYR1075s6WPr91w
 
 My Portofolio : astrobox.epizy.com
  
